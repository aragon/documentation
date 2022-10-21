# Using Agent with Frame

{% hint style="info" %}
In this section, we will walk you through how to use Agent App with Frame wallet.
{% endhint %}

## How to use the Agent app?

The easiest way to use the Agent app to interact directly with other Ethereum smart contracts is using the _smart account_ feature of Frame. Frame is a desktop-native Ethereum provider with native support for the Agent app.

{% hint style="info" %}
If you already have Frame installed and an "acting account" added, you can skip ahead to section **Add your Aragon Agent**.
{% endhint %}

{% hint style="info" %}
If you do not have Frame installed go [here](../../../../setting-up-a-frame-wallet.md).
{% endhint %}

## **Send ETH (or test ETH) to your acting account**

{% hint style="warning" %}
Before you get started, prepare by sending ETH (or test ETH) to your acting account.
{% endhint %}

Your **acting account** is the account that holds at least one (or partial if it is divisible) **voting token** in your organization and is the account you will use to **interact with smart contracts** via Agent.

The ETH you send to this account is used to pay for gas whenever the Agent app is interacting with other smart contracts. Be sure to top off the ETH in your acting account whenever it's running low so that you don't experience out-of-gas errors when interacting with other smart contracts.

## **Add your acting account**

Open the Frame desktop app and click the _**plus-sign**_ button to add your acting account. You can add it using a hardware wallet or a hot wallet.

{% hint style="info" %}
In this example, we will use a hot wallet since we are using the Rinkeby Testnet and not real money on the Ethereum Mainnet. However, it is recommended that you use a hardware wallet.
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bd9702c7d3a7e9ae1a220/file-wPNVEoD1j4.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bd9782c7d3a7e9ae1a221/file-BZzJ4WikKD.png)

![](../../../../../.gitbook/assets/file-Hdky5v4UL9.png)

## **Add your Aragon Agent**

* Go to the same screen on Frame you used to add your acting account, then add your Aragon Agent under the _**Smart accounts**_ section.
* Enter the _name_ of your Aragon organization, then click _**Next**_.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bda5504286364bc8f90f9/file-2urBqXQ8j0.png)

* Then select the acting account, choosing the account with the address that holds your organization's voting token(s) if you have more than one account to select from.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bdabd04286364bc8f90fb/file-QPxHyh0odz.png)

* Select the acting address, choosing the address that holds your organization's voting token(s).

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bdb0b2c7d3a7e9ae1a22a/file-sfavzdmwav.png)

* Your Aragon Agent will now show up in the list of available accounts to use with Frame.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bdb3b04286364bc8f9104/file-yCdIwFtn04.png)

## **Using your Aragon Agent**

Click on the Aragon logo to use your Agent account. Enter your password if you are using a hot account. You are now ready to interact with any other Ethereum smart contract directly with your Aragon Agent.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bddef04286364bc8f9121/file-JXtXhKiVAb.png)

{% hint style="warning" %}
Remember that depending on the permissions set in your organization, your organization's token holders may need to visit the Voting app and vote on each transaction made using the Agent app.
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bdf5e04286364bc8f912b/file-FFA5Mwilwm.png)
