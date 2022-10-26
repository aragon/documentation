# Legal integration with Otoco

{% hint style="info" %}
Being a DAO is great, but sometimes contracts with 'real world' entities are needed, and they need you to be a 'real world' entity as well. This is a How to Guide to setup a standard Delaware Series LLC with [**Otoco**](https://otoco.io/) and to integrate it with your Aragon Client DAO.

Cost to do this? Less than 5 USD!
{% endhint %}



In our example, you started a new Aragon DAO called Awesome Music, a decentralized Music Label. All is working well, you are collaborating with people online in different countries.

But soon you find out that a musician of Classical Music insists on having a legal contract with your DAO Label instead of a token agreement.

That needs the DAO to be registered in the legacy world as an LLC. But how on earth do I do that? Let us show you how!



Open the DAO on Aragon Client by clicking on the following link: [**https://client.aragon.org/#/awsmmusic/**](https://client.aragon.org/#/awsmmusic/) **** (This example DAO is on Ethereum Mainnet).

{% hint style="danger" %}
Switch your Web3 Wallet to **Ethereum Mainnet**, to make the DAO appear on Aragon Client.



Next to Ethereum Mainnet, Otoco is also available on **Goerli Testnet, Polygon Mainnet, and Mumbai Testnet**, so you can also integrate your Client DAO on these networks with Otoco!
{% endhint %}



You should see the following screen. Click on 'Assign Tokens':

![](https://lh6.googleusercontent.com/9jPGBkFSqmTAGgzGafNHwJbn9RT6pdwpG7mMB-FJiv7aVwbesPPi5JkVLTds-IbXskzxQKTkwvi2loX372FyBw6orZVRVRtZUUPqyfJ39KSEcVjXw\_4-l9fRwNJ3OVE4DDxRXTzKWK4cmWe4LVLyDA)



This takes you to the 'Tokens' app. Here you can see some of the Token Holders, the artists which signed up with Awesome Music.

<figure><img src="../../../.gitbook/assets/Schermata 2022-08-31 alle 12.24.30.png" alt=""><figcaption></figcaption></figure>



Now let’s go to Otoco, to create a legal integration for the DAO. Here’s the link [**https://otoco.io/**](https://otoco.io/)****

Click on 'Spin up your project now':

![](https://lh6.googleusercontent.com/96D6ygT4pbD8\_WFZM3cLBAuPTib4OLDRTF4eAGhAQrdkG7\_9R8cukZLubjC6c1sA3d77bVO55NFR\_CbNz2u01e0u-\_fjeP4Mm-SH3vVApjJ3oGHYGbxz86O9q7P7VypNvYsou0s9DgZmqy6OKoRbiQ)



Select 'Ethereum Mainnet' and click 'Get started on next screen':

![](https://lh4.googleusercontent.com/gCbLVyz0bIefsqaiE4tbcSEJYp9Sildw9ljUh3WyYgolMJ8KVL3YMpL1G6LzhMboFhDkFl4w1SHPjkAEzUWVzTmXbml8eQrSe\_UI9SyEtRDaJVnQyO6gOvCrmIZGnWz8RVx07ysj5e14\_4ZGzqSgVA)

The select 'Just Me' and then 'Continue':

![](https://lh5.googleusercontent.com/TZG-OSJnh89laDPv25ZuyhlT5rY7k2JnyjkbjQJHBNPyRGR7PKzdRl09WD-OBQJVsion1klBbSkovtVSsxWf8FWapsCM0y-PqR6qQW-KYtBWTXYMCVgPi4kF7NB\_lTyahXf7XBSlN7P9zwKx1nDgjw)

At the moment the only options to set up an LLC are in the USA. For this example select 'Delaware Series LLC', then click 'check' and then 'continue':

![](https://lh3.googleusercontent.com/Qn5t1VJtdoKKXT0tRLpbFoxj3rdD0uu6VdVw1tHKALmlVR6w5HVmA9S4WKV7yP-IdymEWwL-N5hX0UVzHRWrajppt85nTPkAUDoz-DKcHVsDrG2Z56vdC\_YRrHBb7RsFjr8J7Dvm5tM6CVGPLU2Lww)



Now it's time to connect your Web3 Wallet. Pre-select the account in your wallet which also owns DAO tokens and the right network, in this case 'AWSMM' tokens and 'Ethereum Mainnet'.

{% hint style="danger" %}
If you connect a Web3 Wallet account to Otoco which does not own DAO tokens, the integration will not work.
{% endhint %}



Click 'Connect Wallet':

![](https://lh6.googleusercontent.com/GPiHnhh-D-YYh0huMOgvtDFObHSjCiHINzNYsoR3yYM4Od6-rSTrQqZVEEInYyeC53qDBjjXJ-3amRuS7G0Rrnvz\_k2SFmhLdi2ZR1w27Gc19qSPRR-4CrhamAscGm5U1TVhT2IiGjgE9hesDzLo\_w)



Check whether your wallet connected successfully. In this screen click 'Activate Company'. Now a transaction should pop-up in your Web3 Wallet. Confirm the transaction:

<figure><img src="https://lh6.googleusercontent.com/bQ2-bZsbdfipwuwo7Bd0WjkwNg5UWivA7cCq1ehdKlNFPhkG1erluCz3WUJJk8NdU3K2co_zRnjBkXmsWQsMKZxyfNGcvhst4QyiT6a88Pt8hLgLgwPDzBqYFASHDoB-p9vOZtye2uyUvq38Jia5JLmqRrWULTHuIIkTj0-W1juOAYYUvJqXFdUd" alt=""><figcaption></figcaption></figure>



Once the transaction has been processed you should see the following screen. Click here on 'Go To Dashpanel':

![](https://lh4.googleusercontent.com/C98NFdD89dpROjRsSmIZRieZYRhhN91Ib1EsSyctibGqbCvXLSQ1YI04cUVCoEe2R2ShlDtIxfipH0X\_5wVzMjv-nr5RhtjYoc9yEo6Vla4PS77aTAnh4Ia9Ab6X8JVnSPF9t0G3tC0scD\_cVQknew)

{% hint style="success" %}
Great, the **legal wrapper prepared for your DAO has been setup**! :tada:



Now let’s integrate it with the Aragon Client DAO!
{% endhint %}



In the Otoco Dashpanel, click on 'Tokens' in the left menu bar:

![](https://lh6.googleusercontent.com/zlhj1jPsksD2U-nVVIvy3Fw5d5tP1XBkOnlBz10y9PgmV3Ppdwq6OMdTvRUWJg8WrgJAqrpP4t\_LP4JjdEh-m-y48AJtlKym3P3QCBdrP\_c7TP7R0kqJ4ZWSuqmL6ESjDHe29aHTYQ3xcmo7-PXmOg)



You should see the following screen:

![](https://lh3.googleusercontent.com/bAPONMEYctecwAz1iuoV69fooidqnBWzN4vwTJ7dLNTvQ3jTmSGRZlvc6TzdwixKr0AfZP5ph6UMaMhQnzsEe5QKHTehU-telIokGfhxdAM83j2LlWiiG24oQgwxSZ5BY\_3fUxkWsgIVQ1mLTm\_zGA)



Now we need some info from the DAO. Go back to the 'Tokens' app of Awesome Music. Here's the link: [**https://client.aragon.org/#/awsmmusic/0xd181ce5f2e300e13f8327f3208da8903e026a048/**](https://client.aragon.org/#/awsmmusic/0xd181ce5f2e300e13f8327f3208da8903e026a048/)



When there click on 'awsmm.. (AWSMM)' in the 'TOKEN INFO' box.

<img src="https://lh4.googleusercontent.com/MuYOYEbX2u4dopx5O3Ma1EOt4tDuA7jc34vK2RdrER1Kck7L53Frc-lCf59uI41sNdH59rS-aVvmJmvAgB_Pz4NCwHUVla9a02p-q36BiFP44SaDmbnsFhqLs1u8IjAbzYDpsQs5h84YZ0aiwmqiI7GXMk-ojfCWJOKoD2oXXk2_yogtemhwcbZW" alt="" data-size="original">





Then copy the token address by clicking on the copy symbol:

![](https://lh3.googleusercontent.com/WmK0d0AeihWgxuC10ZEzu41iBPoKWo2x5bAHPMhH5qWwl3Okwunpu4FQZi9NVlUgjSViU\_5kODxxTu1cCkdFyuwiMWHlkNa1TUj8\_e2ZmDjI2OFiSRcyQ5Nu04wqofFUm2h7dx8BEYgTTkCM1tY8M0I29R8yY-uMCngrczNfDnm7RXBqUoeV8eLj)





Now go back to the Otoco screen and paste the address where it says 'paste your ERC-20 token contract address here', and click on 'Attach Token':

![](https://lh3.googleusercontent.com/AHlOW8oSbNiq7T9h-Xrb5wt\_ofVCtyPmSMY5u8Sw4t82ZkzrCdq6Tlzox41tj3qQYGsfOx6Y536f8omA659cbrkiQeiL789veF4IF2UnncKY4K-SYhk08vq68dBSyzkF9a7--dRbf7bSPdM8xiRIHg)



In your Web3 Wallet a transaction should popup. Confirm the transaction and wait for it to be processed.

![](https://lh3.googleusercontent.com/3SE87L4YicNC\_HKdT9KalZJXu2I5apLQQsXqt4sN6vHyhyXHTp23oefPcRtbJ681YvTeDz2uHpgtKPoF2QGIzcmf1U2569GOUI0LA8qvPL3kKpOZISYpCcTsPaRpIK8narWQqwfd9KUgoTYWTguk0A)



{% hint style="success" %}
Awesome, your Aragon Client DAO has now been integrated with the **Otoco legal wrapper**!
{% endhint %}



You should see the screen below. Click on 'SHOW' to see all the Awesome Music token holders appear:

![](https://lh4.googleusercontent.com/a7JKZUo0IspMEOhHbxJOdNwJu27Jz8NYcKBdkYZrhQGCpBRMTh-EFHOxKLJaLPL3qDziiM67ilBSFD5ZPFJ-Jbjoq2mWxGDYGp8zQTBihQi2fLMPcnwDswZlxA\_l2ASHHvkueHpQuy1lK29NSa3WXg)



You should see a list of current holders:

![](https://lh3.googleusercontent.com/U3U6qAWIzlefNpidi1dEEqXqLmu5XB2dlo7Lq4yRGeaxJiM72lKeUR93OMtAEbxnHrDgTxarq-3QvRz\_Q2JEmSHyFVL4hBFe5hhR9QUd4DMD\_KdlGpxqfU2mJ1ez8Z17KR5KeQao1wu\_7wH62pSnjw)



Now if we go back to the Aragon DAO, you can verify that all the token holders are represented in the Legal Wrapper!

![ ](https://lh4.googleusercontent.com/g-NoIu1y3lP6fLPCptcSmj3szpAZv7rgBYMblACdj12eD-OmzSuJpY5JPGzn5mgoX3O0yugiFqrR1JzCqK0iyD3hkWyu5NQsLetm8Jqv8yOXgbfKN6ordhbXJ0iPEazp5cQdhbpqBLjCiM15xHiWVw)



Now last let's take a look at the official LLC documents like the Certificate of Formation. To do so click on 'Files' in the left menu bar. You should see the following:

<figure><img src="https://lh3.googleusercontent.com/kKStyVNxnS4g7RRxr3Ik4ma3bq_VegKxkoROp4BEkgcSY5ogb3ZuqYqAAaJkCYlqE8_0FmsOtJ77aj8zGR1yi4Z2dUsPRUWx9MuigZtNQi3PksRw9U6PBrRZcYMQweGs9pCY99XT8acCQYU7Yi66JrIznjb3m4hdV0_1rro9e9rMRPqistwXcobn" alt=""><figcaption></figcaption></figure>

You can download the LLC documents here.

That was all, good luck now with your DAO in the legacy world! :thumbsup:

