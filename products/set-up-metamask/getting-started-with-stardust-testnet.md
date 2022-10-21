# Stardustテストネットのはじめ方

{% hint style="info" %}
このセクションでは、Stardustテストネット上でWeb3ウォレットを接続し使用する方法を学びます。
{% endhint %}

## Web3ウォレットをStardustテストネットに接続する

{% hint style="info" %}
Web3ウォレットとして[Metamask（英語のみ）](https://metamask.io)を使用することをお勧めします。&#x20;
{% endhint %}

* ウォレットにログインする
* [https://chainlist.org/（英語のみ）](https://chainlist.org/) サイトにアクセスする
* 検索ボックスで「**stardust**」と入力
* 右上の**connect your wallet**ボタンをクリック
* **add to Metamask** ボタンをクリック

{% hint style="info" %}
Metamaskが正常に接続されている場合、キツネのアイコンが表示されます。
{% endhint %}

![chainlist.orgを使ってMetamaskにチェーンを追加](<../../.gitbook/assets/Schermata 2022-01-26 alle 23.17.31.png>)

## **Stardust**にtest-METISを入金する

### test-METISとは

test-METISトークン（METIS）は、Rinkebyでtest-ETHが使われているのと同様に、Stardustで取引手数料の支払い、ひいてはDAOのデプロイに使われるトークンです。

> 重要：test-METISのシンボルは、Andromedaと同じ「METIS」であることに注意してください。

### test-METISの入手方法

* MetamaskのRinkebyテストネットワークに切り替え
* トークンのインポート

METISトークンをインポートする必要があります。Metamaskの**Import Token**オプションをクリックし、トークンアドレス`0xe552fb52a4f19e44ef5a967632dbc320b0820639`をコピペしてください。その後、あなたのMETISトークン残高が表示されます。

* Rinkeby ETHを取得する

{% hint style="warning" %}
このステップは、トークンを全く持っていない場合、またはMETIS残高が0の新しいアカウントを持っている場合に必要です。Rinkebyのtest-ETHが必要な方は[こちら](getting-started-with-rinkeby-testnet.md)へ。
{% endhint %}

* RinkebyでMETISを取得する

[https://rinkeby-faucet.metis.io/（英語のみ）](https://rinkeby-faucet.metis.io)にアクセスし、アカウントが接続されていることを確認します。

取引を確認し、完了するまで待ちます。すべての指示に従うと、トランザクションが成功し、ウォレットの更新メッセージが表示されます。

* L1（レイヤー1）からL2（レイヤー2）へトークンを転送する

L1からL2へトークンを転送するために[ブリッジ（英語のみ）](https://bridge.metis.io/)を開きます。Metamaskウォレットで**Rinkeby Testnet Network**を選択します。

下の画像のように**depositにMETIS**を選択し、金額を記入します。トランザクションを承認し、待ちます。

Metamaskウォレットで**Metis Stardust Network**を選択し、test-METIS（$METIS）が届いているかを確認します。

![Metisブリッジ](<../../.gitbook/assets/Schermata 2022-01-30 alle 16.20.10 (1).png>)
