# Labs práticos — CLF-C02

Quatro laboratórios curtos para fixar o que a prova cobra, todos dentro do **AWS Free Tier**. A CLF-C02 é uma prova conceitual: você não precisa saber operar a AWS para passar. Mas fazer estas quatro coisas uma vez torna concreto aquilo que, no papel, é decoreba — e é justamente o conteúdo dos domínios com mais peso.

| Lab | O que você faz | Domínios | Tempo | Custo |
|---|---|---|---|---|
| [Lab 01](lab-01-conta-segura.md) | Deixa a conta segura: MFA no root, usuário IAM, alias e budget | D2 · D4 | ~30 min | US$ 0 |
| [Lab 02](lab-02-site-estatico-s3.md) | Publica um site estático no S3 e brinca com classes e lifecycle | D3 | ~30 min | US$ 0 |
| [Lab 03](lab-03-ec2-role-s3.md) | Sobe uma EC2 com security group e acessa o S3 por IAM role, sem chaves | D2 · D3 | ~40 min | US$ 0 |
| [Lab 04](lab-04-cloudwatch-custos.md) | Monta alarme de billing, dashboard e explora Cost Explorer e Trusted Advisor | D2 · D4 | ~30 min | US$ 0 |

## Antes de começar

1. **Faça o Lab 01 primeiro.** Ele configura o alerta de custo que protege todos os outros.
2. **Use a região `us-east-1` (Norte da Virgínia)** nos labs, salvo indicação em contrário: é onde o Free Tier tem mais cobertura e onde vivem os alarmes de billing.
3. **Siga a limpeza no fim de cada lab.** Todo lab termina com uma seção de remoção dos recursos — o Free Tier tem limites, e recurso esquecido vira fatura.
4. **Nunca publique credenciais.** Nenhum lab pede que você grave access keys em arquivo; se algum tutorial da internet pedir, desconfie (e veja o Lab 03 para entender por quê).

> ⚠️ **Aviso de custo.** O Free Tier cobre estes labs se você seguir os passos e a limpeza. Ainda assim, a responsabilidade pela conta é sua: mantenha o budget do Lab 01 ativo e confira o Billing Dashboard depois de praticar.
