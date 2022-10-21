# HarmonyでのDAOの作り方

{% hint style="info" %}
このセクションでは、Harmonyネットワーク上でAragon Clientを使用してDAOをデプロイする方法について説明します。
{% endhint %}

{% hint style="success" %}
[2021年、HarmonyはAragonとペアを組み、client.argon.orgのインターフェイスを使ってDAOプロダクトの提供を開始しました（英語のみ）](https://blog.aragon.org/aragon-client-deployed-on-harmony/)
{% endhint %}

## Harmonyとは？

[Harmony.one（英語のみ）](https://www.harmony.one/)は、幅広い互換性、低コスト、[高いトランザクションレート（最大10M/秒と言われています）（英語のみ）](https://medium.com/@aervinaervin/harmony-10million-transactions-per-second-e8161b7b7f61)を持つL2 Ethereum互換ブロックチェーンです。Effective Proof of Stakeネットワークであり、メインネットの取引コストの数分の一でトランザクションができます。

Ethereum上の資産は[ブリッジ（英語のみ）](https://docs.harmony.one/home/general/bridges/horizon-bridge/bridging-eth-one)を使ってHarmonyに送受金することができます。DAOのデプロイコストを500ドル以上から数セントに引き下げることで、Aragonは何百もの企業や非営利団体がWeb3経済に参入するきっかけになることを期待しています。

## Harmonyテストネットではじめる

* Web3ウォレットをHarmony Testnetに接続し、test-ONEを入金してください。

{% hint style="info" %}
[こちら](../set-up-metamask/getting-started-with-harmony-testnet.md)のガイドを参考にしましょう
{% endhint %}

## Harmonyメインネットではじめる

### Web3ウォレットをHarmonyのネットワークに接続する

Web3ウォレットをHarmonyネットワークに接続し、0.2ONE以上を入金してください。

{% hint style="info" %}
[こちら](../set-up-metamask/getting-started-with-harmony.md)のガイドを参考にしましょう
{% endhint %}

### DAOをデプロイする

1. [Aragon Client](https://client.aragon.org/#/)にアクセスしましょう

![](../../.gitbook/assets/file-WwpvtTSvLt.png)

2\. **Connect account**をクリックし、ウォレットを選択します。下の例では、MetamaskをHarmonyネットワークに接続しています。ダイアログボックスで他のネットワークに接続されていると表示された場合、Harmonyネットワークに切り替えてください。接続されているネットワークは、ウォレット上で選択されたネットワークから自動的に導き出されます。

3\. **Create an Organization**をクリックし、[チュートリアル](how-to-create-a-dao-using-aragon-client/)に従い作成していきましょう。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/61db019ca6a5ee76d8a2e9cd/file-xKHkRPU0F6.png)

> <mark style="color:purple;">**ご質問はありますか？Aragonフォーラムであなたの考えをお聞かせください**</mark>**👇**

{% embed url="https://support.aragon.org/t/aragon-client-create-a-dao-on-harmony/22/3" %}
