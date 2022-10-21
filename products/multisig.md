# マルチシグウォレットの設定

{% hint style="info" %}
このセクションでは、Aragon Client DAOをマルチシグウォレットで管理する方法について見ていきます。
{% endhint %}

{% hint style="info" %}
ここでは[Gnosis Safe MultiSig（英語のみ）](https://help.gnosis-safe.io/en/articles/3876461-creating-a-safe-on-a-web-browser)を使用しますが、コントラクトのやり取りをサポートする他のマルチシグウォレットでも同様の方法を取ることができます。
{% endhint %}

## 前提条件

### Client DAOで必要な権限をマルチシグに割り当てる

{% hint style="info" %}
Aragon Client DAOは、各アクションが一連の権限付与によって保護されている制御システムにアクセスすることができます。特定の権限を持っている人だけが操作することができます。そのため、マルチシグウォレットに、希望するアクションの権限を割り当てる必要があるのです。詳しくは[こちら](aragon-client/explore-template-dao/system-setting/permissions-setting.md)をご覧ください。
{% endhint %}

1\. 以下の手順で、マルチシグに権限を付与します。

2\. DAOポータルを開き、左側にある**Permissions**タブを選択します。ここで、DAO内で持っている権限を確認することができます。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6112718fb55c2b04bf6dce7e/file-DCOHNWElgt.png)

3\. 新しい権限を追加するには、**New Permission**ボタンをクリックします。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611272116ffe270af2a97627/file-D7HYuaQgTh.png)

4\. ドロップダウンメニューから権限を作成するアプリを選択します。

5\. **Assign To Entity**フィールドで、新しい権限を割り当てるエンティティを選択します。マルチシグアドレスを追加するには、**Custom Address**を選択し、下のフィールドにアドレスを入力します。

6\. 権限を与えたいアクションを選択します。この例では、DAO内で新しい投票を作成するための権限をマルチシグに割り当てます。

7\. **Add Permission**をクリックします。DAOの構造と、このアクションの権限管理者の設定によっては、投票が作成される場合があります。

8\. 望ましくない権限の取り消しを行います。これを行うには、任意の権限を展開し、ごみ箱のアイコンをクリックしてください。

{% hint style="danger" %}
不適切な権限はDAOを脆弱にしたり、アクセス不能にする可能性があるので、注意してください。
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611275a7b37d837a3d0e2535/file-AecSpNvGSO.png)

設定後

![Multisigの権限](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d0ef364a230081ba1ce2f/file-aDCnpa7wjo.png)

{% hint style="info" %}
ここでは、DAO内の支払いを管理し、投票サポートパラメータを変更するためにマルチシグに権限を割り当てています。しかし、我々は権限マネージャーとして投票を維持しているため、コミュニティのメンバーはこれらの権限の削除に投票することができ、DAOのマルチシグによる管理を実質的に停止させることができます。
{% endhint %}

### アクションの実行

1\. [Gnosis Safe（英語のみ）](https://gnosis-safe.io/)のウェブサイトにアクセスし、dappに接続

2\. vaultを開く

3\. **New transaction**ボタンをクリックして、**Contract interaction**を選択

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d0efb766e8844fc34e2c5/file-ery56Brop6.png)

4\. やりとりしたいAragonアプリのアドレスを入力

DAOポータルの**Organizations**ページで見つけることができます。そこにある**Installed Aragon Apps**セクションを見てください。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d1014766e8844fc34e2cd/file-8cuqErvYC1.png)

5\. ABIフィールドに情報が自動的に入力されます。そこに表示された内容を削除してください。

6\. 選択したAragon Appの、連携したいベースコントラクトを見つけます。

* ステップ 4 で使用したアドレスを[etherscan（英語のみ）](https://etherscan.io/)で開く
* **コントラクト**に移動
* **Read contract**を選択
* **Implementation**を展開
* [etherscan（英語のみ）](https://etherscan.io/)の**Implementation**の下に表示されたアドレスを開く

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d115d766e8844fc34e2ce/file-g3POvBnP7e.png)

7\. アドレスのABIをステップ5のフィールドにコピーする

* **Contract**タブを選択
* **Code**タブを選択
* **Contract ABI**を確認
* ABIをGnosis Safe ABIの入力フィールドにコピー

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d12f1766e8844fc34e2d7/file-nCgkCpoDAD.png)

8\. 使用するメソッドを選択し、パラメータを入力します

ここでは、Finance Appから新しい即時決済を作成します。これは**0.1ETH**（0x0..0トークンアドレスで表される）を0x424...のアドレスに送金します。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611277e1766e8844fc34f0ab/file-xlkaRMNQ6n.png)

**Review**、**Submit**の順にクリックしてください。十分な人数が署名した後、Etherscanでその取引を見ることができ、承認されるとDAOで効力を発揮します。

## 想定される問題

{% hint style="warning" %}
Gnosis Safeのアドレスからこのメソッドを呼び出すための権限があることを確認してください。
{% endhint %}

{% hint style="warning" %}
ガス代の推定に失敗し、警告が表示された場合、権限、メソッドパラメータ、ABI、コントラクトアドレスのいずれかに間違いがある可能性があります。もう一度セットアップを行ってください。
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611278276ffe270af2a97644/file-rxfkptmQt8.png)

{% hint style="warning" %}
小数点以下の数字を入力する場合は、元の値にゼロを18個追加してください。例えば、10.5トークンを転送する**immediateTransfer**メソッドを呼び出す場合、10.5\*10^18 = 10500000000000000000を金額フィールドに入力する必要があります。
{% endhint %}

{% hint style="warning" %}
あるネットワーク（Rinkebyなど）でABIが表示されない場合、別のネットワーク（Ethereum Mainnetなど）上の別のDAOから同様のABIを取得しましょう。
{% endhint %}

> <mark style="color:purple;">**ご質問はありますか？Aragonフォーラムであなたの考えをお聞かせください**</mark>**👇**

{% embed url="https://support.aragon.org/t/web3-multisig-wallet/17/2" %}
