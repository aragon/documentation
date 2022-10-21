# Import your seed phrase into Metamask

{% hint style="info" %}
In this section, we'll go through how to **import the **_**first-dao**_** seed phrase** into the Metamask wallet.
{% endhint %}

## Log in to your Metamask wallet

The first step is to open up the Metamask browser extension and log in. If you're using Chrome you should be able to open Metamask by clicking on the fox icon located to the right of your address bar _(see the image below)_.&#x20;

If you can't see it, [_click here_](https://chrome.google.com/webstore/search/metamask). This will open up an interface to your Ethereum wallet.&#x20;

<figure><img src="../../../../../.gitbook/assets/m-3 (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Since we will import a new seed phrase, save the seed phrase of your current Metamask account by going to: Settings > Securty & Privacy > Reveal Secret Recovery Phrase.
{% endhint %}

## Click on the _**circle**_ in the top right

You should see a black drop-down menu appear _(see image below):_

__![](<../../../../../.gitbook/assets/Screenshot 2022-04-25 at 13.06.32 (1).png>)__

## Click on the _Lock_ button in the top right off this menu

You'll be taken to a _Welcome Back_ page:

![](<../../../../../.gitbook/assets/Screenshot 2022-04-25 at 13.10.18 (2).png>)

## Importing seed phrase

Importing the 12 words phrase will allow you to use Metamask with your _first-dao._

> If you are running the Aragon Client, enter the path and type:
>
> `cd first-dao`\
> `yarn start`

Click on _Forgot password_. Metamask should now open up in a new window with a heading _**Reset Wallet**_.&#x20;

Now, what you need to do is to look at the output of your terminal after you run `yarn start`. You should see the following at the start:

```
main     | Starting Aragon app development...
main     | App name: first-dao
main     | App id: 0x4c93e09d64b5a9a4c770869d95fd637936feb6ae784413a480ae0aa65889348a
main     | Accounts mnemonic "explain tackle mirror kit van hammer degree position ginger unfair soup bonus"
```

These 12 words phrases will allow us to use Metamask to access an account that has permission to update the Counter in our Counter app.

{% hint style="danger" %}
Note that your seed phrase (or _mnemonic phrase_) won't be the same as mine. So make sure you copy yours from your terminal, and not from this blog.
{% endhint %}

## Create a new password

Once you copied the 12 word seed phrase, paste it into the wallet seed text box, and create a new password (see image below):

![](<../../../../../.gitbook/assets/Screenshot 2022-04-25 at 13.28.54 (1).png>)

## Click on the _Restore_ button at the bottom of the page&#x20;

The imported account will appear in the _My account list_ when clicking on the top right circle.

{% hint style="success" %}
You've now connected Metamask to your _first-dao_.
{% endhint %}



> <mark style="color:purple;">**Do you have a question? Leave your comments here at our Discourse forum**</mark>** 👇**

{% embed url="https://support.aragon.org/c/dev-support/20" %}
