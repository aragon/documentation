# Home Page（ホーム画面）

{% hint style="info" %}
このセクションでは、DAOのHome Page、メニューとメインセクションを紹介します。
{% endhint %}

## ホーム画面

ホーム画面は、さまざまなアクションのオプションを提供します。

### ホーム画面は、シンプルなランディングページで以下が表示されます

* 作成し、読み込んだ**DAO名**（左上）
* **ウォレットアドレス**と使用中の**ネットワーク**（右上）
* DAOに**プレインストールされているアプリ**で実行できる各種アクション

また、画面左側のメニューを使用して、DAOに現在インストールされている各種**App**を表示することができます。

画像では、**camino.aragonid.eth**（DAO）にToken Manager、Voting、Finance、Agent Appがインストールされ、さらにデフォルトの Permissions、App Center、Organization System Appがインストールされています。

したがって、この DAO では、Assign Tokens（トークンの割り当て）、Vote（投票）、Check Finance（財務状況の確認）、Create Payments（支払いの実行）というアクションを実行することができます。

![Aragon Clientのホーム画面](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d86746c04286364bc8f65bf/file-xfmyJqyDNO.png)

## メニュー機能

画面左上と右上のメニューには、便利機能が用意されています。

なお、これらの機能の多くは、ブラウザのローカルストレージを利用しているため、バックアップを取っていない限り、ブラウザのデータを消去するとデータが失われる可能性があります。

### ネットワーク接続状態表示

ネットワーク接続状態表示（右上にあります）は、Aragon Clientがサポートしているネットワーク（Ethereum、Polygon、Harmony、Rinkeby等）に接続しているかどうかを教えてくれます。

* <mark style="color:red;">赤表示</mark>: Aragon Clientがノードに接続されていません。接続に失敗しています。
* <mark style="color:green;">緑表示</mark>: Aragon Clientはノードにうまく接続され、正常に動作しています。Clientはネットワークに正常に接続されています。

### Enable account（アカウントの有効化）

{% hint style="warning" %}
Aragon Clientを使用するには、まずAragonがあなたのEthereumアカウント（ウォレット）にアクセスすることを許可する必要があります。
{% endhint %}

これにより、Aragon Clientは、署名のためにアカウントにトランザクションを送信し、アドレスやトークン残高など、アカウント情報を読み取ることができるようになります。

{% hint style="info" %}
EthereumアカウントとMetamaskの詳細については、[こちら](../../set-up-metamask/)をご覧ください。
{% endhint %}

まだ接続していない場合は、**Enable account**をクリックし、Metamaskでアクセスリクエストを承認しましょう。

### Favorite organization（DAOのお気に入り登録）

画面左上のDAO名をクリックし、その横にある星アイコンをクリックすると、そのDAOをお気に入りに登録することができます。

そうすれば、お気に入りリストに表示されるようになり、他のDAOに移動しても、**DAO名**をクリックして、簡単に移動できるようになります。

![お気に入りに登録用の星アイコン](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8674e82c7d3a7e9ae174a3/file-nGxht8KRpF.png)

### Activity status（アクティビティ状況）

**アラームベル**のアイコン（右側）をクリックすると、Aragon上で行ったトランザクションのステータスが表示されます。

取引後、**Clear history**ボタンをクリックすると、ステータス履歴を消去することができます。

![トランザクションステータスのリスト](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8674fd2c7d3a7e9ae174a4/file-Bb4iqf37Ue.png)

### Global preferences（グローバル環境設定）

グローバル環境設定を管理するには、**歯車**アイコン（右上）をクリックします。これらの設定はローカルに保存され、あなたが使用するすべてのAragonDAOで使用されます。

## **Custom labels（カスタムラベル）**

Aragonクライアント上で任意のEthereumアドレスをクリックし、そのアドレスを所有する個人またはDAOの名前などのカスタムラベルを付与することができます。ラベルを入力し、保存してください。

![ウォレットアドレスを選択](<../../../.gitbook/assets/Schermata 2022-02-04 alle 15.20.25.png>)

![ラベルを記入して保存](<../../../.gitbook/assets/Schermata 2022-02-04 alle 15.19.17.png>)

これらのラベルは、あなたのグローバル環境設定（右上の歯車アイコン）の「カスタムラベル」タブに表示されます。他のユーザーから提供されたラベルリストをインポートしたり、作成したラベルをエクスポートしたりすることができます。

ラベルが保存されているブラウザのローカルストレージが誤って、または意図的に消去された場合に備えて、時々ラベルをエクスポートしてバックアップを確保しておいてください。

![設定 - グローバル環境設定 - カスタムラベル](<../../../.gitbook/assets/Schermata 2022-02-04 alle 15.26.22.png>)

## **Notifications（通知）**

グローバル環境設定のNotificationsタブで、興味のあるDAOの活動に関するメール通知を選択することができます。

メールアドレスを入力し、メールに記載されているアクティベーションリンクをクリックすると、登録が完了します。

{% hint style="warning" %}
受信フォルダにメールが届いていない場合は、迷惑メールフォルダをご確認ください。
{% endhint %}

DAO内のActionを追加して、その都度通知を受けられるようにもできます。

![](<../../../.gitbook/assets/Schermata 2022-02-04 alle 15.33.22.png>)

![](<../../../.gitbook/assets/Schermata 2022-02-04 alle 15.35.56.png>)

![](../../../.gitbook/assets/file-gVxhisVskv.png)

![](../../../.gitbook/assets/file-zm2zN621Oj.png)

## **Apps（アプリメニュー）**

左側のサイドバーには、DAOにインストールされているすべてのアプリがリストアップされています。アプリにアクセスするには、その名前をクリックします。アプリの詳細については、[こちら](what-are-apps/)を参照してください。

## **System（システムメニュー）**

左側のサイドバーで**System**をクリックすると、デフォルトでテンプレートに付属している項目のシステム設定が表示されます。

* Permissions（権限）
* App Center（アプリセンター）
* Organization（DAO）

{% hint style="info" %}
設定について詳しくは[こちら](system-setting/)をご覧ください。
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d86746c04286364bc8f65bf/file-xfmyJqyDNO.png)

> <mark style="color:purple;">**ご質問はありますか？Aragonフォーラムであなたの考えをお聞かせください**</mark>**👇**

{% embed url="https://support.aragon.org/t/aragon-client-navigate-your-dao-home/23/2" %}
