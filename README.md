# AWS Certified Cloud Practitioner (CLF-C02) — sistema de estudo gratuito

Este repositório segue o mesmo formato do meu preparo para a [AWS Certified AI Practitioner](https://github.com/DioAugust/aws-ai-practitioner-aif-c01), agora com mais ferramentas: simulado, flashcards com repetição espaçada, revisão de véspera, glossário pesquisável, labs práticos e um plano de 3 semanas. **Tudo gratuito, tudo em português, nada para instalar.**

### 👉 [Abrir o simulado agora](https://dioaugust.github.io/aws-cloud-foundations/)

> **Passou no AIF-C01 pela promoção `AIF2CLOUD`?** Você tem um **voucher grátis** para esta prova — use até **30/11/2026**. [Detalhes ↓](#promo)

---

## O sistema de estudo

| Ferramenta | O que faz | Quando usar |
|---|---|---|
| [**Simulado**](https://dioaugust.github.io/aws-cloud-foundations/) | **150 questões inéditas** na proporção oficial dos domínios, com prova completa cronometrada, treino por domínio e **caderno de erros que persiste entre sessões** | O tempo todo — é o que mais rende nota |
| [**Flashcards**](https://dioaugust.github.io/aws-cloud-foundations/flashcards.html) | **120 cards** com repetição espaçada (método de Leitner): o que você erra volta hoje, o que acerta volta cada vez mais tarde | 5–10 min por dia, todos os dias |
| [**Véspera**](https://dioaugust.github.io/aws-cloud-foundations/vespera.html) | 15 tabelas de decisão dos serviços que a prova confunde, checklist auto-avaliável e os 20 fatos que caem quase sempre | Na semana final e no dia anterior |
| [**Glossário**](https://dioaugust.github.io/aws-cloud-foundations/glossario.html) | **100 serviços** com busca instantânea: o que é, quando é a resposta e com o que a prova o confunde | Sempre que travar num serviço |
| [**Labs**](labs/) | 4 roteiros práticos no Free Tier (conta segura, S3, EC2 com IAM role, custos) | Uma vez cada, para fixar conceito |
| [**Plano de estudo**](plano-de-estudo.md) | Cronograma dia a dia de 3 semanas, com versões para 10 dias, 1 semana e 1 dia | No começo, para se organizar |
| [**Edital**](edital.md) | O exam guide oficial destrinchado: pesos, task statements e lista de serviços | Antes de estudar e na véspera |

Tudo roda no navegador, funciona no celular e **funciona offline** depois de baixado (**Code → Download ZIP**). O progresso (histórico, caderno de erros, caixas de flashcard, checklist) fica salvo no seu navegador — nada é enviado para lugar nenhum.

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
| Validade | 3 anos |

Pesos: **D1** Cloud Concepts 24% · **D2** Security and Compliance 30% · **D3** Cloud Technology and Services 34% · **D4** Billing, Pricing and Support 12%.

O perfil da prova é conceitual: **não cai código, não cai troubleshooting, não cai configuração na prática**. Cai saber o que cada serviço faz, quando usar cada um, e como funcionam responsabilidade compartilhada, preços e suporte. D2 + D3 somam **64% da prova** — é onde o estudo mais rende.

---

<a id="promo"></a>

## 💸 Se você veio do AIF-C01: esta prova pode ser de graça

A promoção **AI & Cloud Foundational Certifications** da AWS (código `AIF2CLOUD`) funciona assim:

**Página oficial → https://www.pearsonvue.com/us/en/aws/aif2cloud.html**

1. Quem registrou o **AIF-C01 com o código `AIF2CLOUD`** pagou USD 50 em vez de USD 100.
2. Quem **passou no AIF-C01 até 30/09/2026** recebe automaticamente um **voucher grátis para a CLF-C02** — sem precisar de outro código.
3. O voucher vale para provas realizadas **até 30 de novembro de 2026**.

Se esse é o seu caso, o custo desta certificação é **zero** — e o conteúdo de segurança e compliance que você estudou no AIF (IAM, KMS, shared responsibility, CloudTrail, Artifact) reaparece aqui com peso de 30%.

> ⚠️ **Promoção com prazo.** Depois de 30/11/2026 a janela do voucher fecha. Confira a [central de certificações da AWS](https://aws.amazon.com/pt/certification/) — a AWS costuma rodar promoções novas, e quem já é certificado ganha um voucher de 50% para a próxima prova na própria conta de certificação.

### Onde agendar

Pela sua **AWS Certification Account**: **https://aws.amazon.com/pt/certification/** — escolha entre centro de testes Pearson VUE e prova online com proctoring, e aplique o voucher no pagamento.

---

## A trilha de estudo — 100% gratuita

Nada aqui custa dinheiro: o curso oficial é gratuito, o material deste repo é aberto e, com o voucher, até a prova sai de graça. O [`plano-de-estudo.md`](plano-de-estudo.md) organiza tudo isso em 3 semanas, dia a dia.

### 1. Conteúdo base — AWS Skill Builder (oficial e gratuito, em PT-BR)

**https://skillbuilder.aws/category/exam-prep/cloud-practitioner-foundational-CLF-C02**

O plano oficial de preparação em 4 passos inclui o curso **AWS Cloud Practitioner Essentials** — que tem versão em português — e o **Official Practice Question Set** com 20 questões no estilo exato da prova. Este é o material de teoria principal: é da própria AWS, é gratuito e está sempre alinhado ao exam guide vigente.

### 2. O edital destrinchado

O [`edital.md`](edital.md) deste repositório é o exam guide oficial mastigado. Leia antes de estudar e releia na véspera:

- **Peso importa.** D3 (34%) e D2 (30%) juntos são quase dois terços da prova. Uma hora estudando D3 rende quase o triplo de uma hora estudando D4.
- **A prova vive de pares confundíveis.** CloudTrail × Config × CloudWatch, Inspector × Macie × GuardDuty, Multi-AZ × read replica, security group × NACL, SQS × SNS, Cost Explorer × Budgets × Pricing Calculator, CloudFront × Global Accelerator. Todos estão nas tabelas de decisão da [página de véspera](https://dioaugust.github.io/aws-cloud-foundations/vespera.html).

### 3. Prática diária: flashcards + questões

Flashcards de manhã (5–10 min, só o que está vencido) e questões à noite. O [caderno de erros](https://dioaugust.github.io/aws-cloud-foundations/) do simulado acumula tudo que você errou entre sessões e só solta a questão quando você acerta de novo.

> **Sobre o idioma:** a prova pode ser feita em português, mas os **nomes dos serviços e a documentação vivem em inglês**. Vale se acostumar com os termos originais (`shared responsibility model`, `least privilege`, `read replica`, `lifecycle policy`) mesmo estudando em PT-BR — é assim que a prova traduzida se comporta, e é assim que o material deste repo foi escrito.

---

## O simulado em detalhe

### Modos

| Modo | Para quê |
|---|---|
| **Simulado completo — 65q / 90 min** | Formato oficial, proporção 24/30/34/12 e cronômetro. É o mais parecido com o dia da prova. |
| **Prova rápida — 30q / 45 min** | Diagnóstico do dia, mesma proporção de domínios. |
| **Banco inteiro — 150q** | Maratona de revisão, sem cronômetro. |
| **Treino por domínio** | Ataca um domínio isolado depois de identificar o ponto fraco. |
| **Caderno de erros** | Só as questões que você já errou e ainda não recuperou. Persiste entre sessões. |
| **Modo estudo** | Mostra o gabarito e a explicação assim que você responde. Bom no começo, ruim perto da prova. |

Dá para embaralhar questões e alternativas, marcar para revisar e navegar pelo mapa de questões. Teclado: `1`–`5` marcam alternativa, `←` e `→` navegam.

### O painel de resultado é a parte que importa

Ele mostra acerto por domínio e por task statement — ordenado por **perda ponderada**, que é o seu erro multiplicado pelo peso do domínio na prova.

Essa é a diferença entre "errei 40% do D4" e "o D4 está me custando 4,8 pontos da nota". Como o D3 pesa quase o triplo do D4, errar 30% do D3 dói muito mais do que errar 50% do D4. **Estude de cima para baixo nessa lista.**

A home guarda o histórico das suas tentativas com um gráfico de evolução da nota contra a linha de corte, e o resultado sai em `.json` se você quiser comparar por fora.

---

## Recomendações (vindas de quem fez o AIF-C01 antes)

- **Comece pelo D2.** Se você fez o AIF, responsabilidade compartilhada, IAM, KMS, CloudTrail e Artifact já são conhecidos — o D2 (30%) é em boa parte revisão. É a nota mais barata de consolidar primeiro.
- **Decore os pares confundíveis.** A prova inteira é "qual serviço faz X". As tabelas da [véspera](https://dioaugust.github.io/aws-cloud-foundations/vespera.html) existem só para isso.
- **Não subestime o D4.** São só 12%, mas é o domínio mais previsível da prova: planos de suporte, modelos de compra do EC2 e as três ferramentas de custo. Meia tarde compra esses pontos inteiros — o [Lab 04](labs/lab-04-cloudwatch-custos.md) faz esse passeio.
- **Faça o [Lab 03](labs/lab-03-ec2-role-s3.md).** É o que mais fixa conceito: você vê com os próprios olhos por que IAM role é melhor que access key (a palavra-chave é `Expiration`).
- **Faça o Official Practice Question Set.** É grátis no Skill Builder e calibra o estilo oficial de enunciado.
- **Saia do modo estudo cedo.** Ele vicia: você acerta lendo o gabarito, não raciocinando. Na última semana, só simulado cronometrado.

---

## Aviso

Este material é **não oficial**. As questões e os flashcards foram escritos do zero a partir do exam guide público do CLF-C02 e **não reproduzem questões reais do exame**. AWS e AWS Certified Cloud Practitioner são marcas da Amazon Web Services, Inc. Os labs usam o AWS Free Tier, mas a responsabilidade pelos custos da sua conta é sua — siga as seções de limpeza.

O repositório [aws-certified-cloud-practitioner-brasil](https://github.com/Thiago-code-lab/aws-certified-cloud-practitioner-brasil) (MIT), de Thiago-code-lab, é referenciado como material complementar e inspirou os formatos de flashcards, checklist e labs deste repo.

## Licença

[MIT](LICENSE) — use, adapte e compartilhe à vontade. Se ajudar alguém, me conta.

---

**@dioaugusto.dev**
