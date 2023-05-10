# Import your private key into Metamask

{% hint style="info" %}
In this section, we'll go through how to **import the private key of an account** into the Metamask wallet.
{% endhint %}

## Log in to your Metamask wallet

The first step is to open up the Metamask browser extension and log in. If you're using Chrome you should be able to open Metamask by clicking on the fox icon located to the right of your address bar _(see the image below)_.&#x20;

If you can't see it, [_click here_](https://chrome.google.com/webstore/search/metamask). This will open up an interface to your Ethereum wallet.&#x20;

<figure><img src="../../../../../.gitbook/assets/m-3.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Since we will import a new private key, for a security reason, save the seed phrase of your current Metamask account by going to: Settings > Securty & Privacy > Reveal Secret Recovery Phrase.
{% endhint %}

## Click on the _**circle**_ in the top right

You should see a black drop-down menu appear _(see image below):_

![](<../../../../../.gitbook/assets/Screenshot 2022-04-25 at 13.06.32 (1).png>)

## Click on the _Import Account_ button

Click the _Import Account_ button and a window like this will appear.

![](<../../../../../.gitbook/assets/Schermata 2022-06-14 alle 10.49.39.png>)

Enter the private key in the proposed field and click _Import_.

The private key that you are importing is provided in the console by the Aragon client.&#x20;

> If you are running the Aragon Client, enter the path and type:
>
> `cd "name of DAO"`\
> `yarn start"`

![](<../../../../../.gitbook/assets/Schermata 2022-06-14 alle 11.00.44.png>)

In our example, we have imported:

> **Account** 0&#x20;
>
> **private key** 0xa8a54b2d8197bc0b19bb8a084031be71835580a01e70a45a13babd16c9bc1563
>
> **public key** 0xb4124cEB3451635DAcedd11767f004d8a28c6eE7

![](<../../../../../.gitbook/assets/Schermata 2022-06-14 alle 11.11.23.png>)

The imported account will appear in the _My account list_ when clicking on the top right circle.

{% hint style="success" %}
You've now connected Metamask to your _first-dao_.
{% endhint %}

