# 法規制に適合したトークンの発行

{% hint style="info" %}
このセクションでは、**AragonがSeries Delaware LLCのような法人組織とどのように関わる可能性があるか**を示します。この例では、Aragon DAOは**Gnosis SafeとEVM-CRISPR**も活用し、DAOがどのように法人組織になることができるかを示しています。
{% endhint %}

## 導入

リーガルラッパーは難しいテーマです。はっきりさせておくと、筆者は弁護士でもなければこれは法的なアドバイスではありません。この記事の目的は、AragonとLLCの関係の一例を示すことですが、この例は必ずしも役立つ手順ではなく、むしろ批判の起点となるかもしれません。

## クイックスタート

[こちら（英語のみ）](https://client.aragon.org/)からDAOを作成します。この例では、 [レピュテーション型DAO](../how-to-create-a-dao-using-aragon-client/page-1.md)を作成しました。\


![基本的なレピュテーション型DAO（トークンは譲渡不可能）](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.35.12 PM.png>)

## トークンをミントする

[EVM CRISPR（英語のみ）](https://evm-crispr.blossom.software/#/terminal)で、新しいトークンをミントするためのコードを入力しましょう。

* ウォレットを接続する
* コンソールをクリアする
* 以下のコマンドをコピーして貼り付ける

```
connect your-dao-here token-manager voting 
new token "Test Token" TEST token-manager:new
install token-manager:new token:TEST true 0
grant voting token-manager:new MINT_ROLE voting
grant voting token-manager:new BURN_ROLE voting
exec token-manager:new mint @me 100e18
```

* Forward\~をクリックし、ウォレット上でトランザクションに署名する
* トランザクションが完了したら、Go Voteをクリックし、DAOに投票する

![EVM CRISPR](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.10.14 PM.png>)

![EVM CRISPRのトランザクションに投票する](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.32.09 PM.png>)

新しいトークンの作成が完了したら、トークン一覧で確認することができます。\


![トークンの確認](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.11.44 PM.png>)

## DAOのリーガルラッパー

次は[Gnosis（英語のみ）](https://gnosis-safe.io/)を開きます

* Gnosisのvaultを作成し（詳しくは[こちら（英語のみ）](https://help.gnosis-safe.io/en/articles/3876461-creating-a-safe-on-a-web-browser)をご覧ください）、トランザクションに必要な資金をvaultに入金する
* Otoco Appを起動する
* 会社名を決め、Delaware、UNA、Wyoming DAOの中から1つ選択する
* 支払いを承認し、会社を設立する

主な手順は以下の画像の通りです。

![gnosisでvaultを作成](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.04.21 PM.png>) ![Otoco Appを起動](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.04.31 PM.png>) ![会社名を決め、Delaware、UNA、Wyoming DAOの中から1つ選択](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.05.46 PM (1).png>) ![会社を設立する](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.05.58 PM.png>)

もし、「your entity smart contract is not a wallet（あなたのエンティティースマートコントラクトはウォレットではありません）」というようなメッセージが表示されたら、Asset walletページで、オーナー（ウォレットアドレスまたはGnosisセーフアドレス）を追加してください。

![](<../../../.gitbook/assets/Schermata 2022-06-07 alle 14.50.29.png>)

次に、トークンのページで、あなたのトークンアドレスをコピペします（DAOの[組織ページ](../explore-template-dao/system-setting/organization-setting.md)にあります）。

![DAOからOtoco LLCにトークンを転送](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.11.31 PM.png>)

これで、Aragonでミントしたトークンを持つDelaware LLCが誕生しました！

![](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.15.49 PM.png>)

> <mark style="color:purple;">**ご質問はありますか？Aragonフォーラムであなたの考えをお聞かせください**</mark>**👇**

{% embed url="https://support.aragon.org/t/aragon-client-legal-wrappers/173" %}
