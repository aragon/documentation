# Frameウォレットの設定

{% hint style="info" %}
このセクションでは、Frameを使い始め、ハードウェアウォレットを使ってDAOとやりとりする方法について学びます。
{% endhint %}

## **Frameのインストール**

[FrameのWebサイト（英語のみ）](https://frame.sh/)にアクセスし、Frameデスクトップクライアントとブラウザ拡張機能をインストールします。

![Frameのダウンロードページ](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bcfb504286364bc8f9089/file-RW9LeLOUHS.png)

## セットアップ

{% hint style="warning" %}
Frameを使用するには、Metamask、Ledger、Trezorのいずれかのウォレットが必要です。
{% endhint %}

まず、[公式サイト（英語のみ）](https://frame.sh/)からFrameをダウンロードします。その後、メニューバーにFrameが表示されます。

<figure><img src="../.gitbook/assets/frame-intro (1).gif" alt=""><figcaption></figcaption></figure>

## デバイスの設定 <a href="#configure-your-device" id="configure-your-device"></a>

### **Metamask**

以下の手順でMetamaskのウォレットをFrameにインポートしましょう。

* ウォレット上部のアカウントバーにある「**+**」ボタンをクリック
* 右側にポップアップするフレーム内の**add new accounts**をクリック
* **seed phrase**をクリック
* Metamaskからseed phraseをコピペし、**next**をクリック（下図参照）
* これであなたのMetamaskウォレットがFrameウォレットに表示されるはずです

![](<../.gitbook/assets/Screenshot 2022-02-23 at 17.04.36.png>)

### **Ledger**

Ledgerのデバイスでは、ピンを挿入してロックを解除します。次にFrameを開きます。

<figure><img src="../.gitbook/assets/frame-ledger.gif" alt=""><figcaption></figcaption></figure>

### **Trezor**

Trezorデバイスの場合、Frameに直接ピンを挿入してください。これで、使用するネットワークとアカウントを選択できるようになります。

<figure><img src="../.gitbook/assets/frame-trezor.gif" alt=""><figcaption></figcaption></figure>

### **ネットワーク**

目的のネットワークを選択するには、右上の**3つの矢印ボタン**を選択します。これにより、メニューが表示され、一般的な設定を行うことができます。

{% hint style="info" %}
ここでは、「**Connection**」の設定を紹介します。
{% endhint %}

**Rinkeby、Mainnet、Ropsten、Kovan**の中から好きなネットワークを選んでください。

{% hint style="info" %}
このチュートリアルでは、Rinkebyを選択します。
{% endhint %}

<figure><img src="../.gitbook/assets/frame-app-menu.gif" alt=""><figcaption></figcaption></figure>

### **アカウント**

最後のステップは、アカウントの選択です。Configurationボタンをクリックします（LedgerまたはTrezorのアイコンの右側にあります）。アイコンの下にポップアップ表示されるAccountsボタンをクリックします。すると、お使いのデバイスで利用可能なアカウントの選択メニューが表示されます。イーサリアムテストネットの中から1つ選択します。

{% hint style="info" %}
test-ETHをお持ちでない方は、[こちら](https://faucet.rinkeby.io/)や[こちら](https://faucets.chain.link/rinkeby)のRinkeby faucetから入手してください（英語のみ）
{% endhint %}

設定メニューでは、そのアカウントに付与したDappの権限を管理することも可能です。

<figure><img src="../.gitbook/assets/frame-accounts.gif" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
これでFrameの設定は完了し、最初のトランザクションに署名する準備が整いました。
{% endhint %}

> <mark style="color:purple;">**ご質問はありますか？Aragonフォーラムであなたの考えをお聞かせください**</mark>**👇**

{% embed url="https://support.aragon.org/t/web3-frame-wallet/16/2" %}
