# 🏗 Setting up a Gnosis Safe MultiSig Wallet

{% hint style="info" %}
In this section, we will look into how Aragon Client DAOs can be managed by a **MultiSig wallet**.
{% endhint %}

{% hint style="warning" %}
Here we are going to use [**Gnosis Safe MultiSig**](https://gnosis-safe.io), however, you could follow a similar approach for any other MultiSig wallet that supports contract interaction.
{% endhint %}

###

## Setting up the necessary permissions

{% hint style="info" %}
Aragon Client DAOs have access to a control system, where each action is protected by a set of permission records. Only someone with specific permissions can act.

**That is why we need to assign the MultiSig wallet to a range of permissions in the DAO that correspond with the desired actions.**

You can read more about permission settings [here](aragon-client/explore-template-dao/system-setting/permissions-setting.md).
{% endhint %}

In this example an Aragon Client DAO has a balance of ETH tokens **** stored in its Vault and you want to initiate a payment to compensate a DAO Contributor for her work. We will show how to **initiate a withdrawal of some of the ETH to the Contributor.**

<figure><img src="../.gitbook/assets/a1_Sig.png" alt=""><figcaption></figcaption></figure>

We want to add new permissions for your MultiSig, so click in this screen on 'New permission':

<figure><img src="../.gitbook/assets/a2_sig.png" alt=""><figcaption></figcaption></figure>

You should see the following side-window appear. Click on 'Select an app':

<figure><img src="../.gitbook/assets/a3_sig.png" alt=""><figcaption></figcaption></figure>

For this example we want to initiate a withdrawal of ETH by the MultiSig. This is usually done from the Finance app of the DAO, so select 'Finance' here and then click on 'Select an entity':

<figure><img src="../.gitbook/assets/a4_sig.png" alt=""><figcaption></figcaption></figure>

Since we need to add the address of your MultiSig, click here on 'Custom address...':

<figure><img src="../.gitbook/assets/a5_sig.png" alt=""><figcaption></figcaption></figure>

Now go to your Gnosis Safe, copy its address and paste the address of your MultiSig in the 'GRANT PERMISSION TO' box. Then click on 'Select an action':

<figure><img src="../.gitbook/assets/a6_sig.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Do not forget to remove the letters from the front of the Gnosis Safe address,**`eth:`**or**`gor:`**or different depending on the network you use! Otherwise it won't work..

The address should start with: **`0x`**
{% endhint %}



In this case we want to initiate a new payment, so click on 'Create new payments':

<figure><img src="../.gitbook/assets/a7_sig.png" alt=""><figcaption></figcaption></figure>

Now you filled the required boxes, click on 'Add permission':

<figure><img src="../.gitbook/assets/a8_sig.png" alt=""><figcaption></figcaption></figure>

Here the app warns that the permission can not be directly changed, but that a vote will be created to change the permission. Click on 'Create transaction':

<figure><img src="../.gitbook/assets/a9_sig.png" alt=""><figcaption></figcaption></figure>

A transaction should pop-up in your Web3 Wallet, 'Confirm' the transaction:

<figure><img src="../.gitbook/assets/a10_sig.png" alt=""><figcaption></figcaption></figure>

Once the transaction has processed, head over to the 'Voting' app of your DAO. You should see that an open vote has been generated. Click on the vote:

<figure><img src="../.gitbook/assets/a11_sig.png" alt=""><figcaption></figcaption></figure>

Now confirm the vote by clicking 'Yes':

<figure><img src="../.gitbook/assets/a12_sig.png" alt=""><figcaption></figcaption></figure>

Click here on 'Create transaction' and confirm the transaction that should pop-up in your Web3 Wallet:

<figure><img src="../.gitbook/assets/a13_sig.png" alt=""><figcaption></figcaption></figure>

In our example it confirmed that the vote has passed:

<figure><img src="../.gitbook/assets/a14_sig.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
More DAO members might need to approve the vote for the vote to pass. This depends on the **SUPPORT** and **MINIMUM APPROVAL** settings of your DAO
{% endhint %}

Now head over to the 'Permissions' app to check whether the permission for your MultiSig has been added. In our case click on the **Finance** app, and then unfold the 'Create new payments' permission. We now see that the MultiSig address has appeared!

<figure><img src="../.gitbook/assets/a15_sig.png" alt=""><figcaption></figcaption></figure>

## Initiate payment at the MultiSig

Now that's done we can initiate a payment at the MultiSig!



Head back to the (in this case) Gnosis Safe and press on 'New Transaction'. In the pop-up window which appears, press 'Contract Interaction':



<figure><img src="../.gitbook/assets/a16_sig.png" alt=""><figcaption></figcaption></figure>

