# Templates

{% hint style="success" %}
<mark style="color:blue;">**Create templates**</mark> for easy DAO setup.
{% endhint %}

## How does it work?

Creating a DAO with all the desired apps and permissions requires multiple operations that must be properly orchestrated. In the context of Ethereum, performing all these operations would require sending many transactions. This would not only be very costly, as every transaction needs to pay for gas, also the integrity of the deployment depends on all operations occurring in the right order.

For these reasons, the **recommended way of creating Aragon DAOs** is using what we call **templates**, on-chain _deployment scripts_ that create a DAO and perform all the required configuration steps in an **atomic manner** without the possibility of an attacker interacting with the DAO while it is still being set up. **Templates allow creating a DAO in just one transaction** and when the transaction is processed the DAO is already **fully configured and functional**.

Templates can also be thought of as **DAO templates** as every template can **create a DAO** with **specific settings** for an organization type.&#x20;

The two DAO configurations that one can choose from when using the [Aragon client](https://client.aragon.org/) correspond to the beta templates ([Democracy](https://github.com/aragon/dao-templates/blob/ce62d132d944951dc200df8aa74e42db8e70a094/kits/democracy/contracts/DemocracyKit.sol) and [Multisig](https://github.com/aragon/dao-templates/blob/ce62d132d944951dc200df8aa74e42db8e70a094/kits/multisig/contracts/MultisigKit.sol)) available in the [DAO templates repository](https://github.com/aragon/dao-templates).

{% hint style="danger" %}
The above Democracy and Multisig `kits` have been deprecated and `templates` should now be used instead. You may still find the `kits` notation in some places while we make the transition.
{% endhint %}

## Environment setup <a href="#environment-setup" id="environment-setup"></a>

Before starting you need to check if you have already installed all these prerequisites:

* the right version of **node.js** (recommended `v12 LTS` version)
* **Metamask** web3 provider
* the **aragonCLI** (Aragon Command Line Interface)&#x20;
* the **Aragon Buidler plugin**

If you haven't already installed them or if you need more info about this go to the "_Environment Setup_" paragraph [here](getting-started.md).

## Getting started with templates using the aragonCLI

Now we are ready to build our DAO with the templates.

The [aragonCLI](../aragoncli/) (>= v4.1.0) supports using templates to create a DAO to interact with the apps being developed.

To quickly get started developing your own templates:

```
npx create-aragon-app app
```

That command will create a new Aragon app project. A sample template for this [Counter example app ](../guides/your-first-aragon-app.md)can be found here in [`Template.sol`](https://github.com/aragon/aragon-cli/blob/ff99addc784a261608b66c269c0292891da5a311/packages/cli/test/mock/contracts/Template.sol)

Import this in the app under the `contracts` folder. Then install the `@aragon/templates-shared` package which contains contract, deployment, and testing utilities to help you build your own template.

Then to run your DAO enter:

```
cd app
yarn start
```

When modifying the name of your contract or app name be sure to update those in `Template.sol` otherwise running the template will fail.

{% hint style="info" %}
The client should load within few minutes. In case of not, please terminate it and then restart it.&#x20;
{% endhint %}

## Template structure <a href="#template-structure" id="template-structure"></a>

All templates follow a similar structure:

1. Use a [DAOFactory](https://github.com/aragon/aragonOS/blob/4.0.1/contracts/factory/DAOFactory.sol) to create a DAO.
2. Assign the template contract the necessary permissions in the DAO needed for installation (usually only `APP_MANAGER_ROLE`).
3. Create app proxy instances for all the apps (`dao.newAppInstance(...)`).
4. Initialize apps (`app.initialize(...)`).
5. Set up permissions for the apps and the DAO.
6. Clean up the permissions temporarily assigned to the template.

