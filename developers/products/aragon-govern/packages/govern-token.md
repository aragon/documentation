# govern-token

{% hint style="danger" %}
**WARNING**

Aragon Govern is **beta software** which is **NOT MAINTAINED** anymore. It's a really cool product though with innovative and nifty smart contracts. So although you might run into an **error** 🐲 here and there, the documentation is definitely worth the read and the play!

And welcome to connect with us through [Discord](https://discord.gg/thyHMDt) or our technical [forum](https://support.aragon.org/c/dev-support/20)!
{% endhint %}

## Govern Token

This package contains the contracts for Token.

## Configuration

First, run `yarn` to install all the dependencies, if it hasn't been run before for any other package.

Then, create the `.env` file in the root directory of this package and include those:

* `PRIVATE_KEY=YOUR_PRIVATE_KEY`

`PRIVATE_KEY` is necessary to make sure you can deploy contracts.

## Deployment

* `yarn deploy` deploys `GovernTokenFactory` contract.
* `yarn deploy-token` deploys the actual token. To know which arguments to pass in (such as name, symbol, e.t.c.), see `tasks/token.js`
