# DAO commands

{% hint style="info" %}
The `aragon dao` commands can be used for <mark style="color:blue;">interacting with your DAO</mark> directly from the command line. These commands are also available directly using the `dao` alias.
{% endhint %}

{% hint style="warning" %}
**Note**\
The default mnemonic of the Aragon CLI is the same for all users. If you are going to deploy a DAO to public networks it is highly recommended that you use your own web3 provider. Instructions on that can be found [here](../guides/troubleshooting-and-faq.md) (scroll down to 'Set a private key').
{% endhint %}

## dao new <a href="#dao-new" id="dao-new"></a>

Uses a DAO Template to create a new DAO and prints its address.

```
dao new
```

Options:

* `--environment`: The environment in your `arapp.json` that you want to use. Defaults to `aragon:local`. Check the other [default environments](global-configuration.md). You can also use it with the `--env` alias.
* `--use-frame`: Use Frame as a signing provider and web3 provider.
* `--aragon-id`: Assigns an Aragon Id to the DAO.
* `--template`: The aragonPM repo name of the template that is used to create the DAO. Defaults to `bare-template.aragonpm.eth`.
* `--template-version [version-number|latest]`: The version of the repo that will be used to create the DAO. Defaults to `latest`.
* `--fn`: The function on the template that is called to create a new DAO. Defaults to the `newInstance` function for `bare-template.aragonpm.eth`.
* `--fn-args`: The arguments that the function to create the template is called with. Defaults to an array of arguments. To use arrays use the following format `["'0xB24b...73a7', '0xB24b...73a7'"]`.
* `--deploy-event`: The name of the event that is emitted when the DAO is created. The DAO address must be a return argument in the event log named `dao`. Defaults to `DeployDao`.
* `--ipfs-check`: Whether to have start IPFS if not started. Defaults to `true`.

## dao apps <a href="#dao-apps" id="dao-apps"></a>

Used to inspect all the installed apps in a DAO.

```
dao apps <dao-addr>
```

* `dao-addr`: The main address of the DAO (Kernel).

Options:

* `--all`: To include apps without permissions in the report.

## dao id assign <a href="#dao-id-assign" id="dao-id-assign"></a>

Assigns an Aragon Id to a DAO address.

```
dao id assign <dao> <aragon-id>
```

or

```
dao id <dao> <aragon-id>
```

* `dao`: The main address of the DAO (Kernel).
* `aragon-id`: The Aragon Id.

## dao install <a href="#dao-install" id="dao-install"></a>

The `dao install` command installs an instance of an app in the DAO.

```
dao install <dao-addr> <app-apm-repo> [repo-version]
```

* `dao-addr`: The main address of the DAO (Kernel).
* `app-apm-repo`: The repo name of the app being installed (e.g. `voting` or `voting.aragonpm.eth`).
* `repo-version`: (optional) Version of the repo that will be installed; can be a version number or `latest` for the newest published version. Defaults to `latest`.

In [aragonOS](../aragonos/reference-documentation.md#app-installation) an app is considered to be installed in a DAO if it uses the DAO Kernel as its Kernel and there are references to the app in the ACL of the DAO.

The `dao install` command will create an instance of the app and assign permissions to the main account to perform all the protected actions in the app.

Options:

* `--app-init`: Name of the function that will be called to initialize an app. If you want to skip app initialization (which is not generally recommended), you can do it by set it to `none`. By default it will initialize the app using `initialize` function.
* `--app-init-args`: Arguments for calling the app init function. To use arrays use the following format `["'0xB24b...73a7', '0xB24b...73a7'"]`.
* `--set-permissions`: Whether to set permissions in the app. Set it to `open` to allow `ANY_ENTITY` on all roles.

{% hint style="warning" %}
**Note**\
All app instances of the same app in a DAO must run the same version, so installing an app with a version will effectively upgrade all app instances to this version.
{% endhint %}

## dao upgrade <a href="#dao-upgrade" id="dao-upgrade"></a>

The `dao upgrade` command upgrades all instances of an app to a newer version.

```
dao upgrade <dao-addr> <app-apm-repo> [repo-version]
```

* `dao-addr`: The main address of the DAO (Kernel).
* `app-apm-repo`: The repo name of the app being upgraded (e.g. `voting` or `voting.aragonpm.eth`).
* `repo-version`: Version of the repo that the app will be upgraded to; can be a version number or `latest` for the newest published version (defaults to `latest`).

aragonOS protects against having different instances of a particular app running with different versions (e.g. all the Voting app instances run the same version). Performing a `dao upgrade` will upgrade all instances of the app to the version specified.

## dao exec <a href="#dao-exec" id="dao-exec"></a>

Performs transactions in your DAO directly from aragonCLI. It supports [transaction pathing](../the-basics/forwarding.md) so if your account cannot perform the action directly it will try to find how to do it (e.g. creating a vote).

```
dao exec <dao-addr> <app-proxy-addr> <method> [argument1 ... argumentN]
```

* `dao-addr`: The main address of the DAO (Kernel).
* `app-proxy-addr`: The address of the app where the action is being performed. You can find the proxy address by checking [`dao apps`](https://hack.aragon.org/docs/cli-dao-commands#dao-apps).
* `method`: Name of the method being executed in the app (e.g. `withdrawTokens`).
* `arguments`: The arguments that the method will be executed with (each separated by a space).

## dao act <a href="#dao-act" id="dao-act"></a>

Provides some syntax sugar over `dao exec` for executing actions using Agent app instances in a DAO.

```
dao act <agent-proxy> <target-addr> [method] [argument1 ... argumentN]
```

* `agent-proxy`: Address of the Agent app proxy.
* `target-addr`: Address where the action is being executed.
* `method`: The [full signature](https://www.4byte.directory/) of the method we wish to execute in either the external contract or the app we specified, note that by the full signature we mean the [human readable function signature](https://solidity.readthedocs.io/en/v0.5.3/abi-spec.html#function-selector) (e.g. `vote(unint256,bool,bool)`).
* `arguments`: The arguments that the method will be executed with (each separated by a space).

Options:

* `--call-data`: Raw call data.
* `--eth-value`: Amount of ETH from the contract that is sent with the action.

## dao token <a href="#dao-token" id="dao-token"></a>

Commands used to create and interact with the tokens your DAO will use.

#### dao token new <a href="#dao-token-new" id="dao-token-new"></a>

Create a new [MiniMe](https://github.com/Giveth/minime) token.

```
dao token new <token-name> <symbol> [decimal-units] [transfer-enabled] [token-factory-address]
```

* `token-name`: Full name of the new Token.
* `symbol`: Symbol of the new Token.
* `decimal-units`: Total decimal units the new token will use. Defaults to `18`.
* `transfer-enabled`: Whether the new token will have transfers enabled. Defaults to `true`.
* `token-factory-address`: Address of a MiniMe Token Factory deployed on the network. Defaults to an existing Minime Factory address for Rinkeby and Mainnet. Defaults to `0xA29EF584c389c67178aE9152aC9C543f9156E2B3` on Mainnet and `0xad991658443c56b3dE2D7d7f5d8C68F339aEef29` on Rinkeby.

#### dao token change-controller <a href="#dao-token-change-controller" id="dao-token-change-controller"></a>

Change the controller of a MiniMe token.

```
dao token change-controller <token-addr> <new-controller-addr>
```

* `token-addr`: Address of the token.
* `new-controller-addr`: Address of the new controller.

## dao acl <a href="#dao-acl" id="dao-acl"></a>

Used to inspect the ACL state in a DAO to check its permissions.

```
dao acl <dao-addr>
```

* `dao-addr`: The main address of the DAO (Kernel).

#### dao acl create <a href="#dao-acl-create" id="dao-acl-create"></a>

Used to create a permission in the ACL. Can only be used if the permission hasn't been created before. The `manager` of the permission can use `dao acl grant` and `dao acl revoke` to manage the permission.

```
dao acl create <dao-addr> <app-proxy-addr> <role> <entity> <manager>
```

* `dao-addr`: The main address of the DAO (Kernel).
* `app-proxy-addr`: The address of the app whose permissions are being managed. You can find the proxy address by checking [`dao apps`](dao-commands.md#dao-apps).
* `role`: The identifier for the role. Can be the `bytes32` identifier of the role or its name (e.g. `INCREMENT_ROLE`).
* `entity`: The address of the entity that is being granted the permission by creating it.
* `manager`: The address of the entity that will be able to grant that permission or revoke it.

#### dao acl grant <a href="#dao-acl-grant" id="dao-acl-grant"></a>

Used to grant a permission in the ACL.

```
dao acl grant <dao-addr> <app-proxy-addr> <role> <entity> [params...]
```

* `dao-addr`: The main address of the DAO (Kernel).
* `app-proxy-addr`: The address of the app whose permissions are being managed. You can find the proxy address by checking [`dao apps`](dao-commands.md#dao-apps).
* `role`: The identifier for the role. Can be the `bytes32` identifier of the role or its name (e.g. `INCREMENT_ROLE`).
* `entity`: The address of entity that is being granted the permission.
* `params`: ACL parameters, with the following syntax: `"<id>,<op>,<value>"`. Multiple parameters must be separated by spaces. See the ACL [documentation](../aragonos/reference-documentation.md#parameter-interpretation) for the list of available operators.\
  **Examples:**
  * `"0,GT,2"`
  * `"2,EQ,0xC7f8dDbc7B3BFd432dEAc0CA270110467EcE01c3"`
  * `"LOGIC_OP_PARAM_ID,OR,(1,2)"`    `"0,LT,4"`    `"1,EQ,42"`
  * `"LOGIC_OP_PARAM_ID,IF_ELSE,(1,2,3)"`    `"BLOCK_NUMBER_PARAM_ID,GT,1000"`    `"0,EQ,42"`    `"0,EQ,0"`

#### dao acl revoke <a href="#dao-acl-revoke" id="dao-acl-revoke"></a>

Used to revoke a permission in the ACL.

```
dao acl revoke <dao-addr> <app-proxy-addr> <role> <entity>
```

* `dao-addr`: The main address of the DAO (Kernel).
* `app-proxy-addr`: The address of the app whose permissions are being managed. You can find the proxy address by checking [`dao apps`](dao-commands.md#dao-apps).
* `role`: The identifier for the role. Can be the `bytes32` identifier of the role or its name (e.g. `INCREMENT_ROLE`).
* `entity`: The address of entity that is being revoked the permission.

#### dao acl set-manager <a href="#dao-acl-set-manager" id="dao-acl-set-manager"></a>

Used to change the manager of a permission in the ACL.

```
dao acl set-manager <dao-addr> <app-proxy-addr> <role> <manager>
```

* `dao-addr`: The main address of the DAO (Kernel).
* `app-proxy-addr`: The address of the app whose permissions are being managed. You can find the proxy address by checking [`dao apps`](dao-commands.md#dao-apps).
* `role`: The identifier for the role. Can be the `bytes32` identifier of the role or its name (e.g. `INCREMENT_ROLE`).
* `manager`: The new manager for the permission.

#### dao acl remove-manager <a href="#dao-acl-remove-manager" id="dao-acl-remove-manager"></a>

Used to remove the manager of a permission in the ACL. The permission can be created again after removing its manager.

```
dao acl remove-manager <dao-addr> <app-proxy-addr> <role>
```

* `dao-addr`: The main address of the DAO (Kernel).
* `app-proxy-addr`: The address of the app whose permissions are being managed. You can find the proxy address by checking [`dao apps`](dao-commands.md#dao-apps).
* `role`: The identifier for the role. Can be the `bytes32` identifier of the role or its name (e.g. `INCREMENT_ROLE`).

