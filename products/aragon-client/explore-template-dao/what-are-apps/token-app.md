# Tokens App（トークンアプリ）

Tokens Appは、**新しいトークンをミント**して、自分自身や他のエンティティに**割り当てる**ために使用されます。Token Appでミントされたトークンは、トークンの保有者に**投票権を付与**します。

EVM Crisprで新しいトークンをミントする手順については、[こちら（英語のみ）](https://docs.evmcrispr.blossom.software/aragonOS/token-manager/)をご覧ください。

{% hint style="info" %}
#### ミントとは？

ミントとは、新しいトークンを作成することです。トークンは好きなだけ作成できます（DAOのメンバーが同意している限り）。つまり、新しいトークンを新規ユーザーのためにミントするだけで、DAOに新しいユーザーを好きなだけ追加できます。以下では、新しいトークンをDAOに追加する方法を説明します。
{% endhint %}

## エンティティにトークンをミントする理由

* 例えば、DAOのトークンの半分を労働者が、残りの半分を投資家が保有します
* DAOは、企業が投資した資金量に比例して、トークンをミントします
* DAOは、特定の商品やサービスと引き換えに、エンティティに対して一定量のトークンをミントします
* DAOは、毎月一定量のトークンをミントし、その月にDAOに価値を提供した全員に比例して配布します

## 各種テンプレートでTokens Appを使用する

Tokens Appは、DAOの**メンバーシップと投票権を管理**するために使用されます。DAOにメンバーを追加するには、トークンをミントして割り当てるだけと簡単です。

メンバーシップと投票権を管理するためのこのシンプルなプロセスは、Aragonを使用してDAOのリソースを管理するための基盤となるものです。

### 企業型テンプレート

企業型テンプレートでは、1トークン＝1投票権、メンバーは割り当てられた数だけトークンを保有でき、トークンは譲渡可能です。

### メンバーシップ型テンプレート

メンバーシップ型テンプレートでは、1トークンが1投票権に相当しますが、メンバーは複数のトークンを保有することができず、トークンは譲渡不可能です。

### レピュテーション型テンプレート

レピュテーション型テンプレートについては、1トークンが1票となり、会員は割り当てられた数だけトークンを保有できますが、トークンは譲渡不可能です。

![Tokens App](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d867d542c7d3a7e9ae174bd/file-3GPg0yG2o5.png)

## **Holder（所有者）**

Token AppのHolderセクションには、現在のトークン保有者のリストと、それぞれの保有するDAOトークンの残高が表示されます。

### リストのドロップダウンメニューをクリックすると、以下のオプションが表示されます

* Add tokens：そのトークンホルダーにさらにトークンを割り当てる
* Remove tokens：トークンホルダーからトークンを削除する
* Edit custome label：カスタムラベルの編集（詳しくは[こちら](../home.md)）

![Tokens Appの外観](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d867d622c7d3a7e9ae174be/file-dgpIXaBkm6.png)

## **Token Info（トークン情報）**

**Token Info**セクションでは、DAO内のガバナンスに使用されているトークンの情報を見ることができます。

### **Token supply（**トークン供給量**）**

トータルでどれくらいのトークンがミントされたのか

### **Transferable（**譲渡可能か**）**

トークンを割り当てた後、別のエンティティに譲渡可能かどうか

### Token（トークン）

トークン名とトークンシンボル

![Token Infoの外観](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d867df22c7d3a7e9ae174bf/file-7fiikNO0jj.png)

## **Ownership Distribution（トークン保有量分布）**

**Ownership Distribution**では、DAOのトークン供給量のうち、どのエンティティが何パーセントを所有しているかを確認することができます。これは、トークンの所有権がDAO内にどのように集中しているかを確認するために役立ちます。

![トークン保有量分布](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d867dff04286364bc8f65d9/file-nj7kpToblW.png)

## **Add Tokens（トークンの追加）**

DAOにメンバーを追加し、DAOトークンを割り当てる場合、**Add Token**を使用する必要があります。

Add Tokensボタンをクリックすると、入力用のテキストフィールドがあるパネルが開きます。

* _**The recipient**:_ トークンを割り当てたいエンティティのアドレス
* _**Number of tokens**_: 割り当てたいトークンの数

これらの情報を入力した後、パネル内のボタンをクリックすると、アクションが完了します。

![トークンを追加](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d867e382c7d3a7e9ae174c0/file-gQIE902ZlX.png)

### この時点では、すべてのアクションにトークン所有者の投票が必要です

**Create transaction**をクリックして、ミントする新しいトークンを割り当てるための新しい投票を作成するトランザクションを作成します。Ethereumプロバイダでトランザクションに署名し、確認を待って、次のステップに進みます。

![](https://lh3.googleusercontent.com/RVlpE5QIyKb2gvvr5KQOf8ukZa0k5wczXfgOnnHfcvXI2JnBUtLX4KjKob\_EWMF9k9y1NjB1yzNcYrJLm2ETRezy7v9DDWucQNQ18OEQT\_8dBjMvSoZsymVIGK\_BJv\_8Cw1Mk88L)

### トークンを割り当てるかの提案にYes票を入れて承認する

Voting Appで、先ほど作成した**Mint tokens**の提案をクリックし、トークンのミントと割り当てを承認するためにYesを投票します。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a553504286364bc8f7fff/file-qb1DOKAI56.png)

![](https://lh6.googleusercontent.com/OYlBJ41umTMbdfMLqS9geT8ycshlmUfUgPHz6pNkg9cwIx3zNKAb8elnfw0QAKpo5N9rpah\_vExxl2lJYQG3ChtEK-5evFmrDG\_C92IUjn6\_Gt1\_WD8sP2ntGPaiVAeo4jZrQq1\_)

![](https://lh5.googleusercontent.com/IJWz3XKDtHi4MlsuxGlLJ8zatP6RiAluev6UK72zn1kMlHkpzNMAZEGyqSxw\_sp5lRIwHNU5ErZI1F0tjh\_8yVfIx99ImrR3X\_Xy7DWd9MC8k\_nY9w4X5CVbH6EqwnR54SD3kBw7)

![](https://lh6.googleusercontent.com/SJXCuLvpm6UwVIvBsplOQCcH5mfm11meFrHj9HRVH1FOGiM\_ax8Wmzf4IoQtX2GJNSDLC7BrUn8RmdDuaZ0Vzd9fhH\_JT-TggnudmR\_408oQ6VC6N6JWZXi1Hc2SudTl\_Y1p0xzZ)

### DAOの新メンバーをチェックする

{% hint style="success" %}
あなたのDAOは、1人から2人になったばかりです。新しい企業型DAOの良いスタートです！
{% endhint %}

{% hint style="warning" %}
* 賛成率が必要賛成率以上となる投票が行われた場合（例：必要賛成率60%、現在の賛成率65%）、自動的に提案が可決されることになります。
* 賛成率が必要賛成率よりも低い場合（例：必要賛成率が60％、現在の賛成率が40％）、反対票を追加することで議案の成立を阻止することができます。

**このためこの提案は、投票期間が終了するか、賛成率が必要賛成率を上回るか、どちらかの条件が満たされるまで保留されることになります。**
{% endhint %}

![](https://lh4.googleusercontent.com/DOedZ-Oj8ettsh6BPRTs7e7aY9ubI8k\_1R9oYcVTdiDouLo3coVdYI4s8pGTtZdHqw65aS1JgJ4ZTdQT77Unz86R9BvorceFOaebefJP9u1UJ2pfMY71PPZEerI3uVcGD\_CW13UA)

[EVM CRISPR（英語のみ）](https://evm-crispr.blossom.software/#/)を使用している場合、以下のようなコードを使用して、既得のトークンをアカウントに割り当てるなどの処理を行うことができます。

```
connect <DAO> token-manager
exec token-manager assignVested <ACCOUNT> <AMOUNT>e18 <START-DATE> <CLIFF-DATE> <END-DATE> true

```

> <mark style="color:purple;">**ご質問はありますか？Aragonフォーラムであなたの考えをお聞かせください**</mark>**👇**

{% embed url="https://support.aragon.org/t/aragon-client-navigate-your-dao-token-app/26/2" %}
