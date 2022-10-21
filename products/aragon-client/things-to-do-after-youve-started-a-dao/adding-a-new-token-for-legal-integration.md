# Adding a new token for legal integration

{% hint style="info" %}
In this section, we show **how Aragon might interact with a legal entity such as a Series Delaware LLC**. In our example the Aragon DAO leverages **Gnosis Safe and EVM-CRISPR** as well, to show how an existing DAO might gain access to the legal entities.
{% endhint %}

## Introduction

Legal wrappers are a challenging subject, and for clarity's sake the author here is not a lawyer or giving legal advice... the goal in this work is to show one example of how Aragon might interact with an LLC, however this example is not meant to serve as a necessarily useful process, and rather as a starting point for critique....

## Quick start

Create your DAO starting [here](https://client.aragon.org/). For this example, I've created an [Aragon Reputation DAO](../how-to-create-a-dao-using-aragon-client/page-1.md)\


![Basic DAO with a reputation DAO - used because these tokens should be non-transferable](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.35.12 PM.png>)

## Mint your Token

Then head over to [EVM CRISPR](https://evm-crispr.blossom.software/#/terminal) where you can drop in some code to mint a new token.&#x20;

* Connect your wallet
* Clear the console
* Copy and paste these commands

```
connect your-dao-here token-manager voting 
new token "Test Token" TEST token-manager:new
install token-manager:new token:TEST true 0
grant voting token-manager:new MINT_ROLE voting
grant voting token-manager:new BURN_ROLE voting
exec token-manager:new mint @me 100e18
```

* Click the forward command and sign the transaction on your wallet
* After the transaction is confirmed, click _Go Vote_ and vote on your DAO

![EVM CRISPR](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.10.14 PM.png>)

![Vote on your EVM CRISPR transaction](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.32.09 PM.png>)

Now that you have created your new tokens you can see them in your tokens list.\


![This is our DAO](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.11.44 PM.png>)

## Legal wrapper for you Aragon DAO

Now over to [Gnosis](https://gnosis-safe.io) where we are going to connect the dots.&#x20;

* Create a Gnosis safe vault (for more help go [here](https://help.gnosis-safe.io/en/articles/3876461-create-a-safe)) and deposit some funds to your vault for signing the transactions.
* Load the Otoco App
* Name your company and choose between Delaware, UNA and Wyoming DAOs.
* _Approve Payment_ and _Activate the Company_

The main steps are shown in the images below.&#x20;

![Create a vault in gnosis](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.04.21 PM.png>) ![Load the Otoco App](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.04.31 PM.png>) ![Name your cool company & choose between Delaware, UNA, and Wyoming DAOs](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.05.46 PM (1).png>) ![Choose your flavor and mint!
](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.05.58 PM (1).png>)

If you see a message like that "your entity smart contract is not a wallet", go on the "_Asset wallet_" page and add an owner (a _Wallet address_ or a _Gnosis Safe Address)_.

![](<../../../.gitbook/assets/Schermata 2022-06-07 alle 14.50.29.png>)

Then go on the _Tokens_ page and copy and paste the address of your token (you can find it on the [Organization page](../explore-template-dao/system-setting/organization-setting.md) in your DAO).

![Transfer the tokens from your DAO to your Otoco LLC](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.11.31 PM.png>)

Now you have a Delaware LLC with Aragon minted tokens!

![](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.15.49 PM.png>)





> <mark style="color:purple;">**Do you have a question? Leave your comments here at our Discourse forum**</mark>** 👇**

{% embed url="https://support.aragon.org/t/aragon-client-legal-wrappers/173" %}
