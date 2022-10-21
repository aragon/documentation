# Security notice for organizations created before Aragon 0.8

[Changes](https://github.com/aragon/aragonOS/issues/549) in the consensus rules of the Ethereum network, which were activated with the Istanbul hard fork, have broken key functionality in the way pre-0.8 versions of the Aragon smart contracts handle ETH deposits from other smart contracts.

The result is that after the Istanbul hard fork (occurred on December 7, 2019), ETH deposits sent from a smart contract to pre-0.8 Aragon smart contracts will fail, and the transaction will revert. **In some cases, this could lead to a permanent loss of funds.** Additionally, certain functionality will be broken, leading to a bad experience for users of Aragon organizations.

Organizations created after the release of Aragon 0.8 will automatically have a fix for this issue, and no further action is needed.

<mark style="color:red;">**Organizations created before the release of Aragon 0.8 (September 11, 2019) are advised to migrate their assets and members to a new Aragon organization**</mark> created using post-0.8 versions of Aragon contracts.

You can create your new organization at [app.aragon.org](https://app.aragon.org), configure the permissions of the new organization to mirror the old organization, then transfer membership, funds, and other assets to the new organization, and pick up where you left off.

For more details, read [this post](https://blog.aragon.org/istanbul-hard-fork-impact/) on the Aragon project blog.
