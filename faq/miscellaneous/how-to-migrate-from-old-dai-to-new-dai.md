# How to migrate from "old" DAI to "new" DAI

The DAI token, managed by [MakerDAO](https://makerdao.com), was migrated to use another token address at 16:00 UTC on 2019-11-18.

You can read more about the specific details of the migration on [MakerDAO's blog](https://blog.makerdao.com/multi-collateral-dai-is-live/).

* The old DAI token at _0x89d24a6b4ccb1b6faa2625fe562bdd9a23260359_ now becomes **SAI**.
* The new **Multi-Collateral DAI** token contract is _0x6b175474e89094c44da98b954eedeac495271d0f_

A migration tool between SAI and DAI is available at [migrate.makerdao.com](https://migrate.makerdao.com).

For any organizations holding the "old" DAI (aka SAI) token, the Aragon client has begun showing the correct name following a release around 2019-11-25.

For organizations holding SAI, there are two recommended paths to upgrade to Multi-Collateral DAI:

* Transfer the SAI into an external account or multisig contract that you control. From there, use the migration interface at [migrate.makerdao.com](https://migrate.makerdao.com) to exchange SAI into DAI, and deposit the new DAI back into your organization
* Install an [Agent app](../../products/aragon-client/explore-template-dao/what-are-apps/agent-app/), if your organization has not yet installed one. Transfer SAI into the Agent app, set up the required permissions to allow interactions with the Agent app, and use [migrate.makerdao.com](https://migrate.makerdao.com) via [Frame](https://frame.sh).

For organizations holding old SAI Collateralized Debt Position (CDPs), the recommended migration paths are similar if the organization was only holding SAI: transfer the organization's SAI CDP ownership to an external account, multisig, or installed Agent app that you can interact with, and use the [migrate.makerdao.com](https://migrate.makerdao.com) interface. In this scenario, ensure that the account with ownership over the SAI CDP also holds enough $MKR to pay back any owed stability fees.

Organizations that want to create new DAI Vaults should interact with the Oasis Trade application using an installed Agent app and Frame.
