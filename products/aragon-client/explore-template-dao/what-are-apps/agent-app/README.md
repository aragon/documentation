# Agent App

## What is the Agent app?

The _**Agent app**_ enables Aragon organizations to **interact** directly with any **other smart contracts** on Ethereum. Before Agent, an organization would have to nominate a trusted party to interact with an Ethereum smart contract on its behalf.

{% hint style="info" %}
For example, an organization would send some $DAI to one of its employees, who would then be trusted to lend the $DAI on Compound, earn interest, and then send the interest plus the principle back to the organization.
{% endhint %}

Now with Agent, an organization can lend its $DAI out on Compound directly, without having to trust any intermediaries.

## How to start using the Agent app?

The easiest way to start using the Agent app is to **check the box** to optionally install it when first creating your organization:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bc80204286364bc8f9029/file-zLiYZ6kXSy.png)

{% hint style="info" %}
Note that installing Agent via one of the templates will replace the Vault app normally included with templates that do not use the Agent app.
{% endhint %}

{% hint style="warning" %}
If you did not optionally install the Agent app when first creating your organization, you can still install it after the organization has been created. To do so, you will need to follow the instructions for [installing and initializing the Agent app using the aragonCLI. ](https://github.com/aragon/aragon-apps)Note that this option is geared towards experts.
{% endhint %}

## **Agent frontend interface**

The _**Agent app**_ currently has a **view-only frontend interface** that you can use to see which tokens are currently held by the Agent app (including ERC-20, ERC-677, and ERC-777 tokens) as well as see a history of transactions made using the Agent app. The transaction history can be filtered by transaction type, token, or date, and can be exported as a CSV file.

![Agent App page](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5e8ce5d32c7d3a7e9aea8d19/file-r5322DPQHX.png)

The Agent smart contract address is available on the _**System**_ menu in the _**Organization**_ page.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bcdad2c7d3a7e9ae1a16d/file-pJP6dzQfhR.png)
