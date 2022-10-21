# レピュテーション型テンプレート

{% hint style="info" %}
このセクションでは、Aragon Clientのレピュテーション型テンプレートを使用してDAOを作成する方法を学びます。
{% endhint %}

{% hint style="danger" %}
始める前に[DAOの作り方](./)を読んでおいてください。
{% endhint %}

レピュテーション型DAOとは、レピュテーション（評判）を表すために譲渡不可能なトークンを使用するDAOです。意思決定は、評判の重み付き投票で行われます。

## レピュテーション型DAOを作る

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.02.19.png>)

**View details**をクリックし、利用可能なアプリを確認し、インストールしたい任意のアプリのボックスにチェックを入れます。完了したら、**Use this template**をクリックします。

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.22.29.png>)

## 名前の設定

DAOの名前を決め、**Organization Name**タブに記入します。Aragonは[Ethereum Name Service](https://ens.domains/ja/) (ENS)を使用してDAOに名前を割り当てています。

{% hint style="warning" %}
この名前は、あなたの DAO にアクセスするときに便利です。忘れないようにしましょう!
{% endhint %}

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.23.36.png>)

## Voting Appのパラメータ設定

{% hint style="info" %}
Voting Appのパラメーターは、現在Aragonフロントエンドクライアントから変更することはできません。DAO作成後にVoting Appのパラメータを変更するには、まずこれらのパラメータを変更するための権限を初期化する必要があり、その後[aragonCLI（英語のみ）](https://hack.aragon.org/developers/tools/aragoncli)を使用してパラメータを変更することができます。
{% endhint %}

### 投票の設定

#### 賛成率（Support）

これは、提案が承認されるために**Yes**に投票するために必要なトークンの相対的な割合です。例えば、**Support**を50%に設定すると、提案の投票に使用されたトークンの50%以上が**Yes**に投票しないと可決されないことになります。

#### 最低承認率（Minimum Approval）

提案を承認するために、トークン供給総数のうち何パーセントの**Yes**票が必要かということです。例えば、**Minimum Approval**を20%に設定した場合、議案が可決されるには、トークン供給量の20%以上が**Yes**に投票する必要があります。

#### 投票期間（Voting Duration）

投票期間のことです。例えば、Vote Durationを24時間に設定した場合、トークン保有者は24時間以内に投票に参加することができます。

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.08.36.png>)

## Token Appのパラメータを設定する

トークン名、シンボル、トークン保持者、各トークン保持者のトークン量（残高）を選択します。トークン保有者は、**Add more**ボタンで追加できます。

{% hint style="warning" %}
現在、トークン名とシンボルを変更することはできません。この画面では、トークン所有者を複数人追加しないでください。作成に失敗する可能性があります。DAOの作成後にトークンホルダーを追加することができます。
{% endhint %}

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.25.03.png>)

## DAO情報を確認する

各パネルを開いて、DAOをローンチするために入力した情報が正しいかどうかを確認します。間違いがある場合は、「**back**」ボタンで前の画面に戻り、必要な修正をしましょう。

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.25.54.png>)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.26.03.png>)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.26.14.png>)

## DAOをローンチする

ここで、DAOを作るためのトランザクションに署名する必要があります。ウィンドウが自動的に開かない場合は、Ethereumプロバイダーを開いてください。Ethereumプロバイダーの**承認**ボタンをクリックして、トランザクションに署名します。

トランザクションが完了するまで待ちます。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624d704286364bc8f650d/file-arEtXF8S0j.png)

処理が完了し、DAOがデプロイされるまで、ページを閉じたり更新しないでください。

## Get startedを選択

{% hint style="success" %}
新しいレピュテーション型DAOの準備が整いました。
{% endhint %}

[こちら](../explore-template-dao/)でレピュテーション型DAOについてもっと知りましょう。

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.17.04.png>)

{% hint style="info" %}
DAOが自動的に開かない場合は、[こちら](../../../faq/products/aragon-client/where-is-my-dao.md)をご確認ください。
{% endhint %}

> <mark style="color:purple;">**ご質問はありますか？Aragonフォーラムであなたの考えをお聞かせください**</mark>**👇**

{% embed url="https://support.aragon.org/t/aragon-client-reputation-template/33/2" %}
