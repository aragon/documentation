# Alerta de transação da carteira Metamask

Quando o _Aragon Client_ pede que você assine e envie várias transações para o blockchain Ethereum, seu provedor Ethereum (por exemplo, Metamask) pode avisá-lo de que as transações subsequentes falharão:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5e31cc5804286364bc949451/file-vZiPEIBtx3.png)

Isso se deve ao fato de que o blockchain Ethereum ainda não fue atualizado desde suas transações iniciais, o que torna impossível para o provedor Ethereum determinar se as transações subsequentes serão bem-sucedidas ou falharão.

Você deve poder ignorar esses avisos com segurança, pois o _Aragon Client_ já terá pré-calculado o estado necessário para garantir que suas transações sejam bem-sucedidas.
