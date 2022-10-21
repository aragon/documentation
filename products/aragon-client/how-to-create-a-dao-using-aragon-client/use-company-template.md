# 企業型テンプレート

{% hint style="info" %}
このセクションでは、Aragon Clientの企業型テンプレートを使用してDAOを作成する方法を学びます。
{% endhint %}

{% hint style="danger" %}
始める前に[DAOの作り方](./)を読んでおいてください。
{% endhint %}

企業型DAOとは、出資のために、譲渡可能なトークンを使用するDAOです。意思決定は、1トークンが1票に相当するトークンによる加重投票で行われます。

## 企業型DAOを作る

![テンプレートの選択](<../../../.gitbook/assets/Schermata 2022-02-04 alle 18.41.40.png>)

**View details**をクリックし、利用可能なアプリを確認し、インストールしたい任意のアプリのボックスにチェックを入れます。完了したら、**Use this template**をクリックします。

![企業型テンプレート](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d86242f04286364bc8f6507/file-QeXiahqUec.png)

## 名前の設定

DAOの名前を決め、**Organization Name**タブに記入します。Aragonは[Ethereum Name Service](https://ens.domains/ja/) (ENS)を使用してDAOに名前を割り当てています。

{% hint style="warning" %}
この名前は、あなたのDAOにアクセスするときに便利です。忘れないようにしましょう!
{% endhint %}

![DAOの名前を決定](<../../../.gitbook/assets/Schermata 2022-02-04 alle 18.52.45.png>)

## Voting Appのパラメータ設定

{% hint style="info" %}
Voting Appのパラメーターは、現在Aragonフロントエンドクライアントから変更することはできません。DAO作成後にVoting Appのパラメータを変更するには、まずこれらのパラメータを変更するための権限を初期化する必要があります。その後[aragonCLI（英語のみ）](https://hack.aragon.org/developers/tools/aragoncli)を使用してパラメータを変更することができます。
{% endhint %}

### 投票の設定

#### 賛成率（Support）

これは、提案が承認されるために**Yes**に投票するために必要なトークンの相対的な割合です。例えば、**Support**を50%に設定すると、提案の投票に使用されたトークンの50%以上が**Yes**に投票しないと可決されないことになります。

#### 最低承認率（Minimum Approval）

提案を承認するために、トークン供給総数のうち何パーセントの**Yes**票が必要かということです。例えば、**Minimum Approval**を20%に設定した場合、議案が可決されるには、トークン供給量の20%以上が**Yes**に投票する必要があります。

#### 投票期間（Voting Duration）

投票期間のことです。例えば、Vote Durationを24時間に設定した場合、トークン保有者は24時間以内に投票に参加することができます。

![Votingの設定](<../../../.gitbook/assets/Schermata 2022-02-04 alle 19.01.42.png>)

## Token Appのパラメータを設定する

トークン名、シンボル、トークン保持者、各トークン保持者のトークン量（残高）を選択します。トークン保有者は、**Add more**ボタンで追加できます。

{% hint style="warning" %}
現在、トークン名とシンボルを変更することはできません。この画面では、トークン所有者を複数人追加しないでください。作成が失敗する可能性があります。DAOの作成後にトークンホルダーを追加することができます。
{% endhint %}

![Token Appの設定](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624862c7d3a7e9ae173e4/file-wSKI8WfAzK.png)

## DAO情報を確認する

各パネルを開いて、DAOをローンチするために入力した情報が正しいかどうかを確認します。間違いがある場合は、「**back**」ボタンで前の画面に戻り、必要な修正をしましょう。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624af04286364bc8f650a/file-QLxk1Q0FZj.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624b704286364bc8f650b/file-IsP1SOVaHO.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624bf2c7d3a7e9ae173e5/file-Qn8KEkg3If.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624c604286364bc8f650c/file-Fqvyo6L3Kz.png)

## DAOをローンチする

ここで、DAOを作るためのトランザクションに署名する必要があります。ウィンドウが自動的に開かない場合は、Ethereumプロバイダーを開いてください。Ethereumプロバイダーの**承認**ボタンをクリックして、トランザクションに署名しましょう。

トランザクションが完了するまで待ちます。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624d704286364bc8f650d/file-arEtXF8S0j.png)

処理が完了し、DAOがデプロイされるまで、ページを閉じたり更新しないでください。

## Get startedを選択

{% hint style="success" %}
新しいレ企業型DAOの準備が整いました。
{% endhint %}

[こちら](../explore-template-dao/)で企業型DAOについてもっと知りましょう。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624ee04286364bc8f650e/file-a4bAYgLmxU.png)

{% hint style="info" %}
DAOが自動的に開かない場合は、[こちら](../../../faq/products/aragon-client/where-is-my-dao.md)をご確認ください。
{% endhint %}

> <mark style="color:purple;">**ご質問はありますか？Aragonフォーラムであなたの考えをお聞かせください**</mark>**👇**

{% embed url="https://support.aragon.org/t/aragon-client-company-template/32/2" %}
