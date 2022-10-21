# Finance App（財務アプリ）

**Finance App**は、DAOの財源管理に使用されます。

## Finance Appの用途

* DAOが保有する各資産の**残高**確認
* 過去の送受金**履歴**の確認
* **新規送金**の実行

![](<../../../../.gitbook/assets/Schermata 2022-02-09 alle 09.52.02.png>)

## **Token Balances（トークン残高）**

Token Balancesでは、DAOが所有する各トークンの残高が表示されます。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62772c7d3a7e9ae190b0/file-eLUV9SRU2y.png)

## **送受金**

このセクションでは、Finance Appを使って過去に行われた送受金の履歴が表示され、送受金日、送金先または送金元のアドレス、送受金に関する参考情報、送受金額などの情報が表示されます。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62832c7d3a7e9ae190b1/file-5lFKotQ4xB.png)

### 送受金履歴は、日付・トークンシンボル・送受金タイプでフィルタリングできます

以下の例を参照してください。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a629604286364bc8f80c5/file-TXwf7noy6I.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62a52c7d3a7e9ae190b8/file-HWRr2HXIlA.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62b62c7d3a7e9ae190b9/file-vWgrnBRGM4.png)

**各送受金について、ドロップダウンメニューをクリックすると、ブロックチェーン上で取引を閲覧するためのリンクが表示され、送受金に関する詳細情報を確認することができます。**

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62c904286364bc8f80cc/file-Puf5b59tKe.png)

**送受金履歴を別のアプリで会計処理するためにエクスポートする必要がある場合は、エクスポートボタンを使ってCSVファイルにエクスポートすることができます。**

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62e604286364bc8f80ce/file-wgYMOA7KJK.png)

## **新規送金**

### 資金の預け入れ

DAOに資金を送るために、Finance Appを使用してデポジットすることができます。

* **New Transfer**ボタンをクリック
* **Deposit**タブを開く
* 入金したいトークンを選択
* 金額を入力
* 参照メモを入力（任意）
* **Submit deposit**ボタンをクリック

{% hint style="info" %}
ETH以外のトークンの場合、入金するために2つのトランザクションが必要になる場合があります。

最初の取引は、Finance Appがあなたの口座残高から入金額を引き出すことを承認し、2番目の取引は、実際の入金のトランザクションです。

これは、Finance Appが、あなたが明示的に許可した以上の資金を口座から引き出すことを防ぐための安全機能です。
{% endhint %}

### **資金の引き出し**

DAOから他のアドレスへの新規送金を作成するために、Finance Appを使用して出金を作成することができます。

* **New Transfer**ボタンをクリック
* **Withdrawal**タブを開く
* 送金を行いたいアドレスを入力
* 送りたいトークンを入力
* 送りたいトークンの金額を入力
* 送金に必要な情報を入力するために、参照メモを追加（任意）

必要情報の入力が完了したら、**Submit transfer**ボタンをクリックして、送金を完了させましょう。（権限がある場合）

![資金の引き出し- Finance App](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a63252c7d3a7e9ae190c4/file-L9njobkDLU.png)

### 新規送金の投票を作成するためトランザクションに署名する

前述のとおり、企業型DAOにおけるすべてのアクションは、トークン保有者による投票が必要です。**Create transaction**をクリックし、Ethereumプロバイダを開いて 送金に関する投票を作成するトランザクションに署名して送信します。

![](https://lh3.googleusercontent.com/UXQwChFz66jOLkHe2GvPoJ\_dTc0dWafDE1aUsgS6GVP47AlL\_RNwSvBTLzZqQDq4M8rxpts6acwsYr2MIO4dRBwjJ6S56h8G1-w9f5c\_FJAK8usZabmT5WbQvR5bqCCXPr-fiGiX)

### 送金に関する投票

送金は、トークン保有者の承認が必要です。送金を承認するために**Yes**票を投じ、DAO内の他のトークン保有者にも同様に投票してもらってください。

![](https://lh3.googleusercontent.com/BYjI\_u7oOJgw6s6\_0IVRxQy\_AAkEHiuc8aQes9a71HZNEknuNwO8FttrpeszbMIXY2j6AV7FfytR-eUi4Y\_eoILA\_WGjHiCz1cYasmUfj\_A0uhmod3bkh1ezWT6IhfP0GmyFmVG7)

### 投票後、トランザクションに署名し、送金が実行される

確認後、送金が実行されます。

![](https://lh4.googleusercontent.com/C86GPoGAqAHhOiN-534hCWcWFeLBfwv3gsnEZ\_aXKwbYeaj67c8nNnvb3\_AK5fEAwPm03a-btdc-mLNkdy\_u-ezuZQG-g7iAvtjfHFoBmZxpYLoukXi7FT88VWifr79\_L21sGjxC)

> <mark style="color:purple;">**ご質問はありますか？Aragonフォーラムであなたの考えをお聞かせください**</mark>**👇**

{% embed url="https://support.aragon.org/t/aragon-client-navigate-your-dao-finance-app/27/2" %}
