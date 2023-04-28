# How to migrate existing Aragon App to Buidler plugin

{% hint style="info" %}
This guide aims to describe the basic steps needed to migrate an **existing Aragon App** from the [**aragonCLI**](https://github.com/aragon/aragon-cli) to the new **Buidler plugin**. This new Aragon tool offers a more user-friendly and stable developer experience. You can learn more about the Buidler plugin [here](https://github.com/aragon/buidler-aragon).
{% endhint %}

For this tutorial, we will assume that you have existing Aragon App which was setup with aragonCLI and now needs migration to the new Builder plugin.

## 1. Install dependencies <a href="#1-install-dependencies" id="1-install-dependencies"></a>

The first step is to install the following NPM development dependencies:

* **"@aragon/buidler-aragon"**: "^0.1.0"
* **"@aragon/contract-test-helpers"**: "0.0.1"
* **"@nomiclabs/buidler"**: "^1.0.2"
* **"@nomiclabs/buidler-truffle5"**: "^1.1.2"
* **"@nomiclabs/buidler-web3"**: "^1.1.2"
* **"bignumber.js"**: "^9.0.0"
* **"web3"**: "^1.2.6"

The command for installing the dependencies is:

```
yarn add <dependencies>
```

Most of these dependencies should be new to your project and are related to Nomic Labs' [Buidler](https://buidler.dev/) (now Hardhat), a task runner for Ethereum smart contract developers. However, one dependency that you may need to upgrade is `web3`, since Aragon's plugin requires `v1.2.6` or higher. This may introduce some breaking changes, mostly in tests. See the [Migrate tests](buidler-plugin-migration.md#5-migrate-tests) section for more information.

## 2. Add/replace npm scripts <a href="#2-add-replace-npm-scripts" id="2-add-replace-npm-scripts"></a>

Since the app won't use `aragonCLI` anymore, some NPM scripts need to be changed.

In `package.json`:

* "postinstall": "yarn compile && yarn build-app"
* "build-app": "cd app && npm install && cd .."
* "compile": "buidler compile --force"
* "start": "buidler start"
* "test": "buidler test --network buidlerevm"

Also, make sure that you have the following two scripts in `app/package.json` (note that this is a different `package.json` than you just edited!):

* **serve**: Launches the webserver (Previously called `devserver` script in most projects)
* **watch**: Watches for file changes (Previously called `watch:script` script in most projects)

## 3. Update `.gitignore` file <a href="#3-update-gitignore-file" id="3-update-gitignore-file"></a>

Add the following two folders to your `.gitignore` file:

* artifacts
* cache

## 4. Create the Buidler config file <a href="#4-create-the-buidler-config-file" id="4-create-the-buidler-config-file"></a>

Add the following `buidler.config.js` file to the root of your project:

```javascript
const { usePlugin } = require('@nomiclabs/buidler/config')

usePlugin('@aragon/buidler-aragon')

module.exports = {
  defaultNetwork: 'localhost',
  networks: {
    localhost: {
      url: 'http://localhost:8545',
    },
  },
  solc: {
    version: '0.4.24',
    optimizer: {
      enabled: true,
      runs: 10000,
    },
  },
  aragon: {
    appServePort: 1234,
    clientServePort: 3000,
    appSrcPath: 'app/',
    appBuildOutputPath: 'dist/',
    hooks: require('./scripts/buidler-hooks'),
  },
}
```

You can find more information about the Buidler configuration file [here](https://buidler.dev/config) (now Hardhat). As for the `aragon` section, it contains 5 main options:

* `appServePort`: The app server port started by the `serve` script of the `app` folder. (Default: `1234`)
* `clientServePort`: Aragon client server port.
* `appSrcPath`: Frontend source for the app.
* `appBuildOutputPath`: Built app path.
* `hooks`: Aragon hooks functions. (See [Hooks](buidler-plugin-migration.md#5-hooks) section for more information)

## 5. Hooks <a href="#5-hooks" id="5-hooks"></a>

Hooks are custom functions called at various stages of an app initialization. They can be used to execute any logic before or after the app is created and also to specify the app's [`initialize()`](https://hack.aragon.org/docs/aragonos-building#constructor-and-initialization) function parameters. For example, initializing the app with a `uint256` and a `string` would be as simple as writing the following hook:

```javascript
getInitParams: async ({}, { web3, artifacts }) => {
  return [23, 'Hello, World!']
}
```

If you were using a template contract before to initialize organization state during `aragon run`, you should convert the smart contract logic into the hooks. Because hooks are much easier to write, maintain, and debug, the Buidler plugin will not be supporting template contracts. You can find complete examples in 1Hive's [Conviction Voting](https://github.com/aragonone/conviction-voting-app/blob/buidlerized/buidler-app/scripts/buidler-hooks.js) and [Payroll](https://github.com/1Hive/payroll-app/blob/buidler-setup/buidler-app/scripts/buidler-hooks.js) apps. In our case, we will simply add empty functions since we don't need any initialization logic. So we will create a file named `buidler-hooks.js` in the `scripts` folder and add the following code:

```javascript
module.exports = {
  // Called before a dao is deployed.
  preDao: async ({}, { web3, artifacts }) => {},

  // Called after a dao is deployed.
  postDao: async ({ dao }, { web3, artifacts }) => {},

  // Called after the app's proxy is created, but before it's initialized.
  preInit: async ({ proxy }, { web3, artifacts }) => {},

  // Called after the app's proxy is initialized.
  postInit: async ({ proxy }, { web3, artifacts }) => {},

  // Called when the start task needs to know the app proxy's init parameters.
  // Must return an array with the proxy's init parameters.
  getInitParams: async ({}, { web3, artifacts }) => {
    return []
  },

  // Called after the app's proxy is updated with a new implementation.
  postUpdate: async ({ proxy }, { web3, artifacts }) => {},
}
```

## 5. Migrate tests <a href="#5-migrate-tests" id="5-migrate-tests"></a>

Since the Aragon Buidler plugin uses truffle 5, you may have to migrate part of your tests. You can follow [this guide](https://medium.com/coinmonks/upgrading-to-truffle-5-22aedc7c2a4d) or the [truffle team announcement](https://www.trufflesuite.com/blog/truffle-v5-has-arrived).

Nevertheless, the following tips can be helpful:

### Async/Await <a href="#async-await" id="async-await"></a>

Most truffle contract functions are now asynchronous, so code like this:

```javascript
const dao = Kernel.at('0x9d1C272D0541345144D943470B3a90f14c56910c')
```

should become:

```javascript
const dao = await Kernel.at('0x9d1C272D0541345144D943470B3a90f14c56910c')
```

### Web3.js 1.2 <a href="#web3js-12" id="web3js-12"></a>

Truffle 5 is using Web3.js `1.2` instead of `0.20`, which comes with a few changes:

* [PromiEvent](https://web3js.readthedocs.io/en/v1.2.0/callbacks-promises-events.html) objects.
* Addresses are now mixed-case instead of lower-case.
* Many Web3 utility functions have been moved to [web3.utils](https://web3js.readthedocs.io/en/v1.2.0/web3-utils.html)
* Numbers returned directly from Web3 are now strings.
* Functions that return multiple values now return an object with both named and indexed keys.

### BN.js <a href="#bnjs" id="bnjs"></a>

Truffle 5 has also replaced [bignumber.js](https://github.com/MikeMcl/bignumber.js) with [BN.js](https://github.com/indutny/bn.js). Instances of `web3.BigNumber()` will therefore have to be changed to `web3.utils.toBN()`.

### Ethereum addresses <a href="#ethereum-addresses" id="ethereum-addresses"></a>

You now need to use full Ethereum addresses instead of partial ones like `0x0`. So this address:

```javascript
const ZERO = '0x00'
```

would become:

```javascript
const ZERO = '0x0000000000000000000000000000000000000000'
```

### Coverage <a href="#coverage" id="coverage"></a>

A useful Buidler plugin is available [here](https://github.com/sc-forks/solidity-coverage) for Solidity code coverage.

## 6. Start the app and uninstall unnecessary dependencies <a href="#6-start-the-app-and-uninstall-unnecessary-dependencies" id="6-start-the-app-and-uninstall-unnecessary-dependencies"></a>

You are now ready to start your app:

```
yarn start
```

You can also uninstall dependencies that are no longer required:

* @aragon/cli
* ganache-cli
* truffle

```
yarn remove <dependencies>
```

