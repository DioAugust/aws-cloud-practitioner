# Lab 01 — Deixando a conta segura (e sem sustos na fatura)

**Domínios:** D2 (2.3 gerenciamento de acessos) · D4 (4.2 gestão de custos)
**Tempo:** ~30 minutos · **Custo:** US$ 0

## Por que este lab

Três das perguntas mais previsíveis da prova saem daqui: *o que fazer com o usuário root*, *por que usar IAM em vez de root* e *qual a primeira providência para não estourar o orçamento*. Depois de configurar isso com as próprias mãos, você não erra mais nenhuma delas.

## O que a prova cobra disso

- Root com MFA, reservado para tarefas excepcionais (task 2.3).
- Usuários e grupos IAM com menor privilégio (task 2.3).
- AWS Budgets como proteção contra custo inesperado (task 4.2).
- Free Tier tem limites — ultrapassou, cobra (task 4.1).

## Passos

### 1. Ative o MFA no usuário root

1. Entre no console como **root** (o e-mail com que criou a conta).
2. Menu do seu nome (canto superior direito) → **Security credentials**.
3. Em **Multi-factor authentication (MFA)** → **Assign MFA device**.
4. Escolha **Authenticator app** e escaneie o QR code com um app (Google Authenticator, Authy, 1Password, Microsoft Authenticator).
5. Digite dois códigos consecutivos para confirmar.

**Observe:** a AWS pede *dois* códigos seguidos justamente para provar que o relógio do seu dispositivo está sincronizado.

### 2. Crie um alias para a conta

1. Ainda no console, vá em **IAM** → painel inicial.
2. Em **AWS Account**, ao lado de *Account Alias*, clique em **Create**.
3. Escolha algo como `dioaugusto-estudos`.

**Observe:** o link de login deixa de ser o número de 12 dígitos e vira `https://SEU-ALIAS.signin.aws.amazon.com/console`.

### 3. Crie um usuário IAM administrativo para o dia a dia

1. **IAM** → **Users** → **Create user**.
2. Nome: `admin-estudos`. Marque **Provide user access to the AWS Management Console**.
3. Em permissões, escolha **Add user to group** → **Create group**.
4. Nome do grupo: `Administradores`. Anexe a policy gerenciada **AdministratorAccess**.
5. Crie o usuário e **guarde a senha inicial**.
6. Saia do root, entre com o novo usuário e **ative MFA nele também** (Security credentials → MFA).

**Observe:** você criou um *grupo* e colocou o usuário nele, em vez de anexar a policy direto ao usuário. É assim que a AWS recomenda gerenciar permissões — e é o que a prova cobra.

> **Nota de menor privilégio:** `AdministratorAccess` para o seu usuário de estudos é aceitável porque a conta é sua e é um laboratório. Em ambiente real, o princípio do menor privilégio pede permissões restritas ao necessário — a prova sempre trata "AdministratorAccess para todos" como resposta errada.

### 4. Crie um orçamento com alerta

1. Faça login com o usuário `admin-estudos`.
2. Vá em **Billing and Cost Management** → **Budgets** → **Create budget**.
3. Escolha **Use a template (simplified)** → **Monthly cost budget** (ou *Zero spend budget*, se quiser ser avisado ao primeiro centavo).
4. Defina o valor (ex.: **US$ 1,00**) e o seu e-mail.
5. Crie o orçamento.

**Observe:** o Budgets **avisa**, não bloqueia. A AWS não interrompe recursos automaticamente ao atingir um valor — este é um ponto que a prova adora testar.

### 5. Olhe o painel de Free Tier

1. Em **Billing and Cost Management** → **Free tier**.
2. Veja a tabela de uso atual contra os limites do nível gratuito.

**Observe:** contas criadas desde julho/2025 veem aqui o saldo de créditos e o prazo do plano gratuito (até 6 meses), além das ofertas always free com o percentual já consumido. Contas mais antigas ainda mostram o modelo anterior (12 meses, always free e trials).

## O que você deve conseguir explicar depois deste lab

- Por que o root não é usado no dia a dia e o que só ele pode fazer.
- A diferença entre anexar policy a um usuário e a um grupo.
- O que o AWS Budgets faz — e o que ele **não** faz.
- Por que o Free Tier não é uma garantia de custo zero.

## Limpeza

Nada aqui gera custo, então **não remova**: mantenha o MFA, o usuário IAM e o budget ativos. Eles protegem a conta durante os próximos labs.

Se quiser desfazer mesmo assim: IAM → Users → excluir `admin-estudos`; IAM → User groups → excluir `Administradores`; Budgets → excluir o orçamento.
