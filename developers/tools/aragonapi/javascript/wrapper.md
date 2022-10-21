# Wrapper

## aragonAPI for Aragon client implementations

### Install <a href="#install" id="install"></a>

```
npm install --save @aragon/wrapper
```

### Import <a href="#import" id="import"></a>

#### ES6 <a href="#es6" id="es6"></a>

```js
import AragonWrapper, { providers } from '@aragon/wrapper'
```

#### ES5 (CommonJS) <a href="#es5-commonjs" id="es5-commonjs"></a>

```js
const AragonWrapper = require('@aragon/wrapper').default
const providers = require('@aragon/wrapper').providers
```

## API Reference <a href="#api-reference" id="api-reference"></a>

### AragonWrapper <a href="#aragonwrapper" id="aragonwrapper"></a>

#### **Parameters** <a href="#parameters" id="parameters"></a>

* `daoAddress` [**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String) The address of the DAO.
* `options` [**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object) Wrapper options. (optional, default `{}`)
  * `options.provider` **any** The Web3 provider to use for blockchain communication. Defaults to `web3.currentProvider` if web3 is injected, otherwise will fallback to [wss://rinkeby.eth.aragon.network/ws](wss://rinkeby.eth.aragon.network/ws) (optional)
  * `options.apm` [**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object) Options for fetching information from aragonPM
  * `options.apm.ensRegistryAddress` [**String**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String) The address of the ENS registry
  * `options.apm.ipfs` [**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object) IPFS options for fetching information from aragonPM (optional)
  * `options.apm.ipfs.gateway` [**String**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String) The IPFS gateway to use for fetching information (optional)
  * `options.apm.ipfs.fetchTimeout` [**Number**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) The timeout before a request to IPFS is automatically failed in milliseconds (optional, default 10s)
  * `options.cache` [**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object) Cache options (optional)
  * `options.cache.forceLocalStorage` [**boolean**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) On browser environments, downgrade to localStorage even if IndexedDB is available (optional)

#### **Examples** <a href="#examples" id="examples"></a>

```javascript
const aragon = new Aragon(
  '0xdeadbeef',
  { apm: { ensRegistryAddress: '0x...' } }
)

// Initialises the wrapper
await aragon.init({
  accounts: {
    providedAccounts: ['0xbeefdead', '0xbeefbeef'],
  },
})
```

#### init <a href="#init" id="init"></a>

Initialise the wrapper.

**Parameters**

* `options` [**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object) An optional options object for configuring the wrapper.
  * `accounts` [**Array**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array)**\<string>** Options object for [`initAccounts()`](wrapper.md#initaccounts)``

Returns [**Promise**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Promise)**\<void>**

Throws [**Error**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Error) if the `daoAddress` provided during constructor is detected to not be a [`Kernel`](https://github.com/aragon/aragonOS/blob/next/contracts/kernel/Kernel.sol) instance

#### initAccounts <a href="#initaccounts" id="initaccounts"></a>

Initialise user-controlled accounts.

**Parameters**

* `options` [**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object)
  * `fetchFromWeb3` [**boolean**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) Whether accounts should also be fetched from the Web3 instance provided to the wrapper
  * `providedAccounts` [**Array**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array)**\<string>** An array of accounts that the user controls

Returns [**Promise**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Promise)**\<void>**

#### initAcl <a href="#initacl" id="initacl"></a>

Initialise the ACL.

**Parameters**

* `options` [**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object)
  * `aclAddress` [**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String) Address of the [`ACL`](https://github.com/aragon/aragonOS/blob/next/contracts/acl/ACL.sol) instance to use, defaults to the `daoAddress`'s default `ACL`

Returns [**Promise**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Promise)**\<void>**

#### getProxyValues <a href="#getproxyvalues" id="getproxyvalues"></a>

Get proxy metadata (`appId`, address of the kernel, ...).

**Parameters**

* `proxyAddress` [**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String) The address of the proxy to get metadata from

Returns [**Promise**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Promise)**<**[**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object)**>**

#### isApp <a href="#isapp" id="isapp"></a>

Check if an object is an app.

**Parameters**

* `app` [**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object)

Returns [**boolean**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Boolean)

#### initApps <a href="#initapps" id="initapps"></a>

Initialise apps observable.

Returns **void**

#### initForwarders <a href="#initforwarders" id="initforwarders"></a>

Initialise forwarder observable.

Returns **void**

#### initNetwork <a href="#initnetwork" id="initnetwork"></a>

Initialise connected network details observable.

Returns [**Promise**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Promise)**\<void>**

#### runApp <a href="#runapp" id="runapp"></a>

Run an app.

**Parameters**

* `sandbox` [**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object) An object that is compatible with the PostMessage API.
* `proxyAddress` [**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String) The address of the app proxy.

Returns [**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object)

#### getAccounts <a href="#getaccounts" id="getaccounts"></a>

Get the available accounts for the current user.

Returns [**Promise**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Promise)**<**[**Array**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array)**<**[**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String)**>>** An array of addresses

#### getTransactionPath <a href="#gettransactionpath" id="gettransactionpath"></a>

Calculate the transaction path for a transaction to `destination` that invokes `methodName` with `params`.

**Parameters**

* `destination` [**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String)
* `methodName` [**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String)
* `params` [**Array**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array)**\<any>**

Returns [**Array**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array)**<**[**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object)**>** An array of Ethereum transactions that describe each step in the path

#### calculateTransactionPath <a href="#calculatetransactionpath" id="calculatetransactionpath"></a>

Calculate the transaction path for a transaction to `destination` that invokes `methodName` with `params`.

**Parameters**

* `sender` [**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String)
* `destination` [**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String)
* `methodName` [**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String)
* `params` [**Array**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array)**\<any>**

Returns [**Array**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array)**<**[**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object)**>** An array of Ethereum transactions that describe each step in the path

#### modifyAddressIdentity <a href="#modifyaddressidentity" id="modifyaddressidentity"></a>

Modify the identity metadata for an address using the highest priority provider.

**Parameters**

* `address` [**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String) Address to modify
* `metadata` [**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object) Identity metadata

Returns a [**Promise**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Promise)**\<void>** that resolves if the modification was successful.

#### resolveAddressIdentity <a href="#resolveaddressidentity" id="resolveaddressidentity"></a>

Resolve the identity metadata for an address using the highest priority provider.

**Parameters**

* `address` [**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String) Address to resolve

Returns a [**Promise**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Promise)**<**[**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object)**>** that resolves with the identity or null if not found.

#### requestAddressIdentityModification <a href="#requestaddressidentitymodification" id="requestaddressidentitymodification"></a>

Request an identity modification using the highest priority provider.

**Parameters**

* `address` [**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String) Address to request modification

Returns a [**Promise**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Promise)**\<void>** that delegates resolution to the handler.

#### removeLocalIdentities <a href="#removelocalidentities" id="removelocalidentities"></a>

Remove specific local identities.

**Parameters**

* `addresses` [**Array**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array)**\<string>** Addresses to remove from local identities

#### searchIdentities <a href="#searchidentities" id="searchidentities"></a>

Search identites using the highest priority provider.

**Parameters**

* `searchTerm` [**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String) String to search for

Returns a [**Promise**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Promise)**<**[**Array**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array)**<**[**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String)**>>** which resolves with the found identities or an empty array.

#### setGuiStyle <a href="#setguistyle" id="setguistyle"></a>

Set the current GUI style of the client to the apps.

**Parameters**

* `appearance` [**string**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/String) Either `light` or `dark`. Other values could be passed in the future (e.g. `black` for OLED screens). Apps should display a corresponding theme, unless `theme` has also been set.
* `theme` [**Object**](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Object) An entire theme ([e.g. aragonUI's light theme](https://github.com/aragon/aragon-ui/blob/be4faf21172bdbc98816dd7ca4533bfa51e6712a/src/theme/theme-light.js)) that should be displayed by app frontends. It is optional and apps should respect it when present. If not possible, apps should respect the value of `appearance`.

Returns **void.**

****

> <mark style="color:purple;">**Do you have a question? Leave your comments here at our Discourse forum**</mark>** 👇**

{% embed url="https://support.aragon.org/c/dev-support/20" %}
