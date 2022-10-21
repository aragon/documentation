# What is Aragon Court

Aragon Court is a **dispute resolution** protocol that handles subjective disputes that cannot be solved by smart contracts. This is achieved by having a **set of guardians** drafted for each dispute **who will vote to guarantee a certain ruling.**

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5e3afa9104286364bc94e693/file-nGEAP7l6NI.jpg)

## Aragon Court fundamentals

**Guardians sign up** to get drafted into the court by **activating ANT** tokens in Aragon Court's smart contract. The more tokens a guardian has activated, the higher the probability of getting drafted.

## Plurality rule

Unlike traditional courts, Aragon Court guardians are not asked to rule impartially on disputes but instead are asked **to rule the way they expect the plurality of guardians to rule.** Aragon Court attempts to find what the subjective truth is (i.e. the most correct outcome of a dispute) with a [Schelling point](https://en.wikipedia.org/wiki/Focal\_point\_\(game\_theory\)). Every time a guardian is drafted for a dispute, a portion of their activated tokens is locked until the dispute is finalized. To incentivize consensus, guardians who don’t vote in favor of the final ruling have their locked tokens slashed. Guardians who vote in favor of the final ruling are rewarded with dispute fees and tokens from any guardians who voted for a minority ruling.

## Proof of stake

Aragon Court is a **permissionless protocol** where any participant can come and go without asking for anyone's authorization. Therefore, the protocol must function with integrity even in the presence of malicious actors, who may pose as multiple guardians at once to "Sybil attack" the Court. The defense against these attacks begins with a simple **staking system where guardian impact is weighted by their active stake of tokens**.

You may be thinking that if a cartel gets a majority of tokens, they'll have a majority weight and attack the system unopposed since they'll influence more than 50% of the decisions. Aragon Court, however. uses multiple countermeasures including iterative appeals, commit and reveal voting, and locked withdrawal periods that are designed to dissuade a cartel from acquiring tokens and abusing Aragon court.

## Guardian responsibilities

Guardians are expected to perform certain duties and responsibilities, like reviewing arguments for a dispute and casting a vote. To help guardians properly execute their tasks, the Aragon Court Dashboard is available and provides all the tools they need.

{% hint style="info" %}
You can learn more about the Dashboard [here](court-dashboard.md) and the details of dispute resolution here.
{% endhint %}
