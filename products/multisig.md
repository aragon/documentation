# Configurando uma carteira MultiSig

{% hint style="info" %}
Nesta seção, veremos como as DAOs do _Aragon Client_ podem ser geridas por uma carteira MultiSig.
{% endhint %}

{% hint style="warning" %}
Aqui vamos usar o [Gnosis Safe MultiSig](https://gnosis-safe.io/), no entanto, você pode seguir uma abordagem parecida para qualquer outra carteira MultiSig que suporte a interação do contrato.
{% endhint %}

## Configurar as permissões necessárias <a href="#prerequisites" id="prerequisites"></a>

{% hint style="info" %}
As DAOs do _Aragon Client_ têm acesso a um sistema de controle, onde cada ação é protegida por um conjunto de registros de permissão. Somente alguém com permissões específicas pode agir.&#x20;

\
**É por isso que precisamos atribuir à carteira MultiSig uma série de permissões que correspondam às ações desejadas.**&#x20;

\
Você pode ler mais sobre isso [aqui](aragon-client/explore-template-dao/system-setting/permissions-setting.md).
{% endhint %}

****\
****Neste exemplo, uma DAO do _Aragon Client_ tem um saldo de tokens ETH armazenados em seu Cofre (_Vault_) e você deseja iniciar um pagamento para compensar um colaborador DAO por seu trabalho. **Mostraremos como iniciar uma retirada de parte dos ETH para o Colaborador**.\
****\
****Comece abrindo a sua DAO do Aragon Client, você deve ver um painel parecido como na imagem abaixo. Clique no menu à esquerda em 'Permissões':

<figure><img src="../.gitbook/assets/1 (1).png" alt=""><figcaption></figcaption></figure>

Queremos adicionar novas permissões para o seu MultiSig, então clique nesta tela em 'Nova permissão'

<figure><img src="../.gitbook/assets/2.png" alt=""><figcaption></figcaption></figure>

Você deve ver a seguinte janela lateral aparecer. Clique em 'Selecionar um aplicativo':

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Para este exemplo, queremos iniciar uma retirada de ETH pelo MultiSig. Isso geralmente é feito no aplicativo 'Finanças' da DAO, então selecione '_Finance_' aqui e clique em 'Selecionar uma entidade':

<figure><img src="../.gitbook/assets/a.png" alt=""><figcaption></figcaption></figure>

Como precisamos adicionar o endereço do seu MultiSig, clique aqui em '_Custom Address_...':

<figure><img src="../.gitbook/assets/aa.png" alt=""><figcaption></figcaption></figure>

Agora vá para o seu Gnosis Safe, copie seu endereço e cole o endereço do seu MultiSig na caixa 'GRANT PERMISSION TO'. Em seguida, clique em 'Selecionar uma ação':

<figure><img src="../.gitbook/assets/aaaa.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Não se esqueça de remover as letras da frente do endereço Gnosis Safe, **eth:** ou **gor:** ou diferente dependendo da rede que você usa! Caso contrário não vai funcionar.. \
\
O endereço deve começar com: **0x**
{% endhint %}

Neste caso queremos iniciar um novo pagamento, então clique em 'Criar novos pagamentos':

<figure><img src="../.gitbook/assets/b.png" alt=""><figcaption></figcaption></figure>

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
