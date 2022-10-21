---
description: Get up and running quickly with Govern as a Developer.
---

# Getting started

{% hint style="info" %}
The Govern project consists of several **sub-projects** interacting with each other. The Aragon Govern product can be found here: [https://govern.aragon.org/](https://govern.aragon.org/)
{% endhint %}

## Contracts

The contracts are split in two projects: [`erc3k`](../../packages/erc-3k.md) (the interfaces defining the ERC3000 standard), and [`govern-core`](../../packages/types.md) (the Aragon Govern contracts, implementing ERC3000).

Relevant packages:

* [`erc3k`](../../packages/erc-3k.md): ERC3000 interfaces.
* [`Govern Core`](../guides/govern-core-concepts.md): Aragon ERC3000 implementation.
* [`Govern Create`](../../packages/govern-create.md): Set of templates used to create new Govern instances.
* [`Govern Contract Utils`](../../packages/govern-contract-utils.md): Set off libraries and utilities used by the Govern contracts.

## Govern Console

The Aragon Govern Console is a no-frills, forkable, extensible power user / developer UI tool for interacting with and visualizing low level information about Govern DAOs.

![The Aragon Govern Console](https://user-images.githubusercontent.com/36158/97722356-77c04900-1ac2-11eb-8a5c-5034a54cdbb4.png)

Relevant packages:

* ``[`Govern Console`](../../packages/govern-console.md).

## Govern Server and Govern.js

**Govern Server** acts as a central point, fetching data from different sources (Ethereum, the Govern subgraph, IPFS) and providing it as a unified API to consumers.&#x20;

You can use it through the Govern.js library, or through its GraphQL API. It is powered by [The Graph](https://thegraph.com/).

![Govern Server and how it relates to the other projects](https://user-images.githubusercontent.com/36158/97721073-e9979300-1ac0-11eb-9373-e007d4e6ce2c.png)

Relevant packages:

* [`Govern.js`](../../packages/govern.js.md)
* [`Govern Server`](../../packages/govern-server.md)
* [`Govern Subgraph`](../../packages/govern-subgraph.md)

{% hint style="danger" %}
**WARNING**

Aragon Govern is **beta software** which is **NOT MAINTAINED** anymore. It's a really cool product though with innovative and nifty smart contracts. So although you might run into an **error** 🐲 here and there, the documentation is definitely worth the read and the play!

And welcome to connect with us through [Discord](https://discord.gg/thyHMDt) or our technical [forum](https://support.aragon.org/c/dev-support/20)!
{% endhint %}

## Run Aragon Govern Console locally:

{% hint style="danger" %}
The recommended Node version to run this is: **`node v14.`** You might run into unwanted errors with a lower or higher version.
{% endhint %}

Start by cloning the Govern repository on your local machine:

```
git clone https://github.com/aragon/govern.git
```

The continue by bootstrapping the entire monorepo with `yarn`:

```
cd govern
yarn
```

{% hint style="danger" %}
The `yarn` command might give a: `gyp ERR! build error.`The next step should work however.
{% endhint %}

This will install all needed dependencies, and link all packages together to make sure you're using the local version of each one. Now it's time to install dependencies of the `@aragon/govern` package and to create a build:

```
cd packages/govern
yarn
yarn build
```

Now we are prepared to give Govern Console a run:

```
cd ..
cd govern-console
yarn
```

{% hint style="danger" %}
No to prevent a 'babel version error' from happening, create a `.env` file in the root of the `govern-console` folder, add the following line and then save the file:

`SKIP_PREFLIGHT_CHECK=true`
{% endhint %}

Now we are really ready to spin up the `@aragon/govern-console` package:

```
yarn start
```

{% hint style="success" %}
It is time to call out your victory :tada:, if you see a page like the below appear in your browser:
{% endhint %}

![](<../../../../../.gitbook/assets/Screenshot 2022-07-04 at 17.09.02.png>)
