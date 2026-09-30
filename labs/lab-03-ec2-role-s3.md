# Lab 03 — EC2, security group e acesso ao S3 por IAM role (sem chave nenhuma)

**Domínios:** D3 (3.3 computação, 3.6 rede) · D2 (2.3 acessos, 2.4 segurança)
**Tempo:** ~40 minutos · **Custo:** US$ 0 (t2.micro/t3.micro no Free Tier — **desligue no fim**)

## Por que este lab

Este é o lab que mais vale a pena. Você vai ver, na prática, por que a AWS insiste que **role é melhor que access key** — e vai encostar em security group, Region, AZ e responsabilidade compartilhada no mesmo exercício.

## O que a prova cobra disso

- IAM role para aplicações, com credenciais temporárias (task 2.3).
- Security group stateful, no nível da instância (task 2.4).
- Famílias e tipos de instância EC2 (task 3.3).
- Patch do sistema operacional é responsabilidade do cliente (task 2.1).

## Passos

### 1. Crie a IAM role da instância

1. **IAM** → **Roles** → **Create role**.
2. Trusted entity: **AWS service** → caso de uso **EC2**.
3. Permissions: procure e marque **AmazonS3ReadOnlyAccess**.
4. Nome: `ec2-le-s3`. Crie.

**Observe:** você definiu *quem pode assumir* (o serviço EC2, na trust policy) e *o que pode fazer* (a permissions policy). Toda role tem essas duas metades — e a prova cobra a existência das duas.

### 2. Suba a instância

1. **EC2** → **Launch instance**.
2. Nome: `lab-clf`.
3. AMI: **Amazon Linux 2023** (marcada como *Free tier eligible*).
4. Tipo: **t2.micro** ou **t3.micro** (o que estiver marcado como Free tier eligible na sua Region).
5. Key pair: escolha **Proceed without a key pair** — vamos entrar sem SSH.
6. **Network settings** → Edit:
   - Deixe a VPC default e uma subnet pública.
   - **Auto-assign public IP: Enable**.
   - Security group: crie um novo, `sg-lab-clf`, e **remova a regra de SSH** que vem sugerida. Deixe o grupo sem nenhuma regra de entrada.
7. **Advanced details** → role até **IAM instance profile** → selecione **`ec2-le-s3`**.
8. Launch.

**Observe:** você subiu um servidor **sem abrir nenhuma porta de entrada** e **sem chave SSH**. Guarde isso: o security group nega toda entrada por padrão; foi preciso não fazer nada para ficar fechado.

### 3. Entre na instância sem SSH (Session Manager)

1. Espere o status ficar **Running** com os checks passando (2/2).
2. Selecione a instância → **Connect** → aba **Session Manager** → **Connect**.

Se o botão estiver desabilitado, é porque falta a permissão do SSM na role. Corrija assim: **IAM → Roles → `ec2-le-s3` → Add permissions → Attach policies → `AmazonSSMManagedInstanceCore`**. Aguarde ~1 minuto e tente de novo.

**Observe:** você abriu um terminal na máquina sem porta 22 aberta e sem chave privada. O Session Manager (parte do **AWS Systems Manager**) é exatamente a resposta que a prova espera em cenários de "acesso administrativo seguro sem expor SSH".

### 4. Prove que a role funciona

No terminal da instância:

```bash
aws sts get-caller-identity
```

Você verá um ARN do tipo `assumed-role/ec2-le-s3/i-0abc...` — a instância está usando **credenciais temporárias da role**, não credenciais suas.

```bash
aws s3 ls
```

Lista seus buckets (incluindo o do Lab 02, se ainda existir).

```bash
aws s3 mb s3://tentativa-de-criar-bucket-lab-clf
```

**Falha com AccessDenied.** A role só tem permissão de leitura.

Agora olhe as credenciais que a instância está usando:

```bash
TOKEN=$(curl -sX PUT "http://169.254.169.254/latest/api/token" -H "X-aws-ec2-metadata-token-ttl-seconds: 60")
curl -s -H "X-aws-ec2-metadata-token: $TOKEN" http://169.254.169.254/latest/meta-data/iam/security-credentials/ec2-le-s3
```

**Observe:** aparecem `AccessKeyId`, `SecretAccessKey`, `Token` e — o mais importante — **`Expiration`**. É esse campo que resume o lab inteiro: as credenciais **expiram e são rotacionadas sozinhas**. Uma access key gravada em arquivo não expira nunca; vazou, vazou para sempre. Por isso a resposta certa na prova é sempre *role*, nunca *access key no servidor*.

### 5. Veja o patching ser problema seu

```bash
sudo dnf check-update | head -20
```

**Observe:** há atualizações pendentes do sistema operacional. Ninguém da AWS vai aplicá-las nesta instância — em EC2, o guest OS é do cliente. Se este fosse um Amazon RDS, o patch do SO e do engine seria da AWS. É a fronteira móvel do modelo de responsabilidade compartilhada, ao vivo.

### 6. (Opcional) Veja o security group em ação

1. No console, EC2 → sua instância → copie o **Public IPv4 address**.
2. Do seu computador: `ping SEU-IP` ou tente abrir `http://SEU-IP` no navegador — não responde.
3. Adicione ao `sg-lab-clf` uma regra de entrada **HTTP (80)** com origem **My IP**, instale um servidor web na instância (`sudo dnf install -y httpd && sudo systemctl start httpd && echo ok | sudo tee /var/www/html/index.html`) e tente de novo.

**Observe:** a resposta do servidor volta para você sem que você tenha criado nenhuma regra de **saída** para o seu IP. Isso é o *stateful* do security group na prática — com NACL (stateless), seria preciso regra nos dois sentidos.

## O que você deve conseguir explicar depois deste lab

- Por que IAM role é mais seguro que access key (a palavra-chave é **Expiration**).
- Que security group é stateful e nega entrada por padrão.
- Que o Session Manager dá acesso sem abrir a porta 22.
- Onde termina a responsabilidade da AWS e começa a sua em uma instância EC2.

## Limpeza — **não pule esta parte**

1. **EC2 → Instances** → selecione `lab-clf` → **Instance state** → **Terminate instance**.
   (Terminate destrói; *Stop* apenas para, e o volume EBS continua sendo cobrado.)
2. **EC2 → Volumes**: confirme que não sobrou volume `available` — se sobrar, exclua.
3. **EC2 → Security Groups** → exclua `sg-lab-clf` (só é possível depois que a instância termina).
4. **IAM → Roles** → exclua `ec2-le-s3` se não for usar mais.
5. Confira o **Billing Dashboard** no dia seguinte.

> A instância cabe no Free Tier (créditos nas contas novas, 750 h/mês nas contas do modelo antigo), mas o **IP público e o volume EBS** podem gerar centavos se ficarem esquecidos. Termine a instância.
