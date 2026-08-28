# AWS Certified Cloud Practitioner (CLF-C02) — edital e plano de estudo

Fonte: exam guide oficial da AWS (docs.aws.amazon.com/aws-certification), consultado em 27/08/2026.

## Formato da prova

| Item | Valor |
|---|---|
| Questões | 65 (50 pontuadas + 15 não pontuadas) |
| Duração | 90 minutos |
| Nota de corte | 700 de 1000 (escala 100–1000) |
| Modelo de nota | compensatório — passa pelo total, não por domínio |
| Tipos | múltipla escolha (4 opções, 1 correta) e múltipla resposta (5 opções, 2 corretas) |
| Custo | USD 100 |
| Nível | Foundational |
| Idiomas | inclui português (Brasil) |
| Aplicação | Pearson VUE ou online proctored |
| Validade | 3 anos |

Perfil-alvo: até 6 meses de exposição à AWS, **inclusive quem não vem de TI** (vendas, financeiro, jurídico, gestão). A prova valida entendimento conceitual da nuvem AWS, não habilidade prática de construir.

**Fora de escopo:** codificação, design de arquiteturas na prática, troubleshooting, implementação e migração hands-on, testes de carga. Você precisa saber **o que cada serviço faz e quando usá-lo**, não como operá-lo.

## Domínios e pesos

| Domínio | Peso |
|---|---|
| D1 — Cloud Concepts | 24% |
| D2 — Security and Compliance | 30% |
| D3 — Cloud Technology and Services | 34% |
| D4 — Billing, Pricing, and Support | 12% |

D2 + D3 somam **64% da prova**. É onde o estudo mais rende.

## Task statements

**D1 — Cloud Concepts (24%)**

- **1.1 Benefícios da nuvem AWS** — proposta de valor; trocar CapEx por OpEx (custo variável); economias de escala; parar de adivinhar capacidade; agilidade e velocidade; alcance global em minutos; economia de escala vs. elasticidade vs. alta disponibilidade; pay-as-you-go.
- **1.2 Princípios de design da nuvem AWS** — os **6 pilares do Well-Architected Framework** (excelência operacional, segurança, confiabilidade, eficiência de performance, otimização de custos, sustentabilidade); design for failure; desacoplamento (loose coupling); escala horizontal; Well-Architected Tool.
- **1.3 Migração para a nuvem** — **AWS CAF** e suas 6 perspectivas (Business, People, Governance / Platform, Security, Operations); **estratégias de migração (7 Rs)**: rehost, replatform, refactor, repurchase, retire, retain, relocate; Snow Family, DMS, Migration Hub, Application Discovery Service.
- **1.4 Economia da nuvem** — TCO e custos on-premises escondidos (energia, refrigeração, equipe, espaço); rightsizing; automação como redução de custo; serviços gerenciados reduzindo custo operacional; BYOL e licenciamento.

**D2 — Security and Compliance (30%)**

- **2.1 Modelo de responsabilidade compartilhada** — segurança **DA** nuvem (AWS) vs. **NA** nuvem (cliente); como a fronteira se move por serviço (EC2 → RDS → Lambda/S3); o que é sempre do cliente (dados, classificação, IAM) e sempre da AWS (físico, hardware, hypervisor, infraestrutura global).
- **2.2 Segurança, governança e compliance** — **AWS Artifact** (relatórios SOC, ISO, PCI); compliance varia por serviço e por Region; criptografia at rest (KMS) e in transit (TLS); quem habilita a criptografia; **CloudTrail** (quem fez o quê) vs. **AWS Config** (como o recurso está configurado) vs. **CloudWatch** (métricas/logs); residência de dados; least privilege.
- **2.3 Gerenciamento de acessos (IAM)** — proteção do **root** (MFA, não usar no dia a dia); usuários, grupos, roles e políticas; **roles com credenciais temporárias > access keys**; MFA; rotação de credenciais; AWS managed vs. customer managed policies; **IAM Identity Center** (SSO multi-conta e federação com AD); **AWS Organizations + SCPs** (guardrails que políticas locais não passam).
- **2.4 Componentes e recursos de segurança** — **security groups (stateful, instância) vs. NACLs (stateless, subnet)**; **WAF** (SQL injection/XSS) vs. **Shield** (DDoS); **GuardDuty** (detecção de ameaças) vs. **Inspector** (vulnerabilidades) vs. **Macie** (dados sensíveis no S3); **Security Hub** (consolidação); **KMS** (chaves) vs. **Secrets Manager** (segredos com rotação); onde achar informação oficial de segurança (Security Blog, Knowledge Center, documentação, whitepapers).

**D3 — Cloud Technology and Services (34%) — maior peso da prova**

- **3.1 Implantação e operação** — console vs. **CLI** (scripts) vs. **SDKs** (código); infraestrutura como código com **CloudFormation**; **Elastic Beanstalk** (PaaS); modelos de nuvem: pública, híbrida, on-premises/privada.
- **3.2 Infraestrutura global** — **Regions → AZs → edge locations**; multi-AZ = alta disponibilidade; multi-Region = DR e latência global; **CloudFront** (CDN nas edge locations); **Global Accelerator** (tráfego dinâmico TCP/UDP via backbone AWS); critérios de escolha de Region (latência, compliance, serviços, preço); **Outposts** (AWS no seu datacenter), Local Zones, Wavelength.
- **3.3 Computação** — famílias EC2 (general purpose, **compute optimized = C**, **memory optimized = R**, storage optimized); **Lambda** (serverless por evento); contêineres: **ECS** (orquestrador AWS) vs. **EKS** (Kubernetes) vs. **Fargate** (motor serverless para ambos); **Auto Scaling** (elasticidade) + **ELB** (distribuição); Lightsail (VPS simplificado); Batch.
- **3.4 Banco de dados** — **RDS Multi-AZ (failover) vs. read replicas (escala de leitura)** — a pegadinha nº 1; **Aurora** (MySQL/PostgreSQL turbinado); **DynamoDB** (NoSQL serverless chave-valor); **ElastiCache** (cache em memória Redis/Memcached); **Redshift** (data warehouse); purpose-built: Neptune (grafos), DocumentDB (documentos/MongoDB), Timestream, QLDB; **DMS** para migrar.
- **3.5 Armazenamento** — classes S3: Standard, **Standard-IA**, One Zone-IA, **Intelligent-Tiering** (padrão imprevisível), Glacier Instant/Flexible/**Deep Archive** (mais barato, recuperação em horas); lifecycle policies; **EBS** (bloco, 1 instância, mesma AZ) vs. **EFS** (arquivo, N instâncias) vs. **instance store** (efêmero); Storage Gateway (híbrido); AWS Backup (backup centralizado); FSx.
- **3.6 Rede** — **VPC**: subnet pública (internet gateway) vs. privada (**NAT gateway** para saída); **Route 53** (DNS + políticas de roteamento); **VPN** (rápida, criptografada, internet) vs. **Direct Connect** (dedicada, consistente, semanas para provisionar); **VPC endpoints** (caminho privado para S3/DynamoDB sem internet); peering; **CloudFront vs. Global Accelerator**.
- **3.7 IA/ML e analytics** — serviços prontos: Rekognition (imagem/vídeo), **Textract** (OCR), **Polly** (texto→fala), **Transcribe** (fala→texto), Translate, Comprehend, Lex, Kendra; **SageMaker AI** (construir modelos próprios) vs. **Bedrock** (foundation models de GenAI via API); Amazon Q; analytics: **Athena** (SQL no S3), **Glue** (catálogo + ETL), **Kinesis** (streaming em tempo real), **QuickSight** (BI/dashboards), EMR (big data), Redshift, OpenSearch.
- **3.8 Outras categorias** — integração: **SQS** (fila, 1 consumidor) vs. **SNS** (pub/sub, N assinantes) vs. **EventBridge** (eventos) vs. **Step Functions** (orquestração); **SES** (e-mail); **Connect** (contact center); **Systems Manager** (operação de frota, patches, Session Manager); usuário final: WorkSpaces (desktop virtual), AppStream; dev tools: família Code*; IoT Core.

**D4 — Billing, Pricing, and Support (12%)**

- **4.1 Modelos de preço** — **On-Demand** (imprevisível) vs. **Reserved/Savings Plans** (estável, 1–3 anos, até ~72%) vs. **Spot** (interrompível, até ~90%) vs. **Dedicated Hosts** (licenças/compliance); Savings Plans = compromisso de USD/hora com flexibilidade (EC2 + Fargate + Lambda); **entrada de dados grátis, saída paga**; Free Tier: always free, 12 meses, trials.
- **4.2 Cobrança e gestão de custos** — **Pricing Calculator** (estimar ANTES) vs. **Cost Explorer** (analisar DEPOIS) vs. **Budgets** (alertar e agir); **cost allocation tags** (rateio por departamento/projeto); **consolidated billing** no Organizations (fatura única + descontos por volume agregado + compartilhamento de RIs/SPs); Cost and Usage Report; alarme de billing como primeira providência de conta nova.
- **4.3 Suporte e recursos técnicos** — planos: **Basic** (só conta e billing) → **Developer** (e-mail, horário comercial) → **Business** (24/7 telefone/chat, produção 1h, Trusted Advisor completo, API) → **Enterprise On-Ramp** (pool de TAMs, 30 min) → **Enterprise** (**TAM dedicado**, crítico 15 min); **Trusted Advisor** (checks de custo, segurança, performance, resiliência, limites); **Marketplace** (software de terceiros na fatura AWS); **re:Post** (comunidade oficial gratuita); Partner Network, Professional Services, IQ, Managed Services, documentação, whitepapers, Prescriptive Guidance.

## Serviços mais cobrados

EC2 (+ Auto Scaling, ELB), Lambda, ECS/EKS/Fargate, Lightsail, Batch, S3 (+ classes e lifecycle), EBS, EFS, FSx, Storage Gateway, Snow Family, AWS Backup, RDS, Aurora, DynamoDB, ElastiCache, Redshift, Neptune, DocumentDB, DMS, VPC (+ subnets, IGW, NAT, security groups, NACLs, endpoints, peering), Route 53, CloudFront, Global Accelerator, Direct Connect, VPN, API Gateway, IAM (+ Identity Center), Organizations (+ SCPs), KMS, Secrets Manager, Certificate Manager, WAF, Shield, GuardDuty, Inspector, Macie, Security Hub, Artifact, Audit Manager, CloudTrail, Config, CloudWatch, Systems Manager, Trusted Advisor, Health Dashboard, CloudFormation, Elastic Beanstalk, Athena, Glue, Kinesis, QuickSight, EMR, OpenSearch, SageMaker AI, Bedrock, Amazon Q, Rekognition, Textract, Polly, Transcribe, Translate, Comprehend, Lex, Kendra, SQS, SNS, EventBridge, Step Functions, SES, Connect, WorkSpaces, Cost Explorer, Budgets, Pricing Calculator, Marketplace.

## Links oficiais

- Página da certificação: https://aws.amazon.com/pt/certification/certified-cloud-practitioner/
- Exam guide oficial (PDF): https://docs.aws.amazon.com/pdfs/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02.pdf
- Plano de preparação em 4 passos (AWS Skill Builder): https://skillbuilder.aws/category/exam-prep/cloud-practitioner-foundational-CLF-C02
- Agendamento (AWS Certification Account): https://aws.amazon.com/pt/certification/

## Material de apoio neste repositório

- [`index.html`](index.html) — simulado interativo com **150 questões inéditas** em PT-BR (termos técnicos em inglês), na proporção oficial 24/30/34/12. Modos: prova completa (65q, 90 min), prova rápida (30q), banco inteiro, treino por domínio, **caderno de erros persistente** e modo estudo com gabarito imediato. O painel final mostra acerto por domínio e por task statement, ordenado por **perda ponderada** (erro × peso do domínio), que é a fila de prioridade de estudo.
- [`flashcards.html`](flashcards.html) — 120 flashcards com repetição espaçada (método de Leitner) cobrindo os quatro domínios.
- [`vespera.html`](vespera.html) — revisão de véspera: 15 tabelas de decisão dos pares confundíveis, checklist auto-avaliável por domínio e os 20 fatos mais cobrados.
- [`glossario.html`](glossario.html) — glossário pesquisável com 100 serviços: o que é, quando é a resposta e com o que a prova o confunde.
- [`labs/`](labs/) — 4 laboratórios práticos no Free Tier (conta segura, S3, EC2 com IAM role, custos e suporte).
- [`plano-de-estudo.md`](plano-de-estudo.md) — cronograma de 3 semanas dia a dia, com versões condensadas para 10 dias, 1 semana e 1 dia.
