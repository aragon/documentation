# Change Quorum using Aragon Console

{% hint style="info" %}
This guide will show you how to change the minimum Quorum (turnout) needed for votes in your DAO to pass using Aragon Console.
{% endhint %}

Open your DAO, adding `/console` to the end of your DAO web address. The URL would look like this: `https://client.aragon.org/#/<your-dao-name>/console`

{% hint style="warning" %}
Replace `<your-dao-name>` with the name of your DAO in the above URL
{% endhint %}

You should see something like the below:

<figure><img src="../../../../.gitbook/assets/immagine1.png" alt=""><figcaption></figcaption></figure>

Next select `Exec` which is a command used to perform transactions DAOs.

You should now see the below screen. Select `Voting`, since you will create a change to the Voting App:

<figure><img src="../../../../.gitbook/assets/immagine2.png" alt=""><figcaption></figcaption></figure>

In the source code of the Voting App on [Github](https://github.com/aragon/aragon-apps/blob/631048d54b9cc71058abb8bd7c17f6738755d950/apps/voting/contracts/Voting.sol) you can find a function to change the minimum accepted Quorum Percentage, exactly what we need:

```solidity
function changeMinAcceptQuorumPct(uint64 _minAcceptQuorumPct)
    external
    authP(MODIFY_QUORUM_ROLE, arr(uint256(_minAcceptQuorumPct), uint256(minAcceptQuorumPct)))
{
    require(_minAcceptQuorumPct <= supportRequiredPct, ERROR_CHANGE_QUORUM_PCTS);
    minAcceptQuorumPct = _minAcceptQuorumPct;

    emit ChangeMinQuorum(_minAcceptQuorumPct);
}
```

We will now call this function from the Aragon Console. We will have to add `changeMinAcceptQuorumPct(uint64 _minAcceptQuorumPct)` to the command in the console, but first we will replace `uint64 _minAcceptQuorumPct` with your desired minimum Quorum Percentage.

This is expressed as a percentage of `10^18` , so for example `100% = 10^18` and `1% = 10^16`. Say you want a new minimum Quorum of 25%, then you need to add 16 zeroes to 25 coming to `250000000000000000`

{% hint style="danger" %}
**Warning**

The **minimum Quorum Percentage can never be higher than the required Support Percentage** for votes within your DAO! So make sure that the required Support Percentage of your DAO is 55% or more. If not, use a percentage lower than the required Support Percentage for this tutorial (otherwise you will run into an issue later).
{% endhint %}

Now add `changeMinAcceptQuorumPct(250000000000000000)` to the command in the console:

<figure><img src="../../../../.gitbook/assets/immagine 3.png" alt=""><figcaption></figcaption></figure>

When you now press 'Enter', a transaction should come up in your Web3 Provider (Metamask for most users). Check whether the minimum Quorum Percentage matches with what you had in mind:

<figure><img src="../../../../.gitbook/assets/immagine4.png" alt=""><figcaption></figcaption></figure>

Click 'Create transaction' and sign it with your Web3 Provider.

You are almost there! But first go to the Voting app since this change has automatically generated a vote. Now you (and enough of your DAO members) need to approve the vote for it to pass:

<figure><img src="../../../../.gitbook/assets/immagine5.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
**Warning**

The change will can only be **enacted** when the remaining voting time has run out. In the case of this example, the `Time remaining` is `23H:59M:12S` :point\_up:
{% endhint %}

When the voting time has run out click on 'Enact this vote' and sign the transaction with your Web3 Provider:

<figure><img src="../../../../.gitbook/assets/immagine6.png" alt=""><figcaption></figcaption></figure>

Once this is done the minimum Quorum Percentage should have been adjusted to 25%. You can double check this by creating a new vote. When you open the vote, the `MINIMUM APPROVAL` should have been adjusted to `>25% needed`.

{% hint style="success" %}
If you made it this far, well done! :clap:
{% endhint %}
