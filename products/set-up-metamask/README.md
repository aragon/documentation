# Metamaskの設定

{% hint style="info" %}
このセクションでは、Metamaskウォレットの設定方法と、異なるブロックチェーンでの設定方法について説明します。
{% endhint %}

{% hint style="success" %}
**Web3ウォレットとして**[**Metamask（英語のみ）**](https://metamask.io)**を使用することをお勧めします。**&#x20;

Metamaskは、通常のウェブサイトからイーサリアム（および他のブロックチェーン）の取引を行うことができるブラウザプラグインです。
{% endhint %}

{% hint style="warning" %}
このガイドでは、Chromeの拡張機能に焦点を当てます。しかし、このプロセスはすべてのブラウザで同様です。
{% endhint %}

## はじめに <a href="#getting-started" id="getting-started"></a>

Aragon**クライアントDAO**を作成するためには、いずれかのテストネットワークまたはメインネットワークに接続する必要があります。以下のブロックチェーンから選択することができます。

* [Ethereum メインネット](getting-started-with-ethereum.md)
* [Rinkeby テストネット](getting-started-with-rinkeby-testnet.md)
* [Polygon](getting-started-with-polygon.md)
* [Andromeda](getting-started-with-metis-andromeda.md)
* [Mumbai テストネット](getting-started-with-mumbai-testnet.md)
* [Harmony](getting-started-with-harmony.md)
* [Harmony テストネット](getting-started-with-harmony-testnet.md)
* [Stardust テストネット](getting-started-with-metis-andromeda.md)
* [BSC テストネット](getting-started-with-bsc-testnet.md)

コマンドラインを使用して直接 DAO を作成し、操作することもできます（この場合、ちょっとしたプログラミングスキルが必要です）。また、いずれかのテスト/メインネットに接続する必要があります（利用できるネットワークは、上のリストと同じです）。

Aragon **Govern DAO**を作成・使用するためには、1つのテスト/メインネットに接続する必要があります。以下のブロックチェーンから選択することができます。

* [Ethereum メインネット](getting-started-with-ethereum.md)
* [Rinkeby テストネット](getting-started-with-rinkeby-testnet.md)

Metamaskを設定し、理解することから始めましょう。

## Metamaskの設定：はじめに <a href="#getting-started" id="getting-started"></a>

* [Metamaskのホームページ（英語のみ）](https://metamask.io/)にアクセスし、ブラウザ拡張機能をダウンロードしてください。ダウンロードが完了すると、自動的にウェルカムページに遷移します。

<figure><img src="../../.gitbook/assets/m-0.png" alt=""><figcaption><p>Metamaskウェルカムページ 説明に従って操作しましょう</p></figcaption></figure>

* 指示に従ってMetamaskアカウントを設定しましょう

{% hint style="info" %}
メタマスクの設定方法について、詳しくは[こちら（英語のみ）](https://wiki.polygon.technology/docs/develop/metamask/hello/)をご覧ください。
{% endhint %}

* Metamaskのセットアップが完了すると、新しく作成されたEthereumウォレットに遷移するはずです。

![Metamaskのアカウント](<../../.gitbook/assets/mm account (1).png>)

{% hint style="success" %}
ここまできたら、初期設定完了です。おめでとうございます🎉
{% endhint %}

## アカウントのアドレス <a href="#account-address" id="account-address"></a>

アカウント名（ここではAccount1）の下にある「3つの点」のボタンをクリックすると、アカウントアドレスを表示したポップアップが現れます。以下の例のように表示されるはずです。

> **0x931D387731bBbC988B312206c74F77D004D6B84b**

{% hint style="success" %}
これは、あなたの公開アドレス（または公開鍵）です。これを他の人と共有することで、ETHや他のトークンを受け取ることができます。
{% endhint %}

## ネットワークの選択 <a href="#selected-networks" id="selected-networks"></a>

右上に、**Main Ethereum Network**が選択されたドロップダウンメニューが表示されます。この選択では、イーサリアムチェーンと直接やりとりすることができます。

**クリックすると、他のネットワークの選択が表示されます。**

<figure><img src="../../.gitbook/assets/m-2.png" alt=""><figcaption><p>ネットワーク選択のドロップダウンメニュー</p></figcaption></figure>

## なぜ他のネットワークを選択する必要がある？

メインのイーサリアムネットワークでプロジェクト（またはDapp）を立ち上げる前に、イーサリアムのテストネットや他のメインネット（PolygonやHarmonyなど）にバージョンをデプロイして、取引手数料のコストを節約することが一般的です。

### テストネットを利用するメリット

テストネットのETHを使用する主な理由は、実際のお金を支払うことなく入手できることです。これにより、開発者やコミュニティは、実際にお金を使う前の段階で不具合を解決することができます。

#### 以下の４種類のテストネットがあります。

* Ropsten
* Kovan
* Rinkeby
* Goerli

{% hint style="warning" %}
この段階では、これらのネットワークの違いについて心配する必要はありません。知っておくべきことは、これらはイーサリアムをシミュレートし、実際のお金を支払うことなく使用できることです。
{% endhint %}

### プライベートネットワークの利用

最後に、**Localhost 8545**を選択することで、プライベートなイーサリアムネットワークとやりとりすることも可能です。この場合のプライベートとは、より安全であるという意味ではありません。ただ、ノードがメイン/テストネットのノードに接続されていないことを意味します。これは**迅速な実験とテストに最適**です。

{% hint style="warning" %}
異なるネットワークを使用したい場合は、ウォレットを設定し、ガス代を支払うために十分な資金をウォレットに準備する必要があることを忘れないでください。この方法については、次のセクションで説明します。
{% endhint %}

> <mark style="color:purple;">**ご質問はありますか？Aragonフォーラムであなたの考えをお聞かせください**</mark>**👇**

{% embed url="https://support.aragon.org/t/web-3-metamask-wallet/15/2" %}
