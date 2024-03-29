# How to build your first Aragon App!

{% hint style="info" %}
In this guide, we will walk you through building your first <mark style="color:blue;">**Aragon App**</mark> using <mark style="color:blue;">**aragonOS**</mark>, the JavaScript implementation of <mark style="color:blue;">**aragonAPI**</mark><mark style="color:blue;">,</mark> <mark style="color:blue;"></mark><mark style="color:blue;">**aragonUI**</mark> and the <mark style="color:blue;">**Aragon builder plugin**</mark><mark style="color:blue;">.</mark>
{% endhint %}

## Environment setup <a href="#environment-setup" id="environment-setup"></a>

Before starting you need to check if you have already installed all these prerequisites:

* the right version of **node.js** (recommended`v12 LTS` version)
* **Metamask** web3 provider
* the **aragonCLI** (Aragon Command Line Interface)&#x20;
* the **Aragon Buidler plugin**

If you haven't already installed them or if you need more info about this goes to the "_Environment Setup_" paragraph [here](../the-basics/getting-started.md).

## The setup

Let's first set up and bootstrap our project:

```
npx create-aragon-app foo tutorial
```

{% hint style="danger" %}
For this particular command switching from `node v12` to `node v14 LTS or v16 LTS` might be required to prevent a node error on install. In that case you have to switch, do not forget to switch back to `v12 LTS` afterwards!
{% endhint %}

This will create a new directory named `foo`, with files cloned from [your first Aragon app template](https://github.com/aragon/your-first-aragon-app). This particular boilerplate includes everything you need to get started:

* [buidler](https://buidler.dev/) (now Hardhat),&#x20;
* aragonOS,
* aragonAPI.

## Structure <a href="#structure" id="structure"></a>

This boilerplate has the following structure:

```md
root
├── app
├ ├── src
├ ├ ├── App.js
├ ├ ├── index.js
├ ├ └── script.js
├ └── package.json
├── contracts
├ └── CounterApp.sol
├── scripts
├ └── buidler-hooks.js
├── arapp.json
├── manifest.json
├── buidler.config.js
└── package.json
```

* **app**: Frontend folder. Completely encapsulated, has its package.json and dependencies.
  * **src**: Source files.
    * `App.js`: Aragon app root component.
    * `index.js`: Aragon app entry point.
    * `script.js`: Aragon app background script.
  * [**package.json**](https://docs.npmjs.com/creating-a-package-json-file): Frontend npm configuration file.
* **contracts**: Smart Contracts folder.
  * `CounterApp.sol`: Aragon app contract.
* **scripts**: Scripts folder.
  * `buidler-hooks.js`: Buidler script hook.
* [**arapp.json**](../aragoncli/global-configuration.md#the-arapp.json-file): Aragon configuration file. Includes Aragon-specific metadata for your app.
* [**manifest.json**](../aragoncli/global-configuration.md#the-manifestjson-file): Aragon configuration file. Includes web-specific configurations.
* [**buidler.config.js**](https://buidler.dev/config/): Buidler (now Hardhat) configuration file.
* [**package.json**](https://docs.npmjs.com/creating-a-package-json-file): Main npm configuration file.

{% hint style="danger" %}
#### Stuck? <a href="#stuck" id="stuck"></a>

If you get stuck at any point come back [**here**](https://github.com/aragon/your-first-aragon-app/pull/2/files) to check the diff with changes after the tutorial is completed.
{% endhint %}

{% hint style="info" %}
If you need help, please reach out to Aragon core contributors and community members in the [#dev-space channel](https://discord.gg/DHgjDnp9) off our Discord server.
{% endhint %}

{% hint style="success" %}
Now let's start with it 💪.
{% endhint %}

## Writing a simple contract <a href="#writing-a-simple-contract" id="writing-a-simple-contract"></a>

To illustrate how easy it is to use aragonOS, we will build our app as a vanilla smart contract, without any Aragon-specific interfaces at all.

Today, we will build a simple counter app — you can increment it, you can decrement it, and it will all be decentralized. Decentralized coffee counter, anyone? If yes, then add the below code to `CounterApp.sol`:

```solidity
// contracts/CounterApp.sol
pragma solidity ^0.4.24;

import "@aragon/os/contracts/lib/math/SafeMath.sol";


contract CounterApp {
    using SafeMath for uint256;

    /// Events
    event Increment(address indexed entity, uint256 step);
    event Decrement(address indexed entity, uint256 step);

    /// State
    uint256 public value;

    function increment(uint256 step) external {
        value = value.add(step);
        emit Increment(msg.sender, step);
    }

    function decrement(uint256 step) external {
        value = value.sub(step);
        emit Decrement(msg.sender, step);
    }
}
```

Pretty simple, right? You might wonder why we would bother adding events to this smart contract, but it comes in handy later for illustration purposes — and we can also create an activity feed from it, if we wanted to.

{% hint style="info" %}
**Note**\
We use [SafeMath](https://github.com/aragon/aragonOS/blob/next/contracts/lib/math/SafeMath.sol) for uint256. Using SafeMath is a security convention that allows handling math operations with safety checks that revert on error preventing the risk of overflows.
{% endhint %}

## 3 steps to governance and upgradeability <a href="#3-steps-to-governance-and-upgradeability" id="3-steps-to-governance-and-upgradeability"></a>

Now for the interesting part: making our simple smart contract an Aragon app.

**First**, inherit from the Aragon app smart contract. Integrate this code in `CounterApp.sol`:

```solidity
import "@aragon/os/contracts/apps/AragonApp.sol";

contract CounterApp is AragonApp {
    // ...
}
```

**Second**, define the roles that you want your app to have.&#x20;

A role can be assigned to other apps or people and those entities will have access to methods guarded by that role.

In this example, we will define a role for incrementing and a role for decrementing but note that you can have a single role to guard all methods in your contract if you find that appropriate. Integrate this code in `CounterApp.sol`:

```solidity
contract CounterApp is AragonApp {
    // ...
    bytes32 constant public INCREMENT_ROLE = keccak256("INCREMENT_ROLE");
    bytes32 constant public DECREMENT_ROLE = keccak256("DECREMENT_ROLE");
    // ...
}
```

**Third**, guard the methods with the `auth()` modifier that the `AragonApp` interface gives you and add an [initialize function ](../aragonos/developing-with-aragonos.md)to your contract; we use `initValue` as the starting value of the counter. Integrate this code in `CounterApp.sol`:

```solidity
contract CounterApp is AragonApp {
    // ...

    function initialize(uint256 _initValue) public onlyInit {
        value = _initValue;

        initialized();
    }

    function increment(uint256 step) auth(INCREMENT_ROLE) external {
        // ...
    }

    function decrement(uint256 step) auth(DECREMENT_ROLE) external {
        // ...
    }
}
```

{% hint style="success" %}
That's it. In 3 steps, you now have an Aragon app, with full upgradeability and modular governance. [**Here**](https://github.com/aragon/your-first-aragon-app/pull/2/files) you can double check whether your code is right.
{% endhint %}

## Descriptive transactions <a href="#descriptive-transactions" id="descriptive-transactions"></a>

Aragon wants to be as user friendly as possible, so it provides an easy way for developers to describe what their smart contracts do in a human-readable way. It's called [Radspec.](../the-basics/human-readable-transactions.md) It works by putting `@notice` statements alongside a human-readable description for the function. In our example, we use the input `step` to describe what is doing our function at runtime.

```solidity
contract CounterApp is AragonApp {
    /**
     * @notice Increment the counter by `step`
     * @param step Amount to increment by
     */
    function increment(uint256 step) auth(INCREMENT_ROLE) external {
        // ...
    }

    /**
     * @notice Decrement the counter by `step`
     * @param step Amount to decrement by
     */
    function decrement(uint256 step) auth(DECREMENT_ROLE) external {
        // ...
    }
}
```

## Building the frontend <a href="#building-the-frontend" id="building-the-frontend"></a>

Because apps inside the [Aragon client ](../the-basics/the-aragon-client.md)are sandboxed, it also means that apps do not have direct access to Web3.

Apps are run inside an iframe, which means that it only has access to their own DOM, not the outlying DOM. The app can communicate with the client over our custom RPC protocol.

Then the client takes care of connecting to Ethereum via Web3, and also handles things like signing transactions, displaying notifications and more to the end-user.

All of this is achieved by using [**aragonAPI**](../aragonapi/). aragonAPI is split into two parts: one for clients and one for apps. The client portion of aragonAPI reads _requests_ from the app over RPC, sandboxes apps and performs Web3 actions, whereas the app portion provides a simple API to communicate with the client (to read state, send transactions and more).

### Background scripts and building state <a href="#background-scripts-and-building-state" id="background-scripts-and-building-state"></a>

Apps usually want to listen to events using Web3 and build an application state from those events. This concept is also known as _**event sourcing**_.

aragonAPI was built with event sourcing in mind. To build the state continually without having the app loaded indefinitely, though, we need to run a background script.

Thankfully the [Aragon client ](../the-basics/the-aragon-client.md)will run background scripts specified in the manifest files of our app (more on manifest files later).

Let's start by writing a background script that listens for our `Increment` and `Decrement` events, and builds a state, for this example, the current value of our counter. Add the below code to `script.js`:

```javascript
// app/src/script.js
import 'core-js/stable'
import 'regenerator-runtime/runtime'
import Aragon, { events } from '@aragon/api'

const app = new Aragon()

app.store(
  async (state, { event }) => {
    const nextState = {
      ...state,
    }

    try {
      switch (event) {
        case 'Increment':
          return { ...nextState, count: await getValue() }
        case 'Decrement':
          return { ...nextState, count: await getValue() }
        case events.SYNC_STATUS_SYNCING:
          return { ...nextState, isSyncing: true }
        case events.SYNC_STATUS_SYNCED:
          return { ...nextState, isSyncing: false }
        default:
          return state
      }
    } catch (err) {
      console.log(err)
    }
  },
  {
    init: initializeState(),
  }
)

/***********************
 *   Event Handlers    *
 ***********************/

function initializeState() {
  return async cachedState => {
    return {
      ...cachedState,
      count: await getValue(),
    }
  }
}

async function getValue() {
  // Get current value from the contract by calling the public getter
  // app.call() returns a single-emission observable that we can immediately turn into a promise
  return parseInt(await app.call('value').toPromise(), 10)
}
```

If you've worked with [Redux](https://redux.js.org/) before, this might look vaguely familiar.

The `store` method takes in a reducer function with the signature `(state, event) => state`, where `state` is whatever you want it to be (in this example it is an integer), and `event` is a [Web3 event](https://web3js.readthedocs.io/en/1.0/web3-eth-contract.html#contract-events). The reducer function **must always** return a state, even if it is the same state as before. Returning undefined will reset the reduced state to its initial null state. Also note that the initial state is always null, not undefined, because of JSONRPC limitations.

The `store` should be used as the main "event loop" in an application's background script (running inside a WebWorker). Listens for events, passes them through reducer, caches the resulting state, and re-emits that state for easy chaining. Optionally takes a configuration object comprised of an init function, to re-initialize cached state, and an externals array for subscribing to external contract events. See below for more details.

The store has block caching automatically applied, such that subsequent loads of the application only fetch new events from a cached ("committed") block height (rather than from 0 or the app's initialization block). This state can be observed in the view portion of your app. Also, note that the `store` method returns an observable of states. This is a recurring theme in the JavaScript implementation of aragonAPI—almost everything is an [RxJS](https://rxjs-dev.firebaseapp.com/) observable.

Learn more about it on the [store() documentation](https://github.com/aragon/aragon.js/blob/master/docs/API.md#store).

{% hint style="success" %}
[**Here**](https://github.com/aragon/your-first-aragon-app/pull/2/files) you can double check whether your code is right.
{% endhint %}

## Displaying State <a href="#displaying-state" id="displaying-state"></a>

Now let's write the view portion of our app. In our case, this is a simple HTML file, and a simple React app with the `useAragonApi` [React Hook](https://reactjs.org/docs/hooks-intro.html) that observes the state that our background script builds for us and returns the data needed to interact with the app contract. Add this code to `app/index.html`:

```html
<!-- app/index.html !-->
<!DOCTYPE html>
<html>
  <head>
    <title>Aragon App</title>
  </head>
  <body>
    <div id="root"></div>
    <script src="src/index.js"></script>
  </body>
</html>
```

Add this code to `app/src/index.js`:

```javascript
// app/src/index.js
import React from 'react'
import ReactDOM from 'react-dom'
import { AragonApi } from '@aragon/api-react'
import App from './App'

const reducer = state => {
  if (state === null) {
    return { count: 0, isSyncing: true }
  }
  return state
}

ReactDOM.render(
  <AragonApi reducer={reducer}>
    <App />
  </AragonApi>,
  document.getElementById('root')
)
```

Before using any Hook provided, you need to declare the component `AragonApi` to connect the app. It is generally a good idea to do it near the top level of your React tree. It should only be declared once. It has an optional reducer prop, which lets you process the state coming from the background script. If not provided, the state is passed as-is.

{% hint style="success" %}
[**Here**](https://github.com/aragon/your-first-aragon-app/pull/2/files) you can double check whether your code is right.
{% endhint %}

## App root component <a href="#app-root-component" id="app-root-component"></a>

Add this code to `App.js`:

```javascript
// app/src/App.js
import React from 'react'
import { useAragonApi } from '@aragon/api-react'
import {
  Box,
  Button,
  GU,
  Header,
  IconMinus,
  IconPlus,
  Main,
  SyncIndicator,
  Text,
  textStyle,
} from '@aragon/ui'

function App() {
  const { appState } = useAragonApi()
  const { count, isSyncing } = appState

  return (
    <Main>
      {isSyncing && <SyncIndicator />}
      <Header
        primary="Counter"
        secondary={
          <Text
            css={`
              ${textStyle('title2')}
            `}
          >
            {count}
          </Text>
        }
      />
      <Box
        css={`
          display: flex;
          align-items: center;
          justify-content: center;
          text-align: center;
          height: ${50 * GU}px;
          ${textStyle('title3')};
        `}
      >
        Count: {count}
      </Box>
    </Main>
  )
}

export default App
```

`useAragonApi()` is a React Hook that returns the data needed to interact with the app contract. As with any React Hook, please ensure that you follow the [Rules of Hooks](https://reactjs.org/docs/hooks-rules.html). It returns an object containing the following entries:

* `appState`: Is the app state, after having passed the background script `state` through the reducer prop of AragonApi.
* `api`: This is the current AragonApp instance. Use it to call methods on the contract.

These are not all the entries but the ones we are going to use in the tutorial. To learn about all of them check the [useAragonApi documentation](https://github.com/aragon/aragon.js/blob/master/packages/aragon-api-react/README.md#usearagonapi).

{% hint style="info" %}
**Note**\
We are using several components from aragonUI. aragonUI is a React library based on aragonDS, the Aragon design system. It aims to provide the elements needed to build Aragon apps that feel native to the Aragon ecosystem. We are not going into details of aragonUI on this tutorial. If you feel like to learn more, check the [Getting started guide](https://ui.aragon.org/getting-started/).
{% endhint %}

**Sending transactions**

Our users need to be able to increment and decrement the counter. For this, we send what is called an _intent_ to the client. An intent is an action you would like to occur on a specific contract. This intent is handled by the client, which will calculate a _transaction path_ using the ACL of our DAO.

To understand transaction paths, we must first understand a little bit about how the ACL works.

The[ ACL (Access Control List) ](../the-basics/permissions.md)is a simple mapping of _who_ can perform _what_ actions _where_. In our case, _someone_ can perform an action guarded by a specific role (the _what_) on our app (the _where_).

However, it's entirely possible that users can not perform actions directly. For example, to increment the counter, we might want a decision-making process, such as a vote. The beauty of aragonOS is that we never need to specify this directly, as this is handled by the ACL.

We simply say that the only one (_who_) that can perform increments and decrements (_what_) on our app (_where_) is the voting app. This is not done at compile-time, it is done at run time.

This works because of a concept called [_forwarders_](../the-basics/forwarding.md). A forwarder is simply an app that can execute transactions on someone's behalf, if the ACL permits it, and that app can have its _arbitrary conditions_ under which it wants to execute your transaction! In the example of the voting app, the voting app will only execute your transaction if the vote passes.

It's really simple to use. Let's add our intents to our app. Integrate this code into `App.js`:

```javascript
// ...

function App() {
  const { api, appState } = useAragonApi()
  const { count, isSyncing } = appState
  const step = 2

  return (
    <Main>
      <Box>
        <div>
          <Button
            display="icon"
            icon={<IconMinus />}
            label="Decrement"
            onClick={() => api.decrement(step).toPromise()}
          />
          <Button
            display="icon"
            icon={<IconPlus />}
            label="Increment"
            onClick={() => api.increment(step).toPromise()}
            css={`
              margin-left: ${2 * GU}px;
            `}
          />
        </div>
      </Box>
    </Main>
  )
}
```

That's it! Now, whenever the user clicks one of either the increment or decrement buttons, an intent is sent to the wrapper, and it will show the user a transaction to sign.

{% hint style="success" %}
[**Here**](https://github.com/aragon/your-first-aragon-app/pull/2/files) you can double check whether your code is right.
{% endhint %}

## Writing the manifest files <a href="#writing-the-manifest-files" id="writing-the-manifest-files"></a>

For aragonAPI to function, it needs some metadata about your app. This metadata is specified in two manifest files; `manifest.json` and `arapp.json`.

### arapp.json <a href="#arappjson" id="arappjson"></a>

`arapp.json` defines the smart contract and aragonPM-specific things like the roles in your app or different environments.

Let's modify `arapp.json` so that it knows about the roles we defined previously and use the development environment. Add this code to `arapp.json`:

```json
{
  "roles": [
    {
      "name": "Increment the counter",
      "id": "INCREMENT_ROLE",
      "params": []
    },
    {
      "name": "Decrement the counter",
      "id": "DECREMENT_ROLE",
      "params": []
    }
  ],
  "environments": {
    "default": {
      "network": "rpc",
      "appName": "foo.aragonpm.eth"
    }
  },
  "path": "contracts/CounterApp.sol"
}
```

Notice that we input a fully qualified [ENS](https://ens.domains/) name for `appName`. Let's examine the ENS name we entered because it is not entirely arbitrary.

![](https://i.imgur.com/MQnYT6d.png)

The first label in the ENS name is the name of our app. This can be anything you want, given that the full ENS name is not taken.

The second and third label is the name of the [aragonPM](../aragonpm/) registry that your repository will be (or is) registered to. For the sake of simplicity, this guide assumes that you have rights to create repositories on aragonpm.eth, but you could deploy your aragonPM registry if you so desire.

### manifest.json <a href="#manifestjson" id="manifestjson"></a>

`manifest.json` defines end-user specific things like the human-readable name of your app, icons, and a small description of your app. It also (optionally) defines background scripts, of which we have one.

Let's modify it accordingly. Add this code to `manifest.json`:

```json
{
  "name": "Counter",
  "description": "My first Aragon app",
  "script": "/script.js",
  "start_url": "/index.html"
}
```

### Buidler script hooks <a href="#buidler-script-hooks" id="buidler-script-hooks"></a>

These hooks are called by the Aragon Buidler plugin during the start task's lifecycle. All hooks receive two parameters:

* Params object that may contain other objects that pertain to the particular hook.
* A "bre" or BuidlerRuntimeEnvironment object that contains environment objects like web3, Truffle artifacts, etc.

We are going to use the `getInitParam` hook. Must return an array with the proxy's init parameters.

That is called when the start task needs to know the app proxy's initialized parameters, `_initValue` for our `CounterApp` initialize function. Add tis code to `buidler-hooks.js`:

```javascript
// scripts/buidler-hooks.js
module.exports = {
  // ...
  getInitParams: async ({}, { web3, artifacts }) => {
    return [15]
  },
  // ...
}
```

{% hint style="success" %}
[**Here**](https://github.com/aragon/your-first-aragon-app/pull/2/files) you can double check whether your code is right.
{% endhint %}

## Running your app locally <a href="#running-your-app-locally" id="running-your-app-locally"></a>

To test out your app without deploying a DAO yourself, installing apps, setting up permissions and setting up aragonPM, you can simply run:

```
yarn
yarn start
```

{% hint style="warning" %}
Please check you have the right compiler version. It is necessary 0.4.24. If not, select the correct one and run _npm start_ again.
{% endhint %}

{% hint style="danger" %}
If you receive a lot of errors on the console, please be sure to run the right node.js (**v12 is required**).
{% endhint %}

This will do a couple of things for you:

* It will start a development chain you can interact with (it uses `ganache-core`, so it's a full testrpc instance) and prints 10 accounts.
* It compiles the contracts.
* It deploys the aragonOS bases (ENS, DAO factory, aragonPM registry).
* It deploys an Aragon DAO with apps and development permissions (i.e. everyone can do everything)
* It builds your app front-end. Since we're importing Node.js modules in our front-end, we need a build script. For this, we opted to use `parcel` because it has zero-config, but you can use your favorite bundler.
* It publishes your app to a local aragonPM instance.
* It installs your app.
* It initializes the app proxy with the parameter we defined in `getInitParams` hook.
* It starts the client locally, installing it if it's not cached.

After running this command a browser tab should pop up with your freshly created DAO, complete with permissions and your local app installed.

Login to metamask (if not already logged in), select the [Localhost 8545 network](how-to-sign-with-web3-providers/set-up-metamask/metamask.md)  and import the [12 words seed phrase](how-to-sign-with-web3-providers/set-up-metamask/import-your-seed-wallet-in-metamask.md) (account mnemonic) listed on the console (if not already done). Select the account you want to use.

At this point feel free to play around. Both front-end and smart contract files have hot reloading. Yes, even smart contract code, we do a proxy swap on every change under the hood 😎, enjoy.

{% hint style="success" %}
If you've made it this far, congratulations! 😊🎉😊🎉
{% endhint %}

{% hint style="danger" %}
#### Stuck? <a href="#stuck" id="stuck"></a>

If you got stuck at any point check back [**here**](https://github.com/aragon/your-first-aragon-app/pull/2/files) to check whether there's a diff with your code.
{% endhint %}

## Next steps <a href="#next-steps" id="next-steps"></a>

### Tests <a href="#tests" id="tests"></a>

If you feel like to keep learning about the Aragon stack right away. A great way of doing it is including some tests on your app. Check the [test examples](https://github.com/aragon/aragon-react-boilerplate/blob/master/test/app.test.js) of the react boilerplate repo for ideas.

### Publishing <a href="#publishing" id="publishing"></a>

Now that we're confident that our app will work and amaze the world, we should publish it. You can follow the publishing guide to learn[ how to publish in different environments.](publish-to-aragonpm.md)

### Documentation <a href="#documentation" id="documentation"></a>

A good place to go from here would be to check out [our existing apps](https://github.com/aragon/aragon-apps). They are fairly self-contained and use some patterns you might find helpful.

There is much more to [aragonOS](../aragonos/) and [aragonAPI](../aragonapi/), and we even have our own [UI toolkit](../aragonui/). We encourage you to explore all 3 and provide us feedback.

### Community <a href="#community" id="community"></a>

Join the conversation and ask questions on [GitHub](https://github.com/aragon), [Aragon Technical Forum](https://support.aragon.org/) and Discord [#dTech-general ](https://discord.gg/A8gQmUfFWs)channel and make sure to tell us if you build something amazing!

Now you just need to share the great news on Twitter and Reddit, to let people know that you've built something great!

