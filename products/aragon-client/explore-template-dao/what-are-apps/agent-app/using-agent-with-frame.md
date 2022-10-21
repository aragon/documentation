# FrameでAgentを利用する

{% hint style="info" %}
ここでは、FrameウォレットでAgent Appを使用する方法を説明します。
{% endhint %}

## Agentアプリを使うには？

Agentアプリを使用して他のEthereumスマートコントラクトと直接やり取りする最も簡単な方法は、Frameのスマートアカウント機能を使用することです。FrameはデスクトップネイティブのEthereumプロバイダーで、Agent Appをネイティブにサポートしています。

{% hint style="info" %}
すでにFrameをインストールし、「Acting Account（代行アカウント）」を追加している場合は、「**Aragon Agentを追加する**」セクションまでスキップできます。
{% endhint %}

{% hint style="info" %}
Frameをインストールしていない場合は、[こちら](../../../../setting-up-a-frame-wallet.md)をご確認ください。
{% endhint %}

## ETH（またはtest-ETH）をActing accountに送金する

{% hint style="warning" %}
始める前に、Acting accountにETH（またはtest-ETH）を送って準備します。
{% endhint %}

あなたの**Acting account**は、少なくとも１つのDAOの**投票トークン**を保持するアカウントであり、Agentを介して**スマートコントラクトとやり取りする**ために使用するアカウントです。

このアカウントに送金したETHは、Agent Appが他のスマートコントラクトとやり取りしているときに、ガス代として使用されます。他のスマートコントラクトとやり取りする際にガス欠エラーが発生しないよう、Acting accountのETHが少なくなってきたら、必ず補充してください。

## **Acting accountを追加する**

Frameデスクトップアプリを開き、**＋**ボタンをクリックしてActing accountを追加してください。ハードウェアウォレットやホットウォレットを使って追加することができます。

{% hint style="info" %}
この例では、Ethereumメインネット上の資金ではなく、Rinkebyテストネットを使用しているため、ホットウォレットを使用します。ただし、ハードウェアウォレットを使用することをお勧めします。
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bd9702c7d3a7e9ae1a220/file-wPNVEoD1j4.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bd9782c7d3a7e9ae1a221/file-BZzJ4WikKD.png)

![](../../../../../.gitbook/assets/file-Hdky5v4UL9.png)

## **Aragon Agentを追加する**

* Acting accountの追加に使用したFrame上の同じ画面に移動し、**Smart accounts**セクションの下にAragon Agentを追加してください。
* DAO名を入力し、**Next**をクリックします。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bda5504286364bc8f90f9/file-2urBqXQ8j0.png)

* 次に、Acting accountを選択します。複数のアカウントから選択する場合は、DAOの投票権を保有するアカウントを選択してください。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bdabd04286364bc8f90fb/file-QPxHyh0odz.png)

* Actingを選択し、DAOの投票トークンを保持しているアドレスを選択します。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bdb0b2c7d3a7e9ae1a22a/file-sfavzdmwav.png)

* Frameで使用可能なアカウントのリストにAragon Agentが表示されるようになりました。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bdb3b04286364bc8f9104/file-yCdIwFtn04.png)

## **Aragon Agentを利用する**

Aragonロゴをクリックし、Agentアカウントを使用してください。ホットアカウントを使用している場合は、パスワードを入力してください。これで、あなたのAragon Agentで直接他のEthereumスマートコントラクトとやり取りする準備が整いました。

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bddef04286364bc8f9121/file-JXtXhKiVAb.png)

{% hint style="warning" %}
DAOで設定された権限によっては、Agent Appで行われた各トランザクションを実行するために、Voting Appで投票する必要があることを忘れないでください。
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bdf5e04286364bc8f912b/file-FFA5Mwilwm.png)
