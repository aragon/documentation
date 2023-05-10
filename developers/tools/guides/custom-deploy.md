# How to create your first custom DAO using Aragon CLI!

{% hint style="info" %}
This guide will show you the process to deploy a **blank DAO** using Aragon CLI and configure it as a **custom DAO** for a cooperative organisation, let's say a cooperative of dairy farmers.

We assume you have a general understanding of Aragon stack.
{% endhint %}

## Environment setup <a href="#environment-setup" id="environment-setup"></a>

Before starting you need to check if you have already installed all these prerequisites:

* the right version of **node.js** (recommended `v12.7 LTS` version)
* web3 provider: [Frame](how-to-sign-with-web3-providers/setting-up-a-frame-wallet/) or [Metamask](how-to-sign-with-web3-providers/set-up-metamask/) (Frame is necessary for this guide).
* the **aragonCLI** (Aragon Command Line Interface)&#x20;
* an [IPFS server.](https://docs.ipfs.io/install/)

{% hint style="info" %}
If installing IPFS on Linux, it can be easily done with: `sudo snap install ipfs`
{% endhint %}

If you haven't already installed them or if you need more info about this goes to the "_Enviroment Setup_" paragraph [here](../the-basics/getting-started.md).

### Creating a blank DAO <a href="#creating-a-blank-organization" id="creating-a-blank-organization"></a>

{% hint style="danger" %}
**Warning**

Installing Frame is necessary for this step. Read [here](how-to-sign-with-web3-providers/setting-up-a-frame-wallet/) how to setup a Frame wallet. Select 'RINKEBY' network and make sure you open your new account (unfold it) in Frame for the transaction to appear.
{% endhint %}

Let's create a blank DAO! Insert and run the following command in your terminal:

```
 dao new --use-frame --env aragon:rinkeby
```

In the Frame app now a 'permission request' from aragonCLI should show up. 'Sign' the request.

After this a transaction to create the DAO should show up in Frame, also 'sign' this transaction:



![](<../../../.gitbook/assets/Screenshot\_2022-04-27\_at\_23\_08\_37 (1).png>)



{% hint style="warning" %}
**Hint**

Make sure you have sufficient Rinkeby Ethereum (ETH) in your wallet for the transaction fees. If not you can request for Rinkeby ETH [here](https://faucets.chain.link/). The transaction could take long. Increase the 'gas fees' to speed up the transaction.
{% endhint %}

{% hint style="success" %}
Well done you just created your first DAO! You should now be able to open the DAO on: `https://client.aragon.org/#/<dao-address>`
{% endhint %}

Find the DAO address in the terminal, and make sure you select the 'Rinkeby' network in Aragon Client for your DAO to load (since Ethereum mainnet is default). You can change to Rinkeby network from here in the top right hand corner: [https://client.aragon.org/#/](https://client.aragon.org/#/)

The DAO was created with the default [`bare-template`](https://github.com/aragon/dao-templates/blob/master/templates/bare/contracts/BareTemplate.sol). So it won’t have a token manager, vault, finance, or voting app installed yet.

{% hint style="info" %}
**Note**\
The `bare-kit` has been deprecated and `bare-template` should be used instead. To learn more about templates check the[ introduction about them](../the-basics/templates.md).

The above command used the `--use-frame` and `--env` flags. You can find other possible flags [here](../aragoncli/dao-commands.md#dao-new), or by adding the `--help` flag to the command.&#x20;
{% endhint %}

### Adding a Token and Token Manager to your DAO <a href="#adding-a-token-and-token-manager-instance" id="adding-a-token-and-token-manager-instance"></a>

Next we will add a token and a token-manager to your DAO. The following types of tokens can be created:

* `Membership`: a non-transferrable token limited to 1 per account.
* `Reputation`: a non-transferrable token without balance restriction.
* `Equity`: a transferrable token without balance restriction.

For the dairy cooperative we want to start with a membership token: one farmer, one member.

First we need to deploy a MiniMe token. The `dao new token` command takes the following variables:

```
dao token new <token-name> <symbol> [decimal-units] [transfer-enabled]
```

{% hint style="info" %}
**Note**

The [MiniMeToken](https://github.com/Giveth/minime) contract is a standard ERC20 token with extra functionality.
{% endhint %}

For our membership token we take `"Member"` as  `token-name`, with `"MBR"` as `symbol`.

We want to set `decimal-units` to `0` (the default is `18`).

The default of `tranfer-enabled` is `true`. By leaving `transfered-enabled` out of the command it takes the default value automatically, which is good for now since we will restrict transferability using the token-manager in a later step.

{% hint style="danger" %}
**Warning**

For the next step it is necessary to start an instance of **Aragon Devchain**. To do so open up an new tab or window in your terminal and run the following command:

`aragon devchain --env aragon:rinkeby`
{% endhint %}

So now run the following command in your terminal:

```
dao token new "Member" "MBR" 0 --use-frame --env aragon:rinkeby
```

Copy the **token address** from the terminal as we will need it later!

Next we need to deploy an instance of the **token-manager** app which will serve as the token-controller for the membership token we just created.

{% hint style="info" %}
**Note**

The token-manager cannot be initialized unless it's already the controller of a MiniMe token. So in this case we want to use the `dao install` command with the `--app-init none` flag. In that way we can perform some actions before we initialize the token-manager. Read more about this [flag](../aragoncli/dao-commands.md#dao-install) here.
{% endhint %}

Insert the DAO address in the below command and run it in your terminal:

```
dao install <dao-address> token-manager --app-init none --use-frame --env aragon:rinkeby
```

In order to get the token-manager address we need to run the following command:

```
dao apps <dao-address> --all --use-frame --env aragon:rinkeby
```

You should see a list of apps, and a token-manager instance listed under permissionless apps. Copy this address as we will need it later.

Next are going to set the token-address as the token-controller on our token, by running the following command:

```
dao token change-controller <token-address> <token-manager-address> --use-frame --env aragon:rinkeby
```

Now we are creating a `MINT_ROLE` permission for the token-manager so more farmers can be added as members to the dairy-DAO at a later point in time. Run the following command:

```
dao acl create <dao-address> <token-manager-address> MINT_ROLE <your-address> <your-address> --use-frame --env aragon:rinkeby
```

{% hint style="danger" %}
**Warning**

Make sure you do not accidentally include multiple spaces instead of 1 space between each variable in the command. Since if you do, you will run into this error:

`✖ Not enough non-option arguments: got 4, need at least 5`
{% endhint %}

We can now initialize the token manager using the `dao exec` command. The token-manager’s initialise function takes 3 parameters:

1. `minime token`: token-address of a MiniMe token.
2. `transferrable`: a boolean indicating if the token should be transferrable or not.
3. `uint`: determining max number of tokens an address can control (use `0` if you do not want to restrict balances).

{% hint style="info" %}
**Note**

You can find more info about `dao exec` commands [here](../aragoncli/dao-commands.md#dao-exec).
{% endhint %}

We would not like dairy farmers to transfer their membership tokens, so we set the boolean to `false`. Then we want one address to control a maximum of 1 membership token, so the `unit` will be set to `1`. Insert the data of the variables in the below command, and run it in your terminal:&#x20;

```
dao exec <dao-address> <token-manager-address> initialize <token-address> false 1 --use-frame --env aragon:rinkeby
```

At this point if you open your DAO in a web browser you should be able to see the [token manager app installed](https://documentation.aragon.org/products/aragon-client/explore-template-dao/what-are-apps/token-app), and should be able to mint tokens from `your-address`. Open your DAO UI from here: `https://client.aragon.org/#/<dao-address>`



![](../../../.gitbook/assets/Screenshot\_2022-04-28\_at\_22\_23\_26.png)

{% hint style="danger" %}
**Warning**

Even though we have initialized the token manager as `transferrable = false`, and token transfers fail, there is what appears to be a UI bug where the token manager will list the token as transferrable even though it is not. [GitHub issue](https://github.com/aragon/aragon-apps/issues/630).
{% endhint %}

### Adding a Voting App to your DAO <a href="#adding-a-voting-instance" id="adding-a-voting-instance"></a>

Adding a [voting-app](https://documentation.aragon.org/products/aragon-client/explore-template-dao/what-are-apps/voting-app) allows actions to be protected by a vote. This to ensure that the required support and quorum is reached in case of changes to your DAO. The dairy-DAO might want to transfer control to another member, such as change can then only be executed when the required majority of members is met.

Since we already have a token and token-manager deployed all we have to do is install the voting-app. This can be done in one step using the `dao install` command and passing arguments via `--app-init-args`.

The voting-app requires the following initialization parameters:

* `minime token`: token-address of a MiniMe token.
* `support required percentage`: percentage of yeas in casted votes for a vote to succeed (expressed as a percentage of `10^18`; eg. `10^16 = 1%`, `10^18 = 100%`).
* `min accept quorum`: percentage of yeas in total possible votes for a vote to succeed (expressed as a percentage of `10^18`; eg. `10^16 = 1%`, `10^18 = 100%`).
* `vote time`: seconds that a vote will be open for token holders to vote (unless enough yeas or nays have been cast to make an early decision).

So if we want a voting-app instance with a support requirement of 60% and min accept quorum of 25% and a voting period of 7 days we would use the following command. Run the command in your terminal:

```
dao install <dao-address> voting --app-init-args <token-address> 600000000000000000 250000000000000000 604800 --use-frame --env aragon:rinkeby
```

Next you will need to assign the create votes permission. If you want all token holders to be able to create votes, we can assign the `CREATE_VOTES_ROLE` to the `token-manager-address`.

The following command grants token holders (so all members of the dairy-DAO) the ability to create votes. Also from now a vote will be required to manage changes to the permissions. Run the command:

```
dao acl create <dao-address> <voting-app-address> CREATE_VOTES_ROLE <token-manager-address> <voting-app-address> --use-frame --env aragon:rinkeby
```

At this point you should be able to open your organization in the browser and be able to create votes! :clap:

{% hint style="info" %}
**Note**

You can find more info about `dao acl` commands [here](../aragoncli/dao-commands.md#dao-acl).
{% endhint %}

### Adding a Vault and Finance App <a href="#adding-a-vault-and-finance-instance" id="adding-a-vault-and-finance-instance"></a>

{% hint style="info" %}
**Note**

The **vault-app** is intended to securely store and manage funds but does not have its own user interface (UI). The [**finance-app**](https://documentation.aragon.org/products/aragon-client/explore-template-dao/what-are-apps/finance-app) provides an interface for the vault-app and provides some limited budgeting capabilities. In the future, it may make sense to install the vault app without the finance app, or the finance app with a different version of the vault app, but for now these two apps generally make sense to install as a pair.
{% endhint %}

The vault-app can be installed without passing any specific initialization parameters. Run the following command in the terminal:

```
dao install <dao-address> vault --use-frame --env aragon:rinkeby
```

Copy the provided `vault-address` from the terminal, which will be needed later.



The finance-app however requires two initialization parameters:

1. `vault-address.`
2. `budgeting period` (in seconds).

If you are familiar with the finance-app in the UI, you may have noticed that there is not way to configure or set a budget. However, the smart-contracts allow you to set a per-asset budget which is reset each time period.

Eventually the UI will be updated to support these functions. If you don’t intend to use any of the budgetting functionality the budget period parameter doesn't matter but it does need to be passed. If you do plan on using the budgeting functionality however here is how it works:

> For a given budget period _P_, a budget _B_ can be set for asset _A_. The total volume of transfers of _A_ cannot exceed its budget within a period _P_. So for example, if we initialize _P_ as 1 Month, we could set a budget for DAI of 1000, and even if the vault contains more than 1000 DAI it will not be able to spend more than 1000 DAI per month. Keep in mind that the budget cannot be seen from the UI, so transactions which exceed the budget will just fail.

For demonstrations purposes, let's set install the finance-app with a budget period of 30 days (in seconds). Run the following command:

```
dao install <dao-address> finance --app-init-args <vault-address> 2592000 --use-frame --env aragon:rinkeby
```

Now we want to create a permission that grants the finance-app the `TRANSFER_ROLE` on the vault. For future possible changes we will also make voting required. Run the following command to do so:

```
dao acl create <dao-address> <vault-address> TRANSFER_ROLE <finance-address> <voting-address> --use-frame --env aragon:rinkeby
```

We also want to grant some permissions to the voting app on the finance-app. In that way voting will be required do the dairy-DAO members wish to make changes to the roles. Run the follwoing commands in the terminal:

```
dao acl create <dao-address> <finance-address> CREATE_PAYMENTS_ROLE <voting-address> <voting-address> --use-frame --env aragon:rinkeby

dao acl create <dao-address> <finance-address> EXECUTE_PAYMENTS_ROLE <voting-address> <voting-address> --use-frame --env aragon:rinkeby

dao acl create <dao-address> <finance-address> MANAGE_PAYMENTS_ROLE <voting-address> <voting-address> --use-frame --env aragon:rinkeby
```

For more information on what each of these roles do as well as additional roles made available by the finance-app, see the [repository](https://github.com/aragon/aragon-apps/blob/87b55951fcd83e4aefcc49f616fa2417743836c3/apps/finance/arapp.json).

{% hint style="success" %}
At this point you should be able to open your custom DAO in the web browser and manage tokens, create votes, and manage funds using  the vault and finance apps! :tada:
{% endhint %}

### Review & Finalize Permissions <a href="#review-finalize-permissions" id="review-finalize-permissions"></a>

While we have a mostly functional dairy-DAO [the permissions](https://documentation.aragon.org/products/aragon-client/explore-template-dao/system-setting/permissions-setting) need to be cleaned up because we do not want our personal address to have root authority in the organization. These steps can be done from the permissions UI (see image below), or directly from Aragon CLI.



![](<../../../.gitbook/assets/Screenshot 2022-05-04 at 16.28.04.png>)

To see what permissions are currently assigned, run the following `dao acl` command:

```
dao acl <dao-address> --use-frame --env aragon:rinkeby
```

You will notice that some key permissions have been granted and are managed by the address you used to perform these commands. By following these steps you are transferring authority as creator of the organization to other applications and entities defined above,&#x20;

{% hint style="danger" %}
Warning

Transferring permissions is an irreversible process, so be careful not to revoke a permission before granting it to an appropriate entity!
{% endhint %}

You’ll want to grant permissions which are currently only assigned to your address to another entity (eg. `voting-address`):

```
dao acl grant <dao-address> <app-address> <ROLE> <voting-address> --use-frame --env aragon:rinkeby
```

You’ll want to revoke permissions for yourself once they have been granted to another entity:

```
dao acl revoke <dao-address> <app-address> <ROLE> <your-address> --use-frame --env aragon:rinkeby
```

You’ll want change the permission manager for permissions from your address to another entity (eg. `voting-address`):

```
dao acl set-manager <dao-address> <app-address> <ROLE> <voting-address> --use-frame --env aragon:rinkeby
```

{% hint style="success" %}
At this point you should have changed permissions. Well done you successfully set up a custom DAO for the dairy-farmers cooperation. Let's toast to that! :cow::milk::milk::cow:
{% endhint %}

