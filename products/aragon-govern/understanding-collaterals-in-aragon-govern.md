# Collateral for scheduling or challenging a transaction. Why?

{% hint style="info" %}
In this section, you will learn about collateral and why it is necessary to schedule or challenge a transaction.
{% endhint %}

To provide additional **security**, all transactions may be challenged before execution. When a given transaction is challenged, a dispute is created in [Aragon Court ](../aragon-court/)(or any dispute resolution system that is compliant with ERC-3k), and guardians will be summoned to arbitrate the case.

To make sure that not only this process, but also the process of scheduling transactions in the DAO is not abused both the transaction creator as well as the person challenging the transaction needs to provide collateral.

If the dispute is ruled in favor of the original transaction creator the person who created the transaction will get the collateral tokens from the challenger. If the transaction is blocked (e.g. the dispute is ruled in favor of the challenger), then the challenger gets the collateral tokens from the transaction creator.

Collaterals make sure members have skin in the game when interacting within an optimistic governance model and will be less likely to abuse it. Collaterals also allow DAO creators to restrict transaction and challenge creation to specific token holders so that only certain individuals who hold a specific token create transactions to begin with.
