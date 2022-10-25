# What is Aragon Voice?

[**Aragon Voice**](https://voice.aragon.org) is a new and universally verifiable voting solution that doesn't require the payment of the gas fees (it is gasless). Using Aragon Voice it is possible to submit proposals with any [standard ERC20](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/) token and vote on the proposals using a decentralized end-to-end verifiable protocol.

Aragon Voice is **free to use**, meaning that no one is priced out of participation. Full transparency removes any doubt about the integrity of the ballot, meaning that communities are more likely to view ballots as unbiased and run fairly.

With Aragon Voice even the most humble token holder will be empowered to **propose** changing the exchange fee on a Balancer Pool and directly contributing to the development of their favorite project.

## Anyone with an Ethereum address can:

* Design and implement **on-chain proposals** for their ERC20 project, where **votes** can be cast **without gas fees**, and are recorded as metadata on IPFS.
* Signal proposals that use a centralized backend but are universally verifiable\* on our custom vote-counting blockchain (Vochain).

> \* from process creation to vote recount, every operation is transparent and can be freely audited by a third party. Voters themselves can also check that their vote has been counted properly using their ballot receipt to query the [Vochain explorer](https://explorer.vote).

{% hint style="warning" %}
Only on-chain proposal creators need to pay the gas costs of deploying the information to the mainnet. The votes are cast without gas fees.
{% endhint %}

Proposals are processed on Vochain (Aragon's layer 2 protocol) and vote metadata is stored on IPFS.

## **Vocdoni OpenStack**

To power Aragon Voice, we are using the Vocdoni OpenStack: **a fully anonymous voting protocol by design, ensuring data availability and censorship-resistant protocol communication**.

This technology is also the base for Vochain, a layer-2 (L2) voting-specific blockchain, used for accounting ballots transparently.

The result is a completely permissionless, decentralized, and highly scalable governance solution for DAOs and other initiatives that make use of ERC20 tokens.

{% hint style="info" %}
Aragon Voice can be used for permissionless signaling, dispute resolution and deterministic on-chain execution when combined with Aragon Court and Aragon Govern.
{% endhint %}
