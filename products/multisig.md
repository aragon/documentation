# Configurando uma carteira MultiSig

{% hint style="info" %}
Nesta seção, veremos como os DAOs do cliente Aragon podem ser gerenciados por uma carteira MultiSig.
{% endhint %}

Aqui vamos usar o [**Gnosis Safe MultiSig**](https://help.gnosis-safe.io/en/articles/3876461-create-a-safe) , no entanto, você pode seguir uma abordagem semelhante para qualquer outra carteira MultiSig que suporte a interação do contrato.

{% hint style="info" %}
Aqui vamos usar o [Gnosis Safe MultiSig](https://gnosis-safe.io/) , no entanto, você pode seguir uma abordagem semelhante para qualquer outra carteira MultiSig que suporte a interação do contrato.
{% endhint %}

## Pré-requisitos <a href="#prerequisites" id="prerequisites"></a>

### Atribua as permissões desejadas no Client DAO ao MultiSig <a href="#assign-the-desired-permissions-in-the-client-dao-to-the-multisig" id="assign-the-desired-permissions-in-the-client-dao-to-the-multisig"></a>

{% hint style="info" %}
Os DAOs Cliente Aragon têm acesso a um sistema de controle, onde cada ação é protegida por um conjunto de registros de permissão. Somente alguém com permissões específicas pode agir. É por isso que precisamos atribuir à carteira MultiSig uma série de permissões que correspondam às ações desejadas. Você pode ler mais sobre isso [aqui](aragon-client/explore-template-dao/system-setting/permissions-setting.md).
{% endhint %}

1\. Siga as etapas abaixo para atribuir permissão a um MultiSig.

2\. Abra seu portal DAO e selecione a guia de _**permissões à esquerda.**_ Aqui você pode examinar as permissões que você tem em seu DAO.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6112718fb55c2b04bf6dce7e/file-DCOHNWElgt.png)

3\. Para adicionar uma nova permissão, pressione o botão _**Nova Permissão**_.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611272116ffe270af2a97627/file-D7HYuaQgTh.png)

4\. Selecione o aplicativo para o qual deseja criar permissão no menu suspenso Aplicativo.

5\. Selecione a qual entidade será atribuída a nova permissão no campo \_ **Atribuir à entidade** \_. Para adicionar o endereço MultiSig selecione _**Custom Address**_ e digite o endereço no campo abaixo.

6\. Selecione uma ação para a qual desejamos conceder permissão. No nosso caso, estamos atribuindo permissão para um MultiSig criar novos votos dentro do nosso DAO.

7\. Pressione _**Adicionar permissão**_ . Isso pode criar um voto dependendo da sua estrutura DAO e de quem é o gerenciador de permissões dessa ação.

8\. Revogue as permissões indesejáveis. Para fazer isso, expanda qualquer permissão e pressione o ícone da lixeira.

{% hint style="danger" %}
Tenha cuidado, pois permissões incorretas podem tornar seu DAO vulnerável ou inacessível.
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611275a7b37d837a3d0e2535/file-AecSpNvGSO.png)

Resultado:

![Permissões Multisig](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d0ef364a230081ba1ce2f/file-aDCnpa7wjo.png)

{% hint style="info" %}
Aqui, atribuímos permissões ao MutliSig para gerenciar pagamentos e alterar os parâmetros de suporte a votação no DAO. No entanto, como continuamos votando como Gerente de Permissões, os membros da comunidade poderão votar para remover essas permissões, revogando efetivamente esse controle MultiSigs sobre o DAO\_.\_
{% endhint %}

### Executando ações <a href="#executing-actions" id="executing-actions"></a>

1\. Acesse o site [Gnosis Safe](https://gnosis-safe.io/) e conecte-se ao DApp deles.

2\. Abra seu cofre.

3\. Pressione o botão _Nova **transação**_ e selecione _**Interação do contrato**_.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d0efb766e8844fc34e2c5/file-ery56Brop6.png)

4\. Forneça o endereço do App Aragon com o qual você gostaria de interagir.

Você pode encontrá-lo na página _**Organizações**_ do seu portal DAO. Veja a seção **\_Aplicativos Aragon instalados\_** lá.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d1014766e8844fc34e2cd/file-8cuqErvYC1.png)

5\. Isso preencherá automaticamente o campo ABI. Exclua o conteúdo que apareceu lá.

6\. Encontre o contrato base do aplicativo Aragon selecionado com o qual você gostaria de interagir.

* Abra o endereço que você usou na etapa 4 no [etherscan](https://etherscan.io/)
* Ir para o _**contrato**_
* Selecione _**Ler contrato**_
* Expandir _**implementação**_
* Abra o endereço que apareceu em _**Implementação**_ no [etherscan](https://etherscan.io/)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d115d766e8844fc34e2ce/file-g3POvBnP7e.png)

7\. Copie a ABI do endereço aberto para o campo da etapa 5.

* Ir para o _**contrato**_
* Selecionar _**código**_
* Localize _**o Contrato ABI**_
* Copie a ABI para o campo de entrada Gnosis Safe ABI

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d12f1766e8844fc34e2d7/file-nCgkCpoDAD.png)

8\. Selecione o método que deseja usar e preencha os parâmetros.

Aqui vamos criar um novo pagamento imediato a partir do aplicativo Finanças. Ele transferirá **0,1 ETH** (representado por um endereço de token 0x0..0) para o endereço _0x424...._

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611277e1766e8844fc34f0ab/file-xlkaRMNQ6n.png)

9\. Pressione _**Revisar**_ e _**Enviar**_ . Depois que um número suficiente de pessoas assinar a transação, você poderá visualizá-la no Etherscan e, uma vez confirmada, deverá entrar em vigor no DAO.

## Possíveis problemas <a href="#possible-issues" id="possible-issues"></a>

{% hint style="warning" %}
Certifique-se de ter as permissões para invocar este método do endereço Gnosis Safe.
{% endhint %}

{% hint style="warning" %}
Se a estimativa de gás falhar e você receber avisos, provavelmente houve um erro nas permissões, nos parâmetros do método ou na ABI e no endereço do contrato. Por favor, faça a configuração novamente.
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611278276ffe270af2a97644/file-rxfkptmQt8.png)

{% hint style="warning" %}
Se você estiver preenchendo números fracionários, adicione 18 zeros ao valor original. Por exemplo, se você quiser invocar o método **imediatoTransfer** que transferirá 10,5 tokens, você terá que inserir 10,5\*10^18 = 10500000000000000000 no campo de valor.
{% endhint %}

{% hint style="warning" %}
Se a ABI não estiver sendo exibida em uma rede (Rinkeby, por exemplo), obtenha a ABI semelhante de outro DAO em uma rede diferente (Ethereum Mainnet, por exemplo).
{% endhint %}

> <mark style="color:purple;">**Você tem uma pergunta?Deixe seus comentários aqui em nosso fórum Aragon**</mark>** 👇**

{% embed url="https://support.aragon.org/t/web3-multisig-wallet/17/2" %}
