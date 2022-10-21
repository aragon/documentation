# How to create a Govern DAO

{% hint style="info" %}
In this section, you will learn how to create a DAO using Aragon Govern.
{% endhint %}

## How to create a DAO

Creating a Govern DAO is a quick and easy process.

Go to [https://govern.aragon.org/#/create-dao](https://govern.aragon.org/#/create-dao), choose the network and connect your web3 wallet (if you need help go [here](../set-up-metamask/)) and fill out all the relevant information regarding your DAO.

## Basic Information

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/61155889b55c2b04bf6ddda0/file-jQxSjLKpa8.png)

## In the first step you should define

* **DAO identifier**: This will be your DAO unique identifier, and will be used as part of the URL to directly access your DAO. It may not contain spaces, and must not have already been used by another DAO. Try and name it something that relates to your community only (eg. "space\_invaders\_gamers\_dao").
* **DAO token**: Fill out the information about the token your community will use to govern your DAO. 3-4 letters is generally sufficient for your token name.

{% hint style="info" %}
**If you don't have a token yet**

\=> Choose the **New Token** option and fill out the token name, token symbol, and how many tokens you would like to mint initially. You can mint more tokens in the future, or even change the token contract to restrict future further minting. All the minted tokens will initially be sent to your wallet.

**If you already have a token**

\=> Choose the **Existing Token** option and add your token address to it.
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/61155a2d21ef206e5592aff7/file-6re43pNq8c.png)

* **Use Aragon Proxies**: Instead of deploying a whole smart contract to be the executor of your DAO (the one that executes transactions as the DAO), you will just deploy a proxy contract (which is a minimal version that forwards requests to a full contract that was already deployed by Aragon). By selecting this option you will drastically reduce the amount of gas needed to deploy your DAO.

{% hint style="warning" %}
This option **DOES NOT** reduce the security of your DAO in any way.
{% endhint %}

## Configuration

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6115589a6ffe270af2a9855f/file-jLdUKuX5Ov.png)

## In the second step you should define

* **Execution delay**: The amount of time a given transaction will be on hold before being executed. During this period, the transaction can be reviewed by your community members, and if it does not conform with your DAO agreement, it can be challenged. At the end of the delay period, the transaction will be available for execution. [Learn more](why-do-transactions-require-a-delay-period-in-order-to-be-executed.md).
* **Rules & Agreement**: An Aragon Govern DAO works thanks to optimistic governance: it expects its members to act in its best interest, and for them to always follow a specific set of (pre-agreed) rules. These rules are what make a DAO agreement, and can be provided as free text, pdf, or document.
* **Dispute resolution client**: This is the address of a smart contract that can act as a dispute resolution system for the optimistic governance model to be enacted. The default address is set to Aragon Court, a tested and secure dispute resolution system by Aragon. Be aware that if you change this address, and the new smart contract does not implement the [ERC3k standard](https://eips.ethereum.org/EIPS/eip-3000) (or it relies on an insecure system) you might make your DAO unusable or allow funds to be stolen.

## Collateral

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611558bd64a230081ba1eaec/file-dYJrDvkzgq.png)

## In the third step you should assert a...

* **Schedule token amount**: This is the token cost that will be required by any member to spend before they can schedule a transaction. Members who do not own the amount of tokens you define here will not be able to schedule any transaction. [Learn more about collaterals](understanding-collaterals-in-aragon-govern.md).
* **Challenge token amount**: This is the token cost that will be required by any member to challenge a transaction. Members who do not own the amount of tokens you define here will not be able to challenge any transaction. [Learn more about collaterals.](understanding-collaterals-in-aragon-govern.md)\*\*\*\*
* **Whitelist of addresses (optional):** This is an additional safeguard step you might want to add to your DAO to grant only a subset of members permission to schedule transactions.

{% hint style="danger" %}
Important: If a wallet address is in the whitelist, it still needs to hold the collateral token to schedule a transaction.
{% endhint %}

## Review the information to make sure everything is correct.

If you are happy with it, just go ahead and click the "Confirm and create a DAO" button.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611559fdb55c2b04bf6dddb3/file-fxIiexUROg.png)

> <mark style="color:purple;">**Do you have a question? Leave your comments here at our Discourse forum**</mark>** 👇**

{% embed url="https://support.aragon.org/t/aragon-govern-create-a-dao/43/2" %}
