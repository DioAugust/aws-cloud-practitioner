# Lab 04 — CloudWatch, Trusted Advisor e as ferramentas de custo

**Domínios:** D4 (4.2 gestão de custos, 4.3 suporte) · D2 (2.2 monitoramento)
**Tempo:** ~30 minutos · **Custo:** US$ 0

## Por que este lab

O D4 vale só 12% da prova, mas é o domínio mais previsível: quase todas as questões saem de cinco telas do console. Este lab é uma visita guiada a essas telas — meia hora aqui costuma valer os 12% inteiros.

## O que a prova cobra disso

- CloudWatch para métricas e alarmes (task 2.2).
- Cost Explorer × Budgets × Pricing Calculator (task 4.2).
- Trusted Advisor e suas categorias de verificação (task 4.3).
- Planos de suporte e o que cada um libera (task 4.3).

## Passos

### 1. Crie um alarme de billing no CloudWatch

1. Primeiro habilite o alerta: **Billing and Cost Management** → **Billing preferences** → marque **Receive AWS Free Tier alerts** e **Receive CloudWatch billing alerts** → salve.
2. Vá para **CloudWatch** e **mude a Region para us-east-1 (N. Virginia)** — as métricas de billing só existem lá, independentemente de onde seus recursos estão.
3. **CloudWatch** → **Alarms** → **All alarms** → **Create alarm** → **Select metric**.
4. **Billing** → **Total Estimated Charge** → moeda **USD** → **Select metric**.
5. Condição: **Greater than** `1` (dólar). Avançar.
6. Notificação: **Create new topic** (SNS), coloque seu e-mail, crie o tópico.
7. Nomeie o alarme (`billing-1-dolar`) e crie.
8. **Confirme a inscrição pelo e-mail que o SNS enviar** — sem isso, o alarme não te avisa.

**Observe duas coisas:** (a) a métrica de billing é **global e mora em us-east-1** — pegadinha clássica; (b) você acabou de usar **SNS** (pub/sub) para entregar a notificação, exatamente o papel que a prova cobra dele.

### 2. Explore o Cost Explorer

1. **Billing and Cost Management** → **Cost Explorer** → **Launch Cost Explorer** (a primeira habilitação leva alguns minutos para popular os dados).
2. Abra o relatório e experimente: agrupe por **Service**, depois por **Region**, depois por **Usage type**.
3. Ative a previsão (**Forecast**) no seletor de período.

**Observe:** ele mostra o que **já foi gasto** e projeta a tendência. Se a pergunta da prova for sobre estimar uma arquitetura que ainda não existe, a resposta é **Pricing Calculator**, não este.

### 3. Faça uma estimativa no Pricing Calculator

1. Abra **https://calculator.aws** (não precisa estar logado).
2. **Create estimate** → adicione um **Amazon EC2**: escolha `t3.medium`, Linux, 730 horas/mês, On-Demand.
3. Anote o valor. Agora mude o modelo de compra para **Reserved Instance, 3 anos, All Upfront** e compare.
4. Adicione um **Amazon S3** com 500 GB Standard e veja o custo somar.

**Observe:** você acabou de ver, em números, por que a prova diz que compromisso maior = desconto maior. E repare que a calculadora separa **armazenamento** de **transferência de dados de saída** — as dimensões de preço que caem na prova.

### 4. Passe pelo Trusted Advisor

1. Console → **Trusted Advisor**.
2. Leia as seis categorias: **Cost optimization, Security, Fault tolerance, Performance, Service limits, Operational excellence**.
3. Veja os checks disponíveis na sua conta e os que aparecem bloqueados.

**Observe:** com o plano **Basic** só há um subconjunto de checks (todos os de limites e alguns de segurança e tolerância a falhas). O conjunto completo exige **Business Support+** ou superior — resposta direta de prova. Repare também se ele acusa "MFA on Root Account" como resolvido: se você fez o Lab 01, deve estar verde.

### 5. Veja os planos de suporte e o Health Dashboard

1. Console → **Support** → **Support plans**.
2. Compare as colunas: canais de atendimento, tempos de resposta, TAM, acesso ao Trusted Advisor completo.
3. Depois abra o **AWS Health Dashboard** (menu do sino/Health): veja a aba de status geral dos serviços e a de eventos da **sua conta**.

**Observe:** a tabela de comparação de planos é literalmente o conteúdo da task 4.3. Fixe: **Business Support+ = primeiro com 24/7 por telefone e Trusted Advisor completo**; **Enterprise Support = TAM designado e 15 minutos para caso crítico**. Se a sua tela ainda mostrar Developer, Business ou Enterprise On-Ramp, são os planos antigos, descontinuados em 1/1/2027.

### 6. Crie um dashboard no CloudWatch (opcional)

1. **CloudWatch** → **Dashboards** → **Create dashboard** (`meu-lab`).
2. Adicione um widget de linha com a métrica de billing (ou de CPU, se ainda tiver a instância do Lab 03).

**Observe:** dashboards do CloudWatch monitoram **infraestrutura**. Dashboard de indicador de negócio para a diretoria é **QuickSight** — outra troca que a prova faz de propósito.

## O que você deve conseguir explicar depois deste lab

- Quando usar Pricing Calculator, Cost Explorer e Budgets (antes, depois, durante).
- Que a métrica de billing vive em us-east-1.
- As seis categorias do Trusted Advisor e o que o plano Basic limita.
- A diferença entre Business Support+ e Enterprise Support.
- CloudWatch (infraestrutura) × QuickSight (negócio).

## Limpeza

Pode manter o alarme de billing e o tópico SNS — eles são gratuitos nas quantidades do Free Tier e protegem sua conta.

Se quiser remover: **CloudWatch → Alarms** → excluir `billing-1-dolar`; **SNS → Topics** → excluir o tópico; **CloudWatch → Dashboards** → excluir `meu-lab`.

> O Cost Explorer, depois de habilitado, pode cobrar por requisições de API paginadas em uso intenso e programático. Navegar pelo console como neste lab não gera custo.
