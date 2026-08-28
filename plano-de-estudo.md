# Plano de estudo — 3 semanas até a CLF-C02

Um cronograma dia a dia, montado na ordem do **peso dos domínios**, não na ordem do edital. Cada dia tem teoria (1 h) e prática (30 min). Se você tiver menos tempo, corte a teoria pela metade e **mantenha a prática** — questão e flashcard rendem mais nota por minuto do que releitura.

**Materiais usados aqui, todos gratuitos:**

| Sigla | O que é | Onde |
|---|---|---|
| **SB** | Curso oficial *AWS Cloud Practitioner Essentials* (tem PT-BR) | [Skill Builder](https://skillbuilder.aws/category/exam-prep/cloud-practitioner-foundational-CLF-C02) |
| **ED** | Edital destrinchado deste repo | [`edital.md`](edital.md) |
| **SIM** | Simulado, 150 questões | [index.html](https://dioaugust.github.io/aws-cloud-practitioner/) |
| **FC** | Flashcards com repetição espaçada | [flashcards.html](https://dioaugust.github.io/aws-cloud-practitioner/flashcards.html) |
| **GL** | Glossário pesquisável de serviços | [glossario.html](https://dioaugust.github.io/aws-cloud-practitioner/glossario.html) |
| **VE** | Revisão de véspera | [vespera.html](https://dioaugust.github.io/aws-cloud-practitioner/vespera.html) |
| **LAB** | Labs práticos no Free Tier | [`labs/`](labs/) |

> **Regra de ouro dos flashcards:** faça a sessão "de hoje" **todos os dias**, inclusive nos dias de descanso. São 5–10 minutos e é o que segura o conteúdo das semanas anteriores.

---

## Semana 1 — Fundamentos e Segurança (D1 + D2 = 54% da prova)

| Dia | Teoria (~1 h) | Prática (~30 min) |
|---|---|---|
| **1** | ED: leia o edital inteiro, sem tentar decorar. Só para saber o tamanho do território. SB: módulo 1 (Cloud Concepts). | [LAB 01](labs/lab-01-conta-segura.md) — deixe sua conta segura e com budget. |
| **2** | SB: benefícios da nuvem, modelos de serviço e implantação. ED: seção D1, tasks 1.1 e 1.2. | FC: sessão de hoje (só D1). SIM: treino do **D1**, 15 questões em modo estudo. |
| **3** | ED: Well-Architected (6 pilares) e CAF (6 perspectivas). Escreva os dois de cabeça num papel. | FC: sessão de hoje. SIM: treino do **D1**, mais 15 questões. |
| **4** | ED: 7 Rs da migração + TCO e rightsizing (tasks 1.3 e 1.4). GL: leia as entradas de migração (DMS, Snow Family, Migration Hub). | FC: sessão de hoje. SIM: treino do **D1** completo, agora **sem** modo estudo. |
| **5** | SB: módulo de segurança. ED: D2, tasks 2.1 e 2.2 (responsabilidade compartilhada, Artifact, CloudTrail × Config × CloudWatch). | FC: sessão de hoje. SIM: treino do **D2**, 15 questões em modo estudo. |
| **6** | ED: D2, tasks 2.3 e 2.4 (IAM, root, MFA, SCPs, WAF/Shield, GuardDuty/Inspector/Macie). GL: leia todas as entradas da categoria **Segurança**. | [LAB 04](labs/lab-04-cloudwatch-custos.md) — passeio pelas telas de custo e suporte. |
| **7** | **Descanso ativo.** Só releia os 20 fatos da [VE](https://dioaugust.github.io/aws-cloud-practitioner/vespera.html). | FC: sessão de hoje. SIM: **prova rápida (30q)** — seu primeiro diagnóstico. |

**Meta da semana 1:** acertar ≥ 60% na prova rápida do dia 7. Se ficou abaixo, repita o treino dos domínios fracos antes de seguir.

---

## Semana 2 — Tecnologia e Serviços + Custos (D3 + D4 = 46% da prova)

| Dia | Teoria (~1 h) | Prática (~30 min) |
|---|---|---|
| **8** | ED: D3, tasks 3.1 e 3.2 (console/CLI/SDK, CloudFormation, Beanstalk, Regions/AZs/edge, Outposts). | FC: sessão de hoje. SIM: treino do **D3**, 15 questões em modo estudo. |
| **9** | ED: D3, task 3.3 (EC2, famílias, Lambda, ECS/EKS/Fargate, Auto Scaling, ELB). GL: categoria **Computação**. | [LAB 03](labs/lab-03-ec2-role-s3.md) — EC2 + role + security group. O lab que mais rende. |
| **10** | ED: D3, tasks 3.4 e 3.5 (bancos e armazenamento). Foque em **Multi-AZ × read replica** e nas **classes do S3**. | [LAB 02](labs/lab-02-site-estatico-s3.md) — S3, versionamento e lifecycle. |
| **11** | ED: D3, task 3.6 (VPC, subnets, NAT, endpoints, VPN × Direct Connect, CloudFront × Global Accelerator). GL: categoria **Rede**. | FC: sessão de hoje. SIM: treino do **D3**, mais 15 questões. |
| **12** | ED: D3, tasks 3.7 e 3.8 (IA/ML, analytics, SQS/SNS/EventBridge/Step Functions). GL: categorias **IA e ML**, **Analytics** e **Integração**. | FC: sessão de hoje. SIM: treino do **D3** completo, sem modo estudo. |
| **13** | ED: D4 inteiro (modelos de compra, ferramentas de custo, planos de suporte). É curto e decoreba — leia duas vezes. | FC: sessão de hoje. SIM: treino do **D4** completo. |
| **14** | **Descanso ativo.** Releia as tabelas de decisão da [VE](https://dioaugust.github.io/aws-cloud-practitioner/vespera.html), parte 1. | SIM: **simulado completo (65q, 90 min)**, cronometrado, sem modo estudo. |

**Meta da semana 2:** ≥ 70% no simulado completo do dia 14. O painel de perda ponderada dá a fila de prioridade da semana 3.

---

## Semana 3 — Consolidação e simulados

| Dia | Teoria (~1 h) | Prática (~30 min) |
|---|---|---|
| **15** | Ataque o domínio no topo da **perda ponderada** do último simulado. Releia a seção dele no ED. | SIM: **caderno de erros** — treine todas as questões acumuladas. |
| **16** | Faça o **Official Practice Question Set** (20 questões) no Skill Builder e revise cada erro na documentação oficial. | FC: sessão de hoje. |
| **17** | Segundo domínio mais fraco. GL: releia as entradas dos serviços que você errou. | SIM: **simulado completo (65q)** cronometrado. |
| **18** | VE: checklist da parte 2 — marque só o que você explicaria em voz alta. Estude o que sobrou desmarcado. | SIM: caderno de erros de novo. |
| **19** | Revisão dos pares confundíveis (VE parte 1), em voz alta, sem olhar. | SIM: **simulado completo (65q)** cronometrado. |
| **20** | Leve: releia os 20 fatos e o checklist. Nada novo a partir daqui. | FC: sessão de hoje + **banco inteiro** no SIM se ainda tiver energia. |
| **21** | **Véspera.** Leia a [VE](https://dioaugust.github.io/aws-cloud-practitioner/vespera.html) inteira, do início ao fim, uma única vez. Durma cedo. | Nada. Sério. |

**Meta da semana 3:** ≥ 80% em dois simulados completos seguidos.

---

## Quando agendar a prova

Agende **assim que bater a meta**: dois simulados completos consecutivos com **80% ou mais**, sem modo estudo e cronometrados. A margem existe porque simulado caseiro nunca é idêntico à prova real — mirar em 80% aqui é o que dá conforto para os 700 pontos (70%) de lá.

Se você tem o **voucher gratuito da promoção AIF2CLOUD**, lembre do prazo: a prova precisa ser realizada até **30 de novembro de 2026**. Agende com folga — vagas em centro de teste e horários de prova online esgotam perto do fim do prazo.

Agendamento: **https://aws.amazon.com/pt/certification/**

## Se você tem menos de 3 semanas

- **10 dias:** faça a semana 1 em 4 dias (só D1 e D2), a semana 2 em 4 dias (D3 e D4) e reserve 2 dias para simulado + caderno de erros. Corte os labs 02 e 04.
- **1 semana:** leia o `edital.md` inteiro no dia 1, faça o baralho completo de flashcards nos dias 2 e 3, e do dia 4 em diante só simulado + caderno de erros. Leia a véspera no último dia.
- **1 dia (não recomendado):** [VE](https://dioaugust.github.io/aws-cloud-practitioner/vespera.html) inteira + uma prova rápida de 30 questões + o caderno de erros. É o máximo que dá para fazer sem se enganar.

## No dia da prova

- Chegue (ou entre na sala online) com **30 minutos de antecedência**; a prova online exige documento com foto, mesa limpa e ambiente sem interrupções.
- São 65 questões em 90 minutos: **~80 segundos por questão**. Não trave: marque para revisão e siga.
- Elimine primeiro as alternativas com absolutos ("sempre", "nunca", "elimina totalmente") — quase nunca são a resposta.
- Procure a palavra que decide o serviço: *auditoria*, *failover*, *menor custo*, *sem servidores*, *tempo real*, *Kubernetes*.
- **Responda todas.** Não há penalidade por erro — questão em branco é ponto perdido de graça.
