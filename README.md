# AWS Certified Cloud Practitioner (CLF-C02) — sistema de estudo

Este repositório segue o mesmo formato do meu preparo para a [AWS Certified AI Practitioner](https://github.com/DioAugust/aws-ai-practitioner-aif-c01): edital destrinchado, trilha de estudo e um simulado inédito em PT-BR, tudo pronto para você usar.

### 👉 [Abrir o simulado agora](https://dioaugust.github.io/aws-cloud-foundations/)

100 questões inéditas em PT-BR, direto no navegador. Não precisa baixar nem instalar nada.

> **Passou no AIF-C01 pela promoção `AIF2CLOUD`?** Você tem um **voucher grátis** para esta prova — use até **30/11/2026**. [Detalhes ↓](#promo)

---

Tem três coisas aqui:

| Arquivo | O que é |
|---|---|
| [`index.html`](index.html) | Simulado interativo com **100 questões inéditas em PT-BR**, na proporção oficial dos domínios (24/30/34/12). Roda no navegador, sem instalar nada. |
| [`edital.md`](edital.md) | O exam guide oficial destrinchado: formato, pesos, task statements, os pares de serviços que a prova adora confundir e a lista dos serviços cobrados. |
| Este README | A trilha de estudo, com o material gratuito em português como base. |

---

## A prova em 30 segundos

| Item | Valor |
|---|---|
| Questões | 65 (50 valem nota, 15 são de calibração) |
| Duração | 90 minutos |
| Nota de corte | 700 de 1000 (escala 100–1000) |
| Modelo de nota | compensatório — passa pelo total, não domínio a domínio |
| Custo | USD 100 — **ou grátis com o voucher da promoção abaixo** |
| Nível | Foundational |
| Idioma | dá para fazer em português (Brasil) |
| Aplicação | Pearson VUE ou online proctored |

Pesos dos domínios: **D1** Cloud Concepts 24% · **D2** Security and Compliance 30% · **D3** Cloud Technology and Services 34% · **D4** Billing, Pricing and Support 12%.

O perfil da prova é conceitual: **não cai código, não cai troubleshooting, não cai configuração na prática**. Cai saber o que cada serviço faz, quando usar cada um e como funcionam responsabilidade compartilhada, preços e suporte. D2 + D3 somam **64% da prova** — é onde o estudo mais rende.

---

<a id="promo"></a>

## 💸 Se você veio do AIF-C01: esta prova pode ser de graça

A promoção **AI & Cloud Foundational Certifications** da AWS (código `AIF2CLOUD`) funciona assim:

**Página oficial → https://www.pearsonvue.com/us/en/aws/aif2cloud.html**

1. Quem registrou o **AIF-C01 com o código `AIF2CLOUD`** pagou USD 50 em vez de USD 100.
2. Quem **passou no AIF-C01 até 30/09/2026** recebe automaticamente um **voucher grátis para a CLF-C02** — sem precisar de outro código.
3. O voucher vale para provas realizadas **até 30 de novembro de 2026**.

Se esse é o seu caso, o custo desta certificação é **zero** — e o conteúdo de segurança e compliance que você estudou no AIF (IAM, KMS, shared responsibility, CloudTrail, Artifact) reaparece aqui com peso de 30%. Emendar as duas aproveita o estudo ainda fresco.

> ⚠️ **Promoção com prazo.** Depois de 30/11/2026 a janela do voucher fecha. Confira a [central de certificações da AWS](https://aws.amazon.com/pt/certification/) — a AWS costuma rodar promoções novas, e quem já é certificado ganha um voucher de 50% para a próxima prova na própria conta de certificação.

### Onde agendar

O agendamento sai pela sua **AWS Certification Account**: **https://aws.amazon.com/pt/certification/** — escolha entre centro de testes Pearson VUE e prova online com proctoring. O voucher (ou cupom de 50% de certificações anteriores) é aplicado no pagamento.

---

## A trilha de estudo — 100% gratuita

Tudo nesta trilha custa **zero**: o conteúdo base é open source, o curso e o question set oficiais são gratuitos no Skill Builder, o simulado é deste repo — e, se você veio do AIF-C01 pela promoção, até a prova sai de graça com o voucher. Não precisa comprar curso nem simulado pago para passar nesta certificação.

### 1. Conteúdo base em português — repositório aws-certified-cloud-practitioner-brasil (grátis)

**https://github.com/Thiago-code-lab/aws-certified-cloud-practitioner-brasil**

Foi a fonte de conteúdo desta preparação: material open source em PT-BR cobrindo o edital inteiro em 18 módulos — fundamentos de nuvem, EC2, S3, segurança, redes, bancos de dados, serverless, monitoramento, precificação, migração, CAF, Well-Architected, IA/ML — mais glossário, flashcards, cheatsheets, labs e simulados curtos. Custo zero, sem cadastro.

Ordem de leitura que recomendo (segue o peso da prova, não a numeração dos módulos):

1. **Módulo 01** (introdução à nuvem) + **Módulo 13** (Well-Architected) + **Módulo 12** (CAF) → fecha o D1.
2. **Módulo 03** (segurança e conformidade) → é o coração do D2, leia duas vezes.
3. **Módulos 02, 04, 05, 06, 07, 08, 09, 14, 15** (EC2, S3, redes, bancos, serverless, armazenamento, monitoramento, IA/ML, dev) → o D3 inteiro.
4. **Módulo 10** (precificação e suporte) → D4, curto e decoreba.
5. **Módulo 11** (migração) volta para o D1 (task 1.3), e **17-Glossario** + **cheatsheets** são o material de véspera.

### 2. Curso oficial gratuito — AWS Skill Builder

**https://skillbuilder.aws/category/exam-prep/cloud-practitioner-foundational-CLF-C02**

O plano oficial de preparação em 4 passos da AWS, gratuito, inclui o curso **AWS Cloud Practitioner Essentials** (disponível em português) e o **Official Practice Question Set** com 20 questões no estilo exato da prova. Vale fazer o question set oficial pelo menos uma vez: ele calibra o que a AWS considera "estilo de prova".

### 3. Ler o edital com atenção

O [`edital.md`](edital.md) deste repositório é o exam guide oficial mastigado. Vale ler antes de estudar e reler na véspera. Dois motivos:

- **Peso importa.** D3 (34%) e D2 (30%) juntos são quase dois terços da prova. Uma hora estudando D3 rende quase o triplo de uma hora estudando D4.
- **A prova vive de pares confundíveis.** CloudTrail × Config × CloudWatch, Inspector × Macie × GuardDuty, Multi-AZ × read replica, security group × NACL, SQS × SNS, Cost Explorer × Budgets × Pricing Calculator, CloudFront × Global Accelerator. A lista completa está no edital — dominar esses pares é metade da nota.

### 4. Simulado — treinar em formato de prova

Depois de fechar o conteúdo, o que mais rende é responder questão. O [`index.html`](index.html) deste repo tem 100 questões escritas do zero a partir do exam guide oficial, na proporção exata dos domínios.

---

## O simulado

A forma mais rápida é abrir direto: **https://dioaugust.github.io/aws-cloud-foundations/** — funciona no computador e no celular.

Se preferir ter o arquivo, baixe pelo botão **Code → Download ZIP** e abra o `index.html`. É um arquivo único, sem build, sem servidor, sem dependência: depois de baixado **funciona offline**.

### Modos

| Modo | Para quê |
|---|---|
| **Simulado completo — 65q / 90 min** | Formato oficial, proporção 24/30/34/12 e cronômetro. É o mais parecido com o dia da prova. |
| **Prova rápida — 30q / 45 min** | Diagnóstico do dia, mesma proporção de domínios. |
| **Banco inteiro — 100q** | Maratona de revisão, sem cronômetro. |
| **Treino por domínio** | Ataca um domínio isolado depois de identificar o ponto fraco. |
| **Modo estudo** | Mostra o gabarito e a explicação assim que você responde. Bom no começo, ruim perto da prova. |

Ainda dá para embaralhar questões e alternativas, marcar questões para revisar e navegar pelo mapa de questões. Teclado: `1`–`5` marcam alternativa, `←` e `→` navegam.

### O painel de resultado é a parte que importa

No fim ele mostra acerto por domínio e por task statement — ordenado por **perda ponderada**, que é o seu erro multiplicado pelo peso do domínio na prova.

Essa é a diferença entre "errei 40% do D4" e "o D4 está me custando 4,8 pontos da nota". Como o D3 pesa quase o triplo do D4, errar 30% do D3 dói muito mais do que errar 50% do D4. **Estude de cima para baixo nessa lista** e cada hora rende o máximo de nota possível.

O resultado também sai em `.json` para você comparar tentativas ao longo do tempo.

---

## O que eu recomendo (vindo do AIF-C01)

- **Começar pelo D2.** Se você fez o AIF, o modelo de responsabilidade compartilhada, IAM, KMS, CloudTrail e Artifact já são conhecidos — o D2 desta prova (30%) é em grande parte revisão. É a nota mais barata de consolidar primeiro.
- **Decorar os pares confundíveis.** A prova inteira é "qual serviço faz X". A tabela de pares que a AWS adora trocar está no [`edital.md`](edital.md). Flashcards do repositório do Thiago ajudam aqui.
- **Não subestimar o D4.** São só 12%, mas é o domínio mais decoreba e previsível da prova: planos de suporte, modelos de compra do EC2 e as três ferramentas de custo. Meia tarde de estudo compra esses pontos inteiros.
- **Fazer o Official Practice Question Set.** É grátis no Skill Builder e calibra o estilo oficial de enunciado.
- **Sair do modo estudo cedo.** Ele vicia: você acerta lendo o gabarito, não raciocinando. Na última semana, só simulado cronometrado.

---

## Aviso

Este material é **não oficial**. As questões do simulado foram escritas do zero a partir do exam guide público do CLF-C02 e **não reproduzem questões reais do exame**. AWS e AWS Certified Cloud Practitioner são marcas da Amazon Web Services, Inc. O conteúdo teórico em português referenciado é do repositório [aws-certified-cloud-practitioner-brasil](https://github.com/Thiago-code-lab/aws-certified-cloud-practitioner-brasil) (MIT), de Thiago-code-lab.

## Licença

[MIT](LICENSE) — use, adapte e compartilhe à vontade. Se ajudar alguém, me conta.

---

**@dioaugusto.dev**
