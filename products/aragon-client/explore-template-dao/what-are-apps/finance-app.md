# Finance App

O _**aplicativo Finanças**_ é usado para gerenciar os recursos financeiros de uma organização.

## Objetivo do aplicativo de finanças <a href="#purpose-of-the-finance-app" id="purpose-of-the-finance-app"></a>

* Verificar **o saldo** de cada ativo que a organização possui.
* Verificar o **histórico** de transferências anteriores.
* Criando **novas transferências** do aplicativo Finanças.

![](<../../../../.gitbook/assets/Schermata 2022-02-09 alle 09.52.02.png>)

## **Saldo de token** <a href="#token-balance" id="token-balance"></a>

A seção _Saldos de Token_ mostra o saldo de cada token de propriedade da organização.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62772c7d3a7e9ae190b0/file-eLUV9SRU2y.png)

## **Transferências** <a href="#transfers" id="transfers"></a>

A seção mostra um histórico de transferências anteriores que foram feitas usando o aplicativo Finanças, incluindo informações sobre a data da transferência, o endereço da transferência, uma referência com contexto adicional sobre a transferência e o valor da transferência. transferir.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62832c7d3a7e9ae190b1/file-5lFKotQ4xB.png)

### O histórico de transferências pode ser filtrado por data, símbolo de token ou tipo de transferência <a href="#the-transfer-history-can-be-filtered-by-date-token-symbol-or-transfer-type" id="the-transfer-history-can-be-filtered-by-date-token-symbol-or-transfer-type"></a>

Veja os exemplos abaixo.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a629604286364bc8f80c5/file-TXwf7noy6I.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62a52c7d3a7e9ae190b8/file-HWRr2HXIlA.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62b62c7d3a7e9ae190b9/file-vWgrnBRGM4.png)

#### Para cada transferência, você pode clicar no menu suspenso para obter um link para visualizar a transação no blockchain e ver ainda mais detalhes sobre a transferência: <a href="#for-each-transfer-you-can-click-on-the-drop-down-menu-to-get-a-link-to-view-the-transaction-on-the-b" id="for-each-transfer-you-can-click-on-the-drop-down-menu-to-get-a-link-to-view-the-transaction-on-the-b"></a>

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62c904286364bc8f80cc/file-Puf5b59tKe.png)

#### Se você precisar exportar seu histórico de transferências para contabilidade em um aplicativo separado, há um botão de exportação que pode ser usado para exportar um arquivo CSV: <a href="#if-you-need-to-export-your-transfer-history-for-accounting-in-a-separate-app-theres-an-export-button" id="if-you-need-to-export-your-transfer-history-for-accounting-in-a-separate-app-theres-an-export-button"></a>

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62e604286364bc8f80ce/file-wgYMOA7KJK.png)

## **Nova transferência** <a href="#new-transfer" id="new-transfer"></a>

### **Fundos de depósito** <a href="#deposit-funds" id="deposit-funds"></a>

Para enviar fundos para sua organização, você pode criar um depósito usando o aplicativo Finance

* Clique no botão _**Nova Transferência**_ .
* Abra a guia **\_Depósito\_** .
* Selecione o token que deseja depositar.
* Insira a quantidade.
* Insira uma nota de referência (opcional).
* Em seguida, clique no botão _**Enviar** depósito_ .

{% hint style="info" %}
Para tokens não-ETH, duas transações podem ser necessárias para fazer um depósito.

A primeira transação aprova o aplicativo Finanças para extrair o valor do depósito do saldo da sua conta e a segunda transação é a transação de depósito real.

Este é um recurso de segurança para evitar que o aplicativo Finance extraia mais fundos de sua conta do que você autorizou explicitamente.
{% endhint %}

### **Saque de fundos** <a href="#withdrawal-funds" id="withdrawal-funds"></a>

Para criar uma nova transferência da sua organização para outro endereço, você pode criar uma retirada usando o aplicativo Finanças

* Clique no botão _**Nova Transferência**_ .
* Abra a guia _**Retirada**_ \*\* \*\*.
* Digite o endereço para o qual deseja fazer a transferência.
* Digite o token que você deseja enviar.
* Insira a quantidade de tokens que deseja enviar.
* Adicione (opcionalmente) uma nota de referência para fornecer mais contexto para a transferência.

Depois de preencher todas essas informações, você pode clicar no botão _**Enviar transferência**_ para concluir a ação, se tiver permissão.

![Saque de fundos - Aplicativo Financeiro](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a63252c7d3a7e9ae190c4/file-L9njobkDLU.png)

### **Assine a transação para criar o voto Nova Transferência** <a href="#sign-the-transaction-to-create-the-new-transfer-vote" id="sign-the-transaction-to-create-the-new-transfer-vote"></a>

Conforme mencionado anteriormente, todas as ações na organização da Empresa exigem um voto dos detentores de tokens. Clique _**em Criar transação**_ e abra seu provedor Ethereum para assinar e enviar a transação que cria o voto de Nova Transferência.

![](https://lh3.googleusercontent.com/UXQwChFz66jOLkHe2GvPoJ\_dTc0dWafDE1aUsgS6GVP47AlL\_RNwSvBTLzZqQDq4M8rxpts6acwsYr2MIO4dRBwjJ6S56h8G1-w9f5c\_FJAK8usZabmT5WbQvR5bqCCXPr-fiGiX)

### **Vote na transferência** <a href="#vote-on-the-transfer" id="vote-on-the-transfer"></a>

A transferência deve ser aprovada pelos detentores do token. Dê um voto _**Sim**_ para aprovar a transferência e faça com que os outros detentores de token na organização votem também.

![](https://lh3.googleusercontent.com/BYjI\_u7oOJgw6s6\_0IVRxQy\_AAkEHiuc8aQes9a71HZNEknuNwO8FttrpeszbMIXY2j6AV7FfytR-eUi4Y\_eoILA\_WGjHiCz1cYasmUfj\_A0uhmod3bkh1ezWT6IhfP0GmyFmVG7)

### **A transação de voto é assinada e enviada para aprovar a transferência** <a href="#the-vote-transaction-is-signed-and-sent-to-approve-the-transfer" id="the-vote-transaction-is-signed-and-sent-to-approve-the-transfer"></a>

Após a confirmação, a transferência será executada.

![](https://lh4.googleusercontent.com/C86GPoGAqAHhOiN-534hCWcWFeLBfwv3gsnEZ\_aXKwbYeaj67c8nNnvb3\_AK5fEAwPm03a-btdc-mLNkdy\_u-ezuZQG-g7iAvtjfHFoBmZxpYLoukXi7FT88VWifr79\_L21sGjxC)

> <mark style="color:purple;">**Você tem uma pergunta?Deixe seus comentários aqui em nosso fórum do Discurso**</mark>** 👇**

{% embed url="https://support.aragon.org/t/aragon-client-navigate-your-dao-finance-app/27/2" %}
