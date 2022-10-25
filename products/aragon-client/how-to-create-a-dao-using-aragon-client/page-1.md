# Use the Reputation template

{% hint style="info" %}
In this section, you will learn how to create a Reputation DAO using the Reputation Template in the Aragon Client.
{% endhint %}

{% hint style="danger" %}
Before starting be sure to have read [How to create a DAO](./).
{% endhint %}

A Reputation organization is an organization that uses **non-transferable tokens** to represent reputation. Decisions are made using **reputation-weighted voting**.

## Creating a Reputation DAO

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.02.19.png>)

Click _**View details**_, review the apps available, check the boxes to install any optional apps you want to install. When finished, click _**Use this template**_.

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.22.29.png>)

## Claim a name

Select the name of your DAO and fill in the _**Organization Name**_ tab. Aragon uses the [Ethereum Name Service](https://ens.domains) (ENS) to assign names to organizations.

{% hint style="warning" %}
This name will be useful for accessing your DAO. Don't forget it!
{% endhint %}

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.23.36.png>)

## Configure the parameters of the Voting App

\_\_

{% hint style="info" %}
The Voting app parameters currently cannot be changed from the Aragon front-end client. To change the Voting app parameters after your organization has been created, you must first initialize the permissions to change these parameters, then you can change the parameters using the [aragonCLI](https://hack.aragon.org/developers/tools/aragoncli).
{% endhint %}

### Configure the voting settings

#### The Support percentage

It \_\_ is the relative percentage of tokens that are required to vote _**Yes**_ for a proposal to be approved. For example, if _**Support**_ is set to 50%, then more than 50% of the tokens used to vote on a proposal must vote _**Yes**_ for it to pass.

#### The Minimum Approval percentage

It is the percentage of the total token supply that is required to vote _**Yes**_ on a proposal before it can be approved. For example, if the _**Minimum Approval**_ is set to 20%, then more than 20% of the outstanding token supply must vote _**Yes**_ on a proposal for it to pass.

#### The Vote Duration

It is the length of time that the vote will be open for participation. For example, if the Vote Duration is set to 24 hours, then token holders have 24 hours to participate in the vote.

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.08.36.png>)

## Configure the parameters of the Token App

Choose a token name, a symbol, the token holders and the amount (balance) of token for each token holders. You can add the token holder using the _**Add more**_ button.

{% hint style="warning" %}
The token name and symbol currently cannot be changed. Do not add more than a few token holders to your organization on this screen or the transaction to create your organization may fail. You can add more token holders after the organization has been created.
{% endhint %}

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.25.03.png>)

## Review organization information

Open each panel to make sure that the information entered to launch your organization is correct. If anything is incorrect, you can click the _**back**_ button to return to an earlier screen and make the necessary correction.

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.25.54.png>)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.26.03.png>)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.26.14.png>)

## Launch your organization

Now you need to sign a transaction to create your organization. Open your Ethereum provider if the window does not open automatically. Click the _**confirm**_ button in your Ethereum provider to sign and broadcast the transaction.

Wait until the transaction is completed.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624d704286364bc8f650d/file-arEtXF8S0j.png)

Don't close or refresh the page until the process is completed and the DAO is deployed.

## Click "Get started"

{% hint style="success" %}
Your new Reputation organization is ready to go!
{% endhint %}

Now you can [explore your new Reputation organization.](../explore-template-dao/)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.17.04.png>)

{% hint style="info" %}
If your DAO doesn't open automatically, go [here](../../../faq/products/aragon-client/where-is-my-dao.md) and find how to access.
{% endhint %}

> <mark style="color:purple;">**Do you have a question? Leave your comments here at our Discourse forum**</mark>** 👇**

{% embed url="https://support.aragon.org/t/aragon-client-reputation-template/33/2" %}
