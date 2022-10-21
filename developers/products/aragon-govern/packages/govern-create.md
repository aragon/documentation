# govern-create

{% hint style="danger" %}
**WARNING**

Aragon Govern is **beta software** which is **NOT MAINTAINED** anymore. It's a really cool product though with innovative and nifty smart contracts. So although you might run into an **error** 🐲 here and there, the documentation is definitely worth the read and the play!

And welcome to connect with us through [Discord](https://discord.gg/thyHMDt) or our technical [forum](https://support.aragon.org/c/dev-support/20)!
{% endhint %}

## Govern create

This package contains the factory contracts:

* `GovernFactory`
* `GovernQueueFactory`
* `GovernBaseFactory`

## Configuration

First, run `yarn` to install all the dependencies.

Then, create the `.env` file in the root directory of this package and include those:

* `ETHERSCAN_KEY=YOUR_ETHERSCAN_API_KEY`
* `PRIVATE_KEY=YOUR_PRIVATE_KEY` (depending on the network, update this value for the corresponding private key)

If you don't want to verify contracts on etherscan right away after deploying the contracts, you can omit `ETHERSCAN_KEY` from the `.env` config.

## Deployment

After the configuration step is done, you can run `yarn deploy`.
