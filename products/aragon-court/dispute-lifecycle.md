# Dispute lifecycle

{% hint style="info" %}
In this section, you will learn what is a dispute lifecycle. The following guide aims to cover all the information you need to know as a guardian to understand a dispute's lifecycle and its related tasks so you can have the best experience possible using the Aragon Court Dashboard. For an overview of the Dashboard and its modules, [click here.](court-dashboard.md)
{% endhint %}

![](<../../.gitbook/assets/Screenshot 2022-02-07 at 11.19.38 (1).png>)

The Court's main unit of time is called a **term**, which is currently set to **eight hours**. Every period in Aragon Court is composed of terms (e.g. the vote commit duration lasts six terms or two days).

The current term and its remaining time are always displayed at the top of the dashboard.

As for disputes, they essentially observe the following lifecycle:

* **Pre-draft state:** Dispute creation, and evidence submission.
* **Adjudication rounds:** Adjudication rounds are where guardians are drafted, review the dispute's evidence, then cast and reveal their votes. Disputes can be made up of multiple rounds if the first round's ruling is appealed.
* **Final ruling:** Dispute is settled.

## **Dispute creation and evidence submission**

Disputes can be created by any entity subscribed to Aragon Court.

Once a dispute is created, a period of seven days is allowed to submit evidence that will later be reviewed by guardians. During this period, the dispute creator can also decide to close the evidence submission at any point in time. Evidence can be submitted in text format but HTTP and IPFS links are also accepted.

No action is required by guardians during this period.

## **Summoning Guardians**

![](<../../.gitbook/assets/Screenshot 2022-02-10 at 12.15.55.png>)

#### After the evidence period is over, the first adjudication round is initiated and the Summon guardians period begins.

The only task required during this period is to click on the Summon guardians button on the dispute page. Anybody can execute this task and receive a DAI reward proportional to the number of guardians being drafted. The current draft reward amount is <mark style="color:blue;">`Draft_Fee`</mark> per guardian.

Your chances of being drafted as a guardian are directly proportional to your active amount of tokens.

**If you get selected as a guardian,** here are a few things you need to know:

* **You will receive an email notification containing information about the dispute and the next steps for you (if you subscribed to email notifications).**
* **A portion of your active tokens will be locked until the final ruling is confirmed.** The main purpose of locking your active tokens is to incentivize consensus decisions and honest behavior. The exact locked amount is equal to 30% off the minimum active balance for each time you get drafted. The minimum active balance is currently <mark style="color:blue;">`Min_Active_Balance`</mark>, therefore the amount locked would be <mark style="color:blue;">`Min_Active_Balance x 0.3`</mark>.
* **It's possible to get drafted multiple times for the same dispute, if there are appeal rounds.** In that case, the amount locked will be multiplied by the number of times you are being drafted. The voting power will also be proportional to this number. For example, a guardian getting drafted twice for a dispute would have <mark style="color:blue;">`Min_Active_Balance x 0.3 x 2`</mark> locked and twice the normal voting weight.
* **Neither your inactive tokens nor the tokens contained in your wallet will be locked, only a portion of your active tokens.**

## **Vote commit** <a href="#votecommit" id="votecommit"></a>

{% hint style="danger" %}
The voting period is critical for a drafted guardian.
{% endhint %}

What you must do within the allocated time is first to review the evidence, then to try anticipating what the voting decision of the plurality of guardians will be.

This seems counterintuitive at first. Aragon Court is not exactly functioning like most legacy court systems in which every guardian is asked for their unbiased opinion. If this would be the case, it would be unfair to penalize the ruling minority. Instead, guardians are incentivized to reach consensus and are rewarded or penalized accordingly.

Most importantly, it is essential to cast a vote since failing to do so will result in financial penalties for you.

**Failing to cast a vote will result in your locked tokens getting slashed and redistributed to the winning guardians after the final ruling - so make sure to commit and reveal your vote in the allotted time periods.**

{% hint style="info" %}
The vote commit period lasts two days.
{% endhint %}

## Steps required to cast a vote:

### **Select one of the three voting choices.**

Three choices are available: voting to **Allow** the action being disputed, voting to **Block** the action, or **Refuse to vote**.

You can choose to refuse to vote for many reasons, for example, if you consider that the evidence was not conclusive enough or the description was incoherent.

{% hint style="warning" %}
Remember that you should vote the way that you think a plurality of guardians will vote, since you will be penalized if your vote is in the minority.
{% endhint %}

### **One-time-use-code**

To keep the votes secret until the end of the voting period, your vote will be combined with a randomly generated code.

{% hint style="warning" %}
For security purposes, it's important that you save this code somewhere safe (such as inside a password manager) and do not share it with anyone.
{% endhint %}

**Enable Court Auto-reveal service** is a convenient option available if you want your vote to be revealed automatically during the next phase. If you select this option, you are relying on Aragon, which hosts the Aragon Court Dashboard at [court.aragon.org](https://court.aragon.org), to cast your reveal transaction on time. Otherwise, manual action will be necessary during the Reveal period.

Click the **Commit your vote** button to send the transaction.

### **Leaking the secret one-time-use code**

If you leak your one-time-use-code, either on accident or on purpose, you could be **penalized**. This will put you on the losing side of a dispute even if you cast your vote for the plurality outcome, and your locked tokens will be redistributed to the plurality guardians after the final ruling. This mechanism is in place to dis-incentivize cheating/ collusion among guardians.

If another guardian leaks their one-time-use code then you can penalize them using the following steps (this will be added to the guardian dashboard for ease of use in the near future).

**Step 1.** Visit the **"leak"** section of the Aragon Court ["write contract page"](https://etherscan.io/address/0x96D7B5E5372743Abc69d1eAc714e893fA71d3baa#writeContract) on Etherscan.

**Step 2.** Fill out the form fields with the following information:

* \_voteId: enter the **vote ID** that the guardian is leaking their code for.
  * To get the vote ID, go to the Aragon Court subgraph ["Disputes and rounds with votes"](https://thegraph.com/explorer/subgraph/aragon/aragon-court?query=Disputes%20and%20rounds%20with%20votes) section, enter the Dispute # in place of "0" where it says {id\_in: \[0]}, then press Ctrl+Enter on your keyboard to execute the query. On the right side of the query box it will say "vote": "id": "0". In this case 0 is the vote ID. Note that the vote ID will be different for any dispute other than Dispute #0.
* \_voter: the **Ethereum address** of the cheating guardian.
* \_outcome: the outcome the cheating guardian submitted. It can be a 2 (Refuse to rule), a 3 (Against), or a 4 (In favor).
* \_salt: the **salt** the cheating guardian used to commit the vote
  * To get the salt, take the one-time-use code that was leaked and enter it as the "Input" on [this Keccak256 conversion tool](https://emn178.github.io/online-tools/keccak\_256.html) then press the "Hash" button. The result in the "Output" box is what you should copy/paste into the \_salt field.

{% hint style="info" %}
**An example of the completed form looks like this:**

Step 3. Click the "write" button, then sign and send the transaction. Once the transaction is confirmed, the guardian who leaked their one-time-use code will be penalized.
{% endhint %}

## **Vote reveal** <a href="#votereveal" id="votereveal"></a>

After the voting period has ended, guardians will have **two days** to reveal their vote.

If you enabled the **Auto-reveal service**, there is no action required from you at this stage. Otherwise, simply click on the **Reveal your vote** button. Your one-time code shouldn't be necessary unless a problem occurred within the court, but if it is needed, you'll be prompted to retrieve it from the safe place you stored it and enter it into the guardian app.

## **Appeal and appeal confirmation**

**Now that the votes are revealed, you can see whether you voted with the plurality or not.** But before the ruling can be executed, an appeal period is started during which any user can lock DAI as collateral to propose an appeal. Appeal collateral amounts can be found in the Aragon Court FAQ.

{% hint style="info" %}
An appeal must be confirmed by a second user to officially start a new round. Appeal confirmation collateral amounts can be found in the [Aragon Court FAQ](../../faq/products/aragon-court-faq/).
{% endhint %}

{% hint style="success" %}
**If an appeal is confirmed.**

A new adjudication round is initiated and a new jury is drafted. With each new appeal, the number of guardians is multiplied by **three**. The appeal and appeal confirmation periods both last **two days.**
{% endhint %}

{% hint style="danger" %}
**If an appeal is not confirmed**

The outcome proposed by the appealing party wins. For example, if the ruling of the previous round was "Allow" and the appealing party proposes an "Block" ruling, and no one confirms the appeal, then the final ruling will be "Block".
{% endhint %}

### When the final ruling is confirmed:

* if the ruling has switched in favor of the user who appealed (the "appealing party") then the collateral of the user who confirmed the appeal (the "confirming party") is redistributed to the appealing party.
* If the ruling is in favor of the confirming party, then the collateral of the appealing party is redistributed to the confirming party.
* If the final ruling is in neither the appealing party nor the confirming party's favor, then both the appealing party and confirming party get their collateral back minus a fee that goes to the guardians who voted in the plurality.

## **Final ruling**

Once a ruling has been decided without any appeal, the final ruling is sent to the smart contract that triggered the dispute and all the adjudication rounds for the dispute can be settled taking into account the final ruling for rewards and penalties.

{% hint style="success" %}
**If you voted as a guardian with the plurality of guardians in the final ruling.**

You just earned a percentage of the slashed tokens from guardians who voted in the minority.
{% endhint %}

{% hint style="danger" %}
**If you voted with the minority**

Your locked tokens are redistributed to the guardians who voted with the plurality in the final ruling.
{% endhint %}

## **Final appeal round**

The maximum number of appeal rounds is not infinite, it is currently set to **four**.

{% hint style="success" %}
**If an appeal is still confirmed after the maximum allowed is reached.**

A final round is initiated where the number of guardians equal to <mark style="color:blue;">`total active stake / Min_Active_Balance`</mark> is drafted, in which case all drafted guardians will be required to make up and safely store a secret passphrase to vote. The auto-reveal service is currently disabled for the final appeal round, so guardians will have to manually reveal their vote with their secret passphrase during the final reveal period.
{% endhint %}
