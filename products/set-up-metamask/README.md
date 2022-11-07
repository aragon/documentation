# Configurar uma carteira Metamask

{% hint style="info" %}
Nesta seção, você aprenderá **como configurar uma carteira **_**Metamask**_ e como configurá-la em diferentes _blockchains_. Você pode assistir ao vídeo ou ler o texto abaixo do vídeo.
{% endhint %}

{% hint style="success" %}
**Recomendamos usar o **_****_ [_**Metamask**_](https://metamask.io/) _****_** como sua carteira **_**Web3**_**.**

_Metamask_ é um _plugin_ de navegador que permite fazer transações no _Ethereum_ (e outras _blockchains_) através de sitios web regulares. \*\*\*\*
{% endhint %}

{% hint style="warning" %}
Este guia se concentra em uma extensão do _Chrome_. De qualquer forma, o processo é semelhante para todos os navegadores.
{% endhint %}

## Começar <a href="#getting-started" id="getting-started"></a>

Para criar e usar uma **DAO com **_**Aragon Client**_** ** , você precisa se conectar a um teste ou a uma rede principal. Você pode escolher entre diferentes _blockchains_:

* [Ethereum Mainnet](getting-started-with-ethereum.md)
* [Goerli Testnet](https://documentation.aragon.org/products/set-up-metamask/getting-started-with-rinkeby-testnet)
* [Polygon](getting-started-with-polygon.md)
* Andromeda
* [Mumbai Testnet](getting-started-with-mumbai-testnet.md)
* [Harmony](getting-started-with-harmony.md)
* [Harmony Testnet](getting-started-with-harmony-testnet.md)
* [Stardust testnet](getting-started-with-metis-andromeda.md)
* [BSC Testnet](getting-started-with-bsc-testnet.md)

Você também pode criar e interagir com uma DAO diretamente usando a linha de comando (neste caso é necessário um pouco de habilidade de desenvolvimento), também neste caso você precisa se conectar a um teste ou uma rede principal (as redes disponíveis são as mesmas no lista superior). Para criar ou usar uma **DAO com **_**Aragon Govern**_, você precisa se conectar a um teste ou a uma rede principal. Você pode escolher entre estes _blockchains_:

* [Ethereum Mainnet](getting-started-with-ethereum.md)
* [Goerli Testnet](https://documentation.aragon.org/products/set-up-metamask/getting-started-with-rinkeby-testnet)

Vamos começar a configurar e entender os principais recursos da carteira metamask e então você pode seguir para a escolha de sua rede preferida.

## Começar <a href="#getting-started-1" id="getting-started-1"></a>

* Visite a [página inicial do _Metamask_](https://metamask.io/) e baixe a extensão do navegador. Após ter baixado, você deve ser direcionado automaticamente para uma página de boas-vindas.

<figure><img src="../../.gitbook/assets/m-0.png" alt=""><figcaption><p>Página de boas-vindas da Metamask. Siga as instruções cuidadosamente.</p></figcaption></figure>

* Configure sua conta Metamask de acordo.

{% hint style="info" %}
Se você precisar de mais informações sobre como criar seu próprio perfil Metamask, você pode ir [aqui](https://docs.polygon.technology/docs/develop/metamask/hello/) .
{% endhint %}

* Quando a configuração do Metamask estiver concluída, você deverá ser redirecionado para sua carteira Ethereum recém-criada.

![Conta de Metamask](<../../.gitbook/assets/mm account (1).png>)

{% hint style="success" %}
Se você chegou até aqui, parabéns 🎉.
{% endhint %}

## Endereço da conta <a href="#account-address" id="account-address"></a>

Se você clicar no botão dos **"três pontos"** abaixo do nome da sua conta - no nosso caso, _Conta 1_ - um pop-up aparecerá com o endereço da sua conta. Deve ser parecido ao exemplo abaixo:

> **0x931D387731bBbC988B312206c74F77D004D6B84b**

{% hint style="success" %}
Este é o seu endereço público (ou chave pública). Você pode compartilhar isso com outras pessoas para receber ETH ou outros tokens.
{% endhint %}

## Redes selecionadas <a href="#selected-networks" id="selected-networks"></a>

No canto superior direito, você deve ver um menu suspenso com a _**Main Ethereum Network**_ selecionada. Com esta opção, você pode interagir diretamente com o blockchain principal do _Ethereum_.

#### Se você clicar nele, uma seleção de outras redes será mostrada. <a href="#if-you-click-on-it-a-selection-of-other-networks-will-be-shown." id="if-you-click-on-it-a-selection-of-other-networks-will-be-shown."></a>

<figure><img src="../../.gitbook/assets/m-2.png" alt=""><figcaption><p>Menu suspenso para selecionar a rede.</p></figcaption></figure>



## Por que você deve selecionar outras redes? <a href="#why-should-you-select-other-networks" id="why-should-you-select-other-networks"></a>

Antes de lançar um projeto (ou _Dapp_) na rede principal _Ethereum_, é uma boa prática implantar uma versão em uma rede de teste _Ethereum_ ou em outras redes principais (como _Polygon_ ou _Harmony_) para economizar custos de taxas de transação.

### Os benefícios de usar uma rede de teste <a href="#the-benefits-of-using-a-testnet" id="the-benefits-of-using-a-testnet"></a>

A principal razão para usar um _testnet_ ETH é que ele pode ser obtido sem ter que pagar dinheiro real. Isso dá aos desenvolvedores e à comunidade a chance de resolver quaisquer problemas antes que dinheiro real esteja envolvido.

#### Existem dois redes de teste: <a href="#there-are-four-testnets" id="there-are-four-testnets"></a>

* Goerli
* Sepolia

{% hint style="warning" %}
**Nesta fase, não se preocupe com as diferenças entre essas redes.** Tudo o que você precisa saber é que eles simulam o Ethereum e podem ser usados ​​sem ter que pagar dinheiro real.
{% endhint %}

### Usando redes privadas <a href="#using-private-networks" id="using-private-networks"></a>

Por fim, você também pode interagir com redes privadas Ethereum selecionando **Localhost 8545**. Privado neste caso não significa mais seguro. Significa apenas que os nós não estão conectados aos nós da rede principal ou de teste. **Perfeito para experimentação e testes rápidos.**

{% hint style="warning" %}
Lembre-se de que, se você quiser usar redes diferentes, precisará configurar sua carteira e carregar sua carteira com fundos suficientes para pagar as taxas de transação. Explicaremos como fazer isso nas próximas seções.
{% endhint %}

> <mark style="color:purple;">**Você tem uma pergunta? Deixe seus comentários aqui no nosso fórum Discourse**</mark>** 👇**

{% embed url="https://support.aragon.org/t/web-3-metamask-wallet/15/2" %}
