# Legal integration with Otoco

{% hint style="info" %}
Because sometimes you have to live in the real world. This is a tutorial for **adding a standard Delaware Series LLC to an existing Aragon Client DAO**, however should work with any DAO with ERC20 Tokens.
{% endhint %}

So you started a new Aragon DAO called Awesome Music, a decentralized Music Label. All is working well collaborating with people online in different countries, but soon you find out that a musician of Classical Music insists on having a legal contract with your DAO Label instead of a token agreement. That needs the DAO to be registered in the legacy world as an LLC. But how on earth do I do that? Let us show you how!



Here’s the link to the DAO: [https://client.aragon.org/#/awsmmusic/](https://client.aragon.org/#/awsmmusic/) (This example client is on Ethereum Mainnet).

![Sample Aragon Client dashboard home page](https://lh6.googleusercontent.com/9jPGBkFSqmTAGgzGafNHwJbn9RT6pdwpG7mMB-FJiv7aVwbesPPi5JkVLTds-IbXskzxQKTkwvi2loX372FyBw6orZVRVRtZUUPqyfJ39KSEcVjXw\_4-l9fRwNJ3OVE4DDxRXTzKWK4cmWe4LVLyDA)

Then click on ‘Assign Tokens’ on the left menu navigation area.

<figure><img src="../../../.gitbook/assets/Schermata 2022-08-31 alle 12.24.30.png" alt=""><figcaption><p>Aragon Client Tokens page with wallet address of Client token holders</p></figcaption></figure>

Here you can see some of the Token Holders, artists that signed up with Awesome Music.

Now let’s go to [Otoco](https://otoco.io), to create a Legal Wrapper for the DAO:

![](https://lh6.googleusercontent.com/96D6ygT4pbD8\_WFZM3cLBAuPTib4OLDRTF4eAGhAQrdkG7\_9R8cukZLubjC6c1sA3d77bVO55NFR\_CbNz2u01e0u-\_fjeP4Mm-SH3vVApjJ3oGHYGbxz86O9q7P7VypNvYsou0s9DgZmqy6OKoRbiQ)

Here’s the link [https://otoco.io/](https://otoco.io/). Feel free also to practice a bit with the Otoco app flow using Goerli test network. You may need to get some [goerli ETH for this](https://goerlifaucet.com/).

Click on 'Spin up your project now'.

Select 'Ethereum Mainnet’ and click ‘Get started on next screen’.

![](https://lh4.googleusercontent.com/gCbLVyz0bIefsqaiE4tbcSEJYp9Sildw9ljUh3WyYgolMJ8KVL3YMpL1G6LzhMboFhDkFl4w1SHPjkAEzUWVzTmXbml8eQrSe\_UI9SyEtRDaJVnQyO6gOvCrmIZGnWz8RVx07ysj5e14\_4ZGzqSgVA)

Select ‘Just me’ and then ‘continue’.

![](https://lh5.googleusercontent.com/TZG-OSJnh89laDPv25ZuyhlT5rY7k2JnyjkbjQJHBNPyRGR7PKzdRl09WD-OBQJVsion1klBbSkovtVSsxWf8FWapsCM0y-PqR6qQW-KYtBWTXYMCVgPi4kF7NB\_lTyahXf7XBSlN7P9zwKx1nDgjw)

At the moment the only options are in the USA.&#x20;

Select ‘check’ and then ‘continue’.

![](https://lh3.googleusercontent.com/Qn5t1VJtdoKKXT0tRLpbFoxj3rdD0uu6VdVw1tHKALmlVR6w5HVmA9S4WKV7yP-IdymEWwL-N5hX0UVzHRWrajppt85nTPkAUDoz-DKcHVsDrG2Z56vdC\_YRrHBb7RsFjr8J7Dvm5tM6CVGPLU2Lww)

Connect the same wallet account as the one that owns the DAO tokens, and press ‘connect wallet’.

![](https://lh6.googleusercontent.com/GPiHnhh-D-YYh0huMOgvtDFObHSjCiHINzNYsoR3yYM4Od6-rSTrQqZVEEInYyeC53qDBjjXJ-3amRuS7G0Rrnvz\_k2SFmhLdi2ZR1w27Gc19qSPRR-4CrhamAscGm5U1TVhT2IiGjgE9hesDzLo\_w)

Press ‘activate company’, and confirm tx in Metamask.

![](https://lh6.googleusercontent.com/GPiHnhh-D-YYh0huMOgvtDFObHSjCiHINzNYsoR3yYM4Od6-rSTrQqZVEEInYyeC53qDBjjXJ-3amRuS7G0Rrnvz\_k2SFmhLdi2ZR1w27Gc19qSPRR-4CrhamAscGm5U1TVhT2IiGjgE9hesDzLo\_w)

At the time of writing the ETH to cover the gas fees was around 5 USD.

Wait for tx to be mined...

Click ‘Go to Dashpanel’.

![](https://lh4.googleusercontent.com/C98NFdD89dpROjRsSmIZRieZYRhhN91Ib1EsSyctibGqbCvXLSQ1YI04cUVCoEe2R2ShlDtIxfipH0X\_5wVzMjv-nr5RhtjYoc9yEo6Vla4PS77aTAnh4Ia9Ab6X8JVnSPF9t0G3tC0scD\_cVQknew)

{% hint style="success" %}
Great, we now have **a legal wrapper prepared for our DAO**! Now let’s actually link it to the Aragon DAO!
{% endhint %}

![](https://lh6.googleusercontent.com/zlhj1jPsksD2U-nVVIvy3Fw5d5tP1XBkOnlBz10y9PgmV3Ppdwq6OMdTvRUWJg8WrgJAqrpP4t\_LP4JjdEh-m-y48AJtlKym3P3QCBdrP\_c7TP7R0kqJ4ZWSuqmL6ESjDHe29aHTYQ3xcmo7-PXmOg)

Click on tokens.

![](https://lh3.googleusercontent.com/bAPONMEYctecwAz1iuoV69fooidqnBWzN4vwTJ7dLNTvQ3jTmSGRZlvc6TzdwixKr0AfZP5ph6UMaMhQnzsEe5QKHTehU-telIokGfhxdAM83j2LlWiiG24oQgwxSZ5BY\_3fUxkWsgIVQ1mLTm\_zGA)

Now we are going to link Awesome Music tokens to the legal wrapper.

Go to the Aragon DAO and copy the token address there.

![](https://lh5.googleusercontent.com/\_WiX29-5Epl0w\_W3yhzm2gN0kT3RM\_pNQLCnPL9zrdMIAW9a16HZ8-4QHmRCvZIxCOkeaoeWAWodTwWRwV8q4hWmSLgjSGZ0q-Zz55iLOwGitGYXwFyJWo1Z4U4KRZJ9p8pGxy-A\_93a4iMwUyOHIw)

Click on the token name.

Then copy the address.

![](https://lh6.googleusercontent.com/9VQfuaOJybeuxC16STkB9HWnzmvnDDHbfFUDz6evfo88uZsvrKR\_KD7Z2wBP3tpvukjGSJYq4CN6HN457QiX0pnOzsLm2l3zYigiXH0ZhTR\_QKQfi\_-gj5scutxPREHLFMgTdD8\_wgzAFtx2q0ZwrQ)

Paste the address in the link erc-20 token box and press ‘attach token’.

![](https://lh3.googleusercontent.com/AHlOW8oSbNiq7T9h-Xrb5wt\_ofVCtyPmSMY5u8Sw4t82ZkzrCdq6Tlzox41tj3qQYGsfOx6Y536f8omA659cbrkiQeiL789veF4IF2UnncKY4K-SYhk08vq68dBSyzkF9a7--dRbf7bSPdM8xiRIHg)

Confirm the Metamask transaction and wait for it to be mined.

![](https://lh3.googleusercontent.com/3SE87L4YicNC\_HKdT9KalZJXu2I5apLQQsXqt4sN6vHyhyXHTp23oefPcRtbJ681YvTeDz2uHpgtKPoF2QGIzcmf1U2569GOUI0LA8qvPL3kKpOZISYpCcTsPaRpIK8narWQqwfd9KUgoTYWTguk0A)

{% hint style="success" %}
Awesome, the **Otoco legal wrapper has now been linked to the Aragon DAO**!
{% endhint %}

![](https://lh4.googleusercontent.com/a7JKZUo0IspMEOhHbxJOdNwJu27Jz8NYcKBdkYZrhQGCpBRMTh-EFHOxKLJaLPL3qDziiM67ilBSFD5ZPFJ-Jbjoq2mWxGDYGp8zQTBihQi2fLMPcnwDswZlxA\_l2ASHHvkueHpQuy1lK29NSa3WXg)

Click on ‘show’ to see all the Awesome Music token holders appear:

![](https://lh3.googleusercontent.com/U3U6qAWIzlefNpidi1dEEqXqLmu5XB2dlo7Lq4yRGeaxJiM72lKeUR93OMtAEbxnHrDgTxarq-3QvRz\_Q2JEmSHyFVL4hBFe5hhR9QUd4DMD\_KdlGpxqfU2mJ1ez8Z17KR5KeQao1wu\_7wH62pSnjw)

Now if we go back to the Aragon DAO, you can see that all the token holders are represented in the Legal Wrapper.

![](https://lh4.googleusercontent.com/g-NoIu1y3lP6fLPCptcSmj3szpAZv7rgBYMblACdj12eD-OmzSuJpY5JPGzn5mgoX3O0yugiFqrR1JzCqK0iyD3hkWyu5NQsLetm8Jqv8yOXgbfKN6ordhbXJ0iPEazp5cQdhbpqBLjCiM15xHiWVw)

Also = the official LLC documents like the Certificate of Formation. Click on Files. You can download the documents here. &#x20;
