# 権限の設定

{% hint style="info" %}
このセクションでは、権限の設定について深く掘り下げています。このページの最後に、専用の動画（英語のみ）があります。
{% endhint %}

## Permissions Appとは？

**Permissions App**は、DAOで設定されている現在のすべての権限を表示し、必要に応じて権限を追加または削除するために使用されます。

Permissions Appで設定された権限は、DAO内のさまざまなアクションを実行するための権限を持つエンティティを定義します。

例えば、どのアカウントでも投票を作成する権限を持つことができますが、DAO内のトークン所有者だけが投票を行う権限を持つことができます。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a697f2c7d3a7e9ae19121/file-gDcISkpUXb.png)

## **Permissions Appを見てみる**

Permissions Appは、DAOに**インストールされているすべてのアプリ**と、そのアプリの**アドレスまたはトークンシンボル**を一覧で表示します。アプリの権限とシステムの権限を変更することができます。

![App permissions](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6a562c7d3a7e9ae1912e/file-0y5pgj1j2k.png)

![System permissions（システム権限）](../../../../.gitbook/assets/file-mnVytX0QZA.png)

### すべてのアプリは以下を持っています

* アプリ上で**実行可能なアクション**リスト
* **他のエンティティがアプリ上で実行する許可を得ているアクション**のリスト
* **アプリが付与されている権限**のリスト

{% hint style="info" %}
下図は、Finance Appが実行できるアクションの一覧（Action）、これらのアクションを実行する権限を持つ他のエンティティ（Assigned to entity）、このエンティティに権限を付与する権限を持つ人（Managed by）を示したものです。
{% endhint %}

![Finance Appの権限の例](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6a7104286364bc8f8145/file-NKD9Oqrl0V.png)

### 例

Finance Appで**Create new payments**を実行する必要がある場合、このアクションはVoting Appでの投票を通過します。これは、Finance Appの**Create new payments**アクションがVoting Appに割り当てられているためです。

### Available permissions（利用可能な権限）

Available permissionsのセクションは、以下が表示されます。

* アプリ上で**どのようなアクション**を実行できるか
* **どのエンティティが**各アクションを**実行する**権限を持っているか
* **どのエンティティが**各アクションを**管理**するか。このエンティティを「マネージャー」と呼びます。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b052c7d3a7e9ae19132/file-68mYNPchqp.png)

**マネージャー**は、**あるアクションを実行する権限を持つエンティティを選択する**権限（Assign Permission）と、**そのアクションのマネージャーを変更する**能力（Manage Role）を持っています。これらの操作は、3つの点の下にあるドロップダウンメニューを使用して行うことができます。

![](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.25.57 (1).png>)

### 権限を割り当てる

3つの点のドロップダウンメニューをクリックし、Assign Permissionを選択します。On Appでアプリを、Assign to Entityでエンティティを、Actionでアクションを選択します。

![権限を割り当てる](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.26.48.png>)

### ロールを管理する

3つの点の上にあるドロップダウンメニューをクリックし、「Manage Role」を選択します。UPDATEの欄にSelect an updateをクリックしてアップデート内容を選びましょう。

![権限の管理](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.37.21.png>)

{% hint style="warning" %}
マネージャが他のエンティティにマネージャの役割を再割り当てすることなく、権限のマネージャとして自身を削除した場合、そのアクションの管理は、ACL Appの**Create permissions**アクションを管理するデフォルトのエンティティで割り当てられます。

以下の例では、このアクションの管理はVoting Appに割り当てられます。
{% endhint %}

![](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.12.59.png>)

{% hint style="danger" %}
アクションのマネージャーが`0x0000000000000000000000000000000000000001`に設定されている場合、新しいマネージャを設定することはできず、そのアクションに与えられた権限は永久にロックされます。
{% endhint %}

### 権限を初期化する

アクションにまだマネージャが与えられていない場合、そのアクションを初期化する必要があります。アクションを初期化するには、アクションを管理したいエンティティのアドレス（Grant permission to）を入力し、アクションの実行権限を付与したいエンティティを選択し、Initialize permissionボタンをクリックして権限を初期化します。

![](../../../../.gitbook/assets/inizialize.png)

### **エンティティごとに見る**

Permissions Appのメインページに戻ると、Browse by entityセクションでDAOで設定されているすべての権限を一目で確認することができます。

ここでは、どのエンティティがDAO内のどのアクションを実行する権限を付与されているのかをすばやく確認できます。

View detailsをクリックすると、そのエンティティの権限のページに移動します。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b6104286364bc8f8153/file-W609vjv1Pi.png)

### **権限を追加する**

アプリ上でアクションを実行する権限をエンティティに与えるには、**Add permission**ボタンをクリックし、エンティティにアクションを実行させたいアプリを選択し、権限を与えたいエンティティを選択し、エンティティに実行権限を与えたいアクションを選択します。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b732c7d3a7e9ae1913a/file-xsxDomUDSy.png)

各アプリには、エンティティに実行権限を付与できる異なるアクションがあります。

各アプリ上でアクションを実行する権限をエンティティに付与することで、以下のことが可能になります。

#### ACL (アクセス制御リスト)

* Create permissions：このACLインスタンスを使用するアプリで、まだ初期化されていない権限を作成する`*`

> `*`これらのアクションは非常に重要です。これらのアクション実行権限を持つエンティティは、DAOをほぼ完全に制御することができます。

#### EVM（イーサリアム仮想マシン）スクリプトレジストリ

* **Add executors**: DAOにエグゼキュータを追加する`*`
* **Enable and disable executors**: エグゼキューターをDAOで有効化および無効化する`*`

> `*` これらのアクションは非常に重要です。これらのアクション実行権限を持つエンティティは、DAOをほぼ完全に制御することができます。

{% hint style="warning" %}
エグゼキュータとは、DAO内のスクリプトを実行するためのインタプリタです。DAO内のすべてのアプリは、DAO内のエグゼキュータを使用して、アプリに送信されるトランザクションの一部であるスクリプトを実行します。各スクリプトには、スクリプトの実行にどのエグゼキュータを使用するかを決定する識別子があります。

たとえば、Voting Appに投票トランザクションが送信されるたびに、アプリはスクリプトを実行し、トランザクション内のスクリプトを実行するためにはエグゼキュータを使用します。[Aragon Developer Portal（英語のみ）](https://hack.aragon.org/)で、エグゼキュータに関する詳細なドキュメントを見ることができます。
{% endhint %}

#### Kernel（カーネル）

* Manage apps: アプリのインストール、アプリのアップグレード、およびDAO内のデフォルトアプリの変更。ACLとEVMスクリプトレジストリは、DAOのデフォルトアプリです。このアクションの実行権限を持っている人は、DAOのデフォルトのVaultコントラクト（トークンの入金を受け付けていないアプリのアドレスにトークンが送金された場合にトークンが送金されるVault）を変更することもできます。`*`

> `*` これらのアクションは非常に重要です。これらのアクション実行権限を持つエンティティは、DAOをほぼ完全に制御することができます。

#### **Tokens（トークン）**

* Mint tokens: 新しいトークンを作成し、指定されたアドレスに転送する
* Issue tokens: 新しいトークンを作成し、DAOのTokens Appに転送して、後で指定したエンティティに割り当てる
* Assign tokens: Tokens Appが保有するトークンを指定されたエンティティに転送する
* Revoke vesting: 指定されたエンティティからトークンのベスティングを取り消す
* Burn tokens: delete tokens held by a tokenholder, reducing the total token supply

#### **Voting（投票）**

* Create new votes: 新規に投票を作成する
* Modify support: Supportパラメータを変更する
* Modify quorum: Minimum Approval（最小定足数）パラメータを変更する

{% hint style="info" %}
**Minimum Approval（最低支持率 ％）**は、ある提案が有効であるとみなされるために、その提案に対する指示率が全トークン供給量の何パーセントでなければならないかを示します。

**例 1**

Minimum Approvalを20%に設定した場合、投票が有効とみなされるには、発行済みトークン数の20%以上が議案を承認するよう投票する必要があります。もし投票が定足数（Quorum）に達しない場合、たとえ反対票よりも賛成票の方が多かったとしても、その提案は否決されます。

**例 2**

を20％に設定し、発行済みトークンの10％がその提案に反対し、15％が支持した場合、その提案はMinimum Approvalに達していないため、不成立となります。
{% endhint %}

{% hint style="info" %}
**Support（支持率）**とは、その議案が可決されるために、支持の合計が上回る必要がある票数の割合のことです。例えば、Supportを51%に設定した場合、その議案が可決されるためには、議案に対する投票数の51%以上が賛成である必要があります。
{% endhint %}

#### Finance（財務）

* Create new payments: Finance Appから別のエンティティへの送金を実行する
* Execute payments: あるエンティティに定期的な支払いを実行する
* Change period duration: 会計期間を秒単位で変更する
* Change budgets: 会計期間内に使用できるトークン量を変更する
* Manage payments: 定期的な支払いの有効化・無効化を切り替える

#### **Vault（金庫）**

* Transfer Vault’s tokens: Vaultアプリが保有するトークンを転送する

{% embed url="https://youtu.be/kMF7Y_KPm-4?t=666" %}

> <mark style="color:purple;">**ご質問はありますか？Aragonフォーラムであなたの考えをお聞かせください**</mark>**👇**

{% embed url="https://support.aragon.org/t/aragon-client-navigate-your-dao-permissions-settings/29/2" %}
