# Lab 02 — Site estático no S3, classes de armazenamento e lifecycle

**Domínios:** D3 (3.5 armazenamento) · D2 (2.2 configuração de acesso)
**Tempo:** ~30 minutos · **Custo:** US$ 0 (dentro do Free Tier)

## Por que este lab

O S3 é o serviço mais cobrado do D3, e as perguntas giram em torno de três coisas: classes de armazenamento, versionamento/lifecycle e **quem** é responsável quando um bucket vaza. Aqui você faz as três.

## O que a prova cobra disso

- Classes do S3 e o trade-off custo × tempo de recuperação (task 3.5).
- Versionamento e lifecycle policies (task 3.5).
- Hospedagem de site estático como caso de uso do S3 (task 3.5).
- Bucket público é responsabilidade de configuração do **cliente** (task 2.1).

## Passos

### 1. Crie o bucket

1. Console → **S3** → **Create bucket**.
2. Nome: precisa ser único globalmente, ex.: `estudos-clf-SEUNOME-2026`.
3. Region: **us-east-1**.
4. Deixe **Block all public access** marcado por enquanto. Crie o bucket.

**Observe:** o nome é global — dois clientes da AWS no mundo inteiro não podem ter o mesmo nome de bucket. Isso denuncia que o S3 é um namespace global, ainda que os dados fiquem na Region escolhida.

### 2. Suba um arquivo e observe a classe

1. Crie um `index.html` local simples:
   ```html
   <!doctype html><html lang="pt-BR"><head><meta charset="utf-8"><title>Meu lab S3</title></head>
   <body><h1>Funcionou</h1><p>Site estático servido pelo Amazon S3.</p></body></html>
   ```
2. No bucket → **Upload** → adicione o arquivo.
3. Antes de confirmar, abra **Properties** no formulário de upload e veja o seletor **Storage class**.

**Observe:** o padrão é **S3 Standard**. Repare nas opções e leia a descrição de cada uma: Standard-IA, One Zone-IA, Intelligent-Tiering, Glacier. É exatamente a tabela que cai na prova, escrita pela própria AWS.

### 3. Ative o versionamento e veja-o funcionar

1. Bucket → aba **Properties** → **Bucket Versioning** → **Enable**.
2. Edite o `index.html` local (mude o texto) e faça upload de novo, com o mesmo nome.
3. Na aba **Objects**, ative o botão **Show versions**.

**Observe:** as duas versões coexistem. Exclua o objeto e note que a AWS cria um *delete marker* em vez de apagar de verdade — é assim que o versionamento protege contra exclusão acidental. Remova o delete marker para "desexcluir".

### 4. Publique como site estático

1. Bucket → **Properties** → role até **Static website hosting** → **Enable**.
2. Index document: `index.html`. Salve.
3. Bucket → **Permissions** → **Block public access** → **Edit** → desmarque tudo → confirme.
4. Ainda em Permissions → **Bucket policy** → cole (troque o nome do bucket):
   ```json
   {
     "Version": "2012-10-17",
     "Statement": [{
       "Sid": "PublicReadForWebsite",
       "Effect": "Allow",
       "Principal": "*",
       "Action": "s3:GetObject",
       "Resource": "arn:aws:s3:::SEU-BUCKET-AQUI/*"
     }]
   }
   ```
5. Volte em **Properties → Static website hosting** e abra a URL do endpoint.

**Observe com atenção:** a AWS te obrigou a **duas** ações deliberadas para tornar o conteúdo público — desativar o Block Public Access e escrever uma policy com `Principal: "*"`. Guarde essa sensação: quando a prova perguntar de quem é a culpa por um bucket exposto, a resposta é do cliente, porque expor exige configuração explícita.

### 5. Crie uma regra de lifecycle

1. Bucket → aba **Management** → **Create lifecycle rule**.
2. Nome: `arquivar-antigos`. Escopo: aplicar a todos os objetos (marque o reconhecimento).
3. Marque **Move current versions of objects between storage classes**:
   - Standard-IA após **30 dias**
   - Glacier Flexible Retrieval após **90 dias**
   - Glacier Deep Archive após **180 dias**
4. Crie a regra e leia o resumo da linha do tempo que a AWS mostra.

**Observe:** essa é a resposta para "como reduzir custo de dados que envelhecem" e para "como reter logs por 7 anos pelo menor custo". Se o padrão de acesso fosse **imprevisível**, a resposta seria Intelligent-Tiering em vez de uma regra fixa.

## O que você deve conseguir explicar depois deste lab

- Quando usar Standard, Standard-IA, Intelligent-Tiering e Glacier Deep Archive.
- A diferença entre versionamento e lifecycle (um protege, o outro economiza).
- Por que um bucket exposto é responsabilidade do cliente.
- Que o S3 hospeda sites estáticos, mas não executa código de servidor.

## Limpeza

1. Bucket → **Objects** → **Show versions** → selecione tudo (inclusive versões e delete markers) → **Delete**.
2. **Permissions** → reative **Block all public access** (bom hábito, mesmo antes de excluir).
3. **S3 → Buckets** → selecione o bucket → **Delete** (é preciso digitar o nome para confirmar).

> Um bucket vazio não gera custo relevante, mas deixar um bucket público esquecido é um risco de segurança. Exclua.
