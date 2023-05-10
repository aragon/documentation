# Introduction

## **Upgradeability**&#x20;

{% hint style="info" %}
**Upgradeability** is one of the key features of [aragonOS](../aragonos/).
{% endhint %}

Because upgradeability implies there will be multiple versions of a package of software, we decided to build aragonPM as the main way to **distribute different versions of the packages** that comprise the Aragon client. As we built it, however, we realized that its use cases could extend far beyond just ours as a publicly accessible piece of infrastructure living on Ethereum.

A package or **repository** (repo) in an aragonPM registry keeps track of evolving versions of its contents (the webapp component typically) and smart contract code (if applicable).

## aragonPM as an Aragon DAO <a href="#aragonpm-as-an-aragon-dao" id="aragonpm-as-an-aragon-dao"></a>

aragonPM is built on top of [aragonOS](https://hack.aragon.org/docs/aragonos-intro.html). It is a Decentralized Autonomous Organization (DAO) running on the same Aragon that‘s used to build Aragon organizations (to take advantage of upgradeability and access control)!

This allows for many aragonPM registries to exist with different governance models for package creation and publishing new versions. There is an official Aragon curated instance, `aragonpm.eth`, which has high-quality standards and strict restrictions on what can get published, that we use for publishing our core components.

Different aragonPM registries in which everyone can publish their packages are expected to be created by the community, and we have set up `open.aragonpm.eth` on both the main and Rinkeby networks as an open instance available for anyone to publish to.

{% hint style="info" %}
To get more experience with creating a custom DAO from the command line (aragonCLI), installing apps on a custom DAO, building and publishing your own apps on aragonPM, follow one of the below guides **👇**.
{% endhint %}

### Guides <a href="#guides" id="guides"></a>

1. [Learn how to build your first app](../guides/your-first-aragon-app.md), so you can publish it onto an aragonPM registry
2. [Publish your application onto an aragonPM registry with the CLI](../guides/publish-to-aragonpm.md)
3. [Guide others to install your app from an aragonPM registry](../guides/custom-deploy.md), and finally,
4. [Submit your app to the Aragon Client's App Center](../app-center/submitting-your-app-to-the-app-center.md)

