# Adicionando um novo token para integração legal

{% hint style="info" %}
Nesta seção, mostramos **como a Aragon pode interagir com uma entidade legal, como uma Series Delaware LLC** . Em nosso exemplo, o Aragon DAO também aproveita o **Gnosis Safe e o EVM-CRISPR** , para mostrar como um DAO existente pode obter acesso às entidades legais.
{% endhint %}

## Introdução <a href="#introduction" id="introduction"></a>

Os invólucros legais são um assunto desafiador e, para fins de clareza, o autor aqui não é um advogado ou presta consultoria jurídica ... o objetivo deste trabalho é mostrar um exemplo de como Aragon pode interagir com uma LLC, no entanto, este exemplo não é para servir como um processo necessariamente útil, e sim como um ponto de partida para a crítica....

## Começo rápido <a href="#quick-start" id="quick-start"></a>

Crie seu DAO começando [aqui](https://client.aragon.org/). Para este exemplo, criei um [DAO de reputação de Aragon](https://documentation.aragon.org/products/aragon-client/how-to-create-a-dao-using-aragon-client/page-1)

![DAO básico com DAO de reputação - usado porque esses tokens devem ser intransferíveis](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.35.12 PM.png>)

## Cuide do seu token <a href="#mint-your-token" id="mint-your-token"></a>

Em seguida, vá para o [EVM CRISPR](https://evm-crispr.blossom.software/#/terminal) , onde você pode inserir algum código para cunhar um novo token.

* Conecte sua carteira
* Limpe o console
* Copie e cole estes comandos

```
connect your-dao-here token-manager voting 
new token "Test Token" TEST token-manager:new
install token-manager:new token:TEST true 0
grant voting token-manager:new MINT_ROLE voting
grant voting token-manager:new BURN_ROLE voting
exec token-manager:new mint @me 100e18
```

* Clique no comando forward e assine a transação em sua carteira
* Após a confirmação da transação, clique em _Go Vote_ e vote no seu DAO

![EVM CRISPR](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.10.14 PM.png>)

![Vote na sua transação EVM CRISPR](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.32.09 PM.png>)

Agora que você criou seus novos tokens, você pode vê-los em sua lista de tokens.

![Este é o nosso DAO](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.11.44 PM.png>)

## Embalagem legal para você Aragon DAO <a href="#legal-wrapper-for-you-aragon-dao" id="legal-wrapper-for-you-aragon-dao"></a>

Agora vamos para a [Gnosis](https://gnosis-safe.io/) onde vamos ligar os pontos.

* Crie um cofre seguro da Gnosis (para mais ajuda, acesse [aqui](https://help.gnosis-safe.io/en/articles/3876461-create-a-safe) ) e deposite alguns fundos em seu cofre para assinar as transações.
* Carregue o aplicativo Otoco
* Dê um nome à sua empresa e escolha entre os DAOs de Delaware, UNA e Wyoming.
* _Aprovar Pagamento_ e _Ativar a Empresa_

Os principais passos são mostrados nas imagens abaixo.

![Criar um cofre na gnosis](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.04.21 PM.png>) ![Carregue o aplicativo Otoco](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.04.31 PM.png>) ![Nomeie sua empresa legal e escolha entre Delaware, UNA e Wyoming DAOs](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.05.46 PM.png>) ![Escolha seu sabor e menta!](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.05.58 PM (1).png>)

Se você vir uma mensagem como "seu contrato inteligente de entidade não é uma carteira", vá para a página " _Carteira de ativos_ " e adicione um proprietário (um endereço de _carteira_ ou um _endereço seguro de Gnosis)_.

![](<../../../.gitbook/assets/Schermata 2022-06-07 alle 14.50.29.png>)

Em seguida, vá para a página _Tokens_ e copie e cole o endereço do seu token (você pode encontrá-lo na [página Organização](https://documentation.aragon.org/products/aragon-client/explore-template-dao/system-setting/organization-setting) em seu DAO).

![Transfira os tokens de seu DAO para sua Otoco LLC](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.11.31 PM.png>)

Agora você tem uma Delaware LLC com tokens cunhados em Aragon!​​

![](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.15.49 PM.png>)

> <mark style="color:purple;">**Você tem uma pergunta?Deixe seus comentários aqui em nosso fórum do Discurso**</mark>** 👇**

{% embed url="https://support.aragon.org/t/aragon-client-legal-wrappers/173" %}
