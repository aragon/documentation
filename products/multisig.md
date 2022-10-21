# Setting up a MultiSig wallet

{% hint style="info" %}
In this section, we will look into how Aragon Client DAOs can be managed by a MultiSig wallet.
{% endhint %}

Here we are going to use [**Gnosis Safe MultiSig**](https://help.gnosis-safe.io/en/articles/3876461-create-a-safe), however, you could follow a similar approach for any other MultiSig wallet that supports contract interaction.

{% hint style="info" %}
Here we are going to use [Gnosis Safe MultiSig](https://gnosis-safe.io), however, you could follow a similar approach for any other MultiSig wallet that supports contract interaction.
{% endhint %}

## Prerequisites

### Assign the desired permissions in the Client DAO to the MultiSig

{% hint style="info" %}
Aragon Client DAOs have access to a control system, where each action is protected by a set of permission records. Only someone with specific permissions can act. That is why we need to assign the MultiSig wallet to a range of permissions that correspond with the desired actions. You can read more about it [here](aragon-client/explore-template-dao/system-setting/permissions-setting.md).
{% endhint %}

1\. Follow the steps below to assign permission to a MultiSig.

2\. Open your DAO portal and select the _**permissions**_ tab on the left. Here you can examine the permissions you have within your DAO.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6112718fb55c2b04bf6dce7e/file-DCOHNWElgt.png)

3\. To add a new one permission press the _**New Permission**_ button.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611272116ffe270af2a97627/file-D7HYuaQgTh.png)

4\. Select the App you want to create permission for on App drop-down menu.

5\. Select which entity will be assigned the new permission on the \_**Assign To Entity** \_ field. To add the MultiSig address select _**Custom Address**_ and enter the address in the field below.

6\. Select an action we want to grant permission to. In our case, we are assigning permission for a MultiSig to create new votes within our DAO.

7\. Press _**Add Permission**_. This might create a vote depending on your DAO structure and who is this action's permission manager.

8\. Revoke the undesirable permissions. To do so expand any permission and press onto the dustbin icon.

{% hint style="danger" %}
Please be cautious, as incorrect permissions could make your DAO vulnerable or inaccessible.
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611275a7b37d837a3d0e2535/file-AecSpNvGSO.png)

Result:

![Multisig Permissions](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d0ef364a230081ba1ce2f/file-aDCnpa7wjo.png)

{% hint style="info" %}
Here we have assigned MutliSig permissions to manage payments and change voting support parameters within the DAO. However because we have kept voting as the Permission Manager, community members will be able to vote to remove these permissions effectively revoking this MultiSigs control over the DAO\_.\_
{% endhint %}

### Executing actions

1\. Go to the [Gnosis Safe](https://gnosis-safe.io) website and connect to their DApp.

2\. Open your vault.

3\. Press the _New **Transaction**_ button and select _**Contract Interaction**_.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d0efb766e8844fc34e2c5/file-ery56Brop6.png)

4\. Give the address of the Aragon App you would like to interact with.

You can find it on the _**Organizations**_ page of your DAO portal. Look at the \_**Installed Aragon Apps** \_ section there.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d1014766e8844fc34e2cd/file-8cuqErvYC1.png)

5\. This will automatically populate the ABI field. Delete the content that appeared there.

6\. Find the base contract of the selected Aragon App that you would like to interact with.

* Open the address that you have used in step 4 on [etherscan](https://etherscan.io)
* Go to _**Contract**_
* Select _**Read contract**_
* Expand _**Implementation**_
* Open the address that appeared under _**Implementation**_ on [etherscan](https://etherscan.io)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d115d766e8844fc34e2ce/file-g3POvBnP7e.png)

7\. Copy the ABI of the opened address to the field in step 5.

* Go to _**Contract**_
* Select _**Code**_
* Locate _**Contract ABI**_
* Copy the ABI to the Gnosis Safe ABI input field

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d12f1766e8844fc34e2d7/file-nCgkCpoDAD.png)

8\. Select the method you want to use and populate the parameters.

Here we will create a new immediate payment from the Finance app. It will transfer **0.1 ETH** (represented by a 0x0..0 token address) to the _0x424..._ address.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611277e1766e8844fc34f0ab/file-xlkaRMNQ6n.png)

9\. Press _**Review**_ and _**Submit**_. After enough people sign the transaction you will be able to view it on Etherscan and once it has been confirmed it should take effect on the DAO.

## Possible Issues

{% hint style="warning" %}
Make sure you have the permissions to invoke this method from the Gnosis Safe address.
{% endhint %}

{% hint style="warning" %}
If gas estimation has failed and you get warnings there has likely been a mistake either in permissions, method parameters or ABI and contract address. Please go through the setup again.
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611278276ffe270af2a97644/file-rxfkptmQt8.png)

{% hint style="warning" %}
If you are populating fractional numbers, add 18 zeros to the original value. For example, if you want to invoke **immediateTransfer** method that will transfer 10.5 tokens, you will have to input 10.5\*10^18 = 10500000000000000000 into the amount field.
{% endhint %}

{% hint style="warning" %}
If the ABI is not displaying on one network (Rinkeby e.g.), get the similar ABI from another DAO on a different network (Ethereum Mainnet e.g.).
{% endhint %}

> <mark style="color:purple;">**Do you have a question? Leave your comments here at our Discourse forum**</mark>** 👇**

{% embed url="https://support.aragon.org/t/web3-multisig-wallet/17/2" %}
