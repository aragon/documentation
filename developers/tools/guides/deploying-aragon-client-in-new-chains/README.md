# Deploying Aragon Client in new Chains

## Introduction

{% hint style="info" %}
This guide will run you through how to **deploy Aragon to other EVM compatible chains.**
{% endhint %}

This deployment is self-sufficient and does not pose a requirement on other contracts already deployed to the target chain.

Before you begin, make sure that there are no official deployments to the network you will be targeting.

## Official Aragon Client deployments

| Network Name     | ENS Registry                               | Type                                                          | Deployment                                                                |
| ---------------- | ------------------------------------------ | ------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Ethereum Mainnet | 0x00000000000C2E074eC69A0dFb2997BA6C7d2e1e | <mark style="background-color:blue;">Official</mark>          | [Aragon](https://aragon.org/)                                             |
| Ethereum Rinkeby | 0x98df287b6c145399aaa709692c8d308357bc085d | <mark style="background-color:blue;">Official</mark>          | [Aragon](https://aragon.org/)                                             |
| Ethereum Ropsten | 0x6afe2cacee211ea9179992f89dc61ff25c61e923 | <mark style="background-color:blue;">Official</mark>          | [Aragon](https://aragon.org/)                                             |
| Polygon Mumbai   | 0x431f0eed904590b176f9ff8c36a1c4ff0ee9b982 | <mark style="background-color:blue;">Official</mark>          | [Aragon](https://aragon.org/)<mark style="background-color:blue;"></mark> |
| Polygon Mainnet  | 0x3c70a0190d09f34519e6e218364451add21b7d4b | <mark style="background-color:blue;">Official</mark>          | [Aragon](https://aragon.org/)<mark style="background-color:blue;"></mark> |
| Harmony Testnet  | 0xbc7828fa8665c637901ad5abd5c7e647c9ab140f | <mark style="background-color:blue;">Official</mark>          | [Aragon](https://aragon.org/)                                             |
| xDAI             | 0xaafca6b0c89521752e559650206d7c925fd0e530 | <mark style="background-color:yellow;">Trusted Partner</mark> | [1Hive](https://1hive.org/)                                               |
| Harmony          | 0x843ddfab8406e752d03fa75dbb275070f368658d | <mark style="background-color:blue;">Official</mark>          | [Aragon](https://aragon.org/)                                             |
| BSC Testnet      | 0x843ddfab8406e752d03fa75dbb275070f368658d | <mark style="background-color:blue;">Official</mark>          | [Aragon](https://aragon.org/)                                             |

#### [Deployment information](deployments-information/)

## Good Manners

1. Please verify all contracts that you have deployed with the target network scanner unless they are automatically verified.
2. Notify the Aragon team about your plans to deploy to the target network.
3. Keep the team in close loops about the issues you encounter as well as any ambiguity during the process.
4. Do not change the smart contract code.
5. Any automation and new scripts are welcome. Create a PR for the respective Github repository.

## Deploying

### Before you start

1. We will use notation `<target network>` to represent the network we are deploying to. It should be consistent throughout this tutorial.
2. Make sure that you use one account thought the tutorial. You will need Private key and some network tokens to pay for gas.

### Step 1

**Description:** Provide an account that will be used to deploy contracts as well as rpc connection to the target network.

This account will be the owner of the deployed Aragon infrastructure. To be considered an official deployment we will need to transfer all permissions from this account to an official Aragon account.

*   To provide access to an account using a Private Key:

    1. Create a file `nano ~/.aragon/<target network>_key.json`
    2. Add the following inside the file

    ```
    {
      "rpc": "<RPC url for your target network, for example "<https://rpc-mainnet.matic.network>" for Polygon>",
      "keys": ["Your Private Key"]
    }
    ```
*   To provide access to an account using a Seed Phrase:

    1. Create a file `nano ~/.aragon/mnemonic.json`
    2. Add the following inside the file

    ```
    {
      "rpc": "<RPC url for your target network, for example "<https://rpc-mainnet.matic.network>" for Polygon>",
    "mnemonic": "your mnemonic phrase..."
    }
    ```

### Step 2

**Description:** Deploy [AragonOS](https://github.com/aragon/aragonOS/tree/next/contracts/apps), which contains all main contracts, to the target network. This will allow creating new DAOs as well as publish apps to APM.

1. Clone [AragonOS](https://github.com/aragon/aragonOS/tree/next/contracts/apps) repository
2.  Checkout to `master` branch instead of default `next` branch.

    The `master` branch contains AragonOS v4.4.0 latest stable version. Whereas the `next` has more features, but we don’t want a disputable feature for now.
3. Run `yarn`
4. Run `yarn add @aragon/truffle-config-v4`
5.  Update `node_modules/@aragon/truffle-config-v4/truffle-config.js` with the new network information

    Example:

    ```jsx
    mumbai: {network_id: 80001,provider: providerForNetwork('mumbai'),gas: 6.9e6}
    ```
6. Run `yarn compile`
7.  Deploy `ENS` to the target network

    In case the network does not have an official ENS registry, one should deploy it themselves using provided `ENSFactory`.

    If there is an official ENS deployment, you can use it or deploy a new ENS. If you decide on using an official ENS, make sure to purchase the `aragonpm.eth` domain with the key provided in step 1.

    Run the command below in AragonOS repo, substituting placeholder values:

    ```
    OWNER=<Your Public Key> npx truffle exec --network <target network> scripts/deploy-test-ens.js
    ```
8.  Deploy `DaoFactory`

    DAO factory will already include other contracts that are necessary for the contract deployment. It is a very large contract, and we are aware that some networks do not offer enough gas per block to deploying it.

    You might encounter RPC failing due to making too many calls in a short period of time. As a solution split the deployment script into several subparts or use a more reliable RPC in step 1.

    Run the command below in AragonOS repo, substituting placeholder values:

    ```
    OWNER=<Your Public Key> npx truffle exec --network <target network> scripts/deploy-daofactory.js
    ```
9.  Deploy `APM` (Aragon Package Manager) to the target network

    You should be able to deploy [APM](https://github.com/aragon/apm) in its own repository. However, currently, it does not work due to an unknown issue. **If you could fix it, it would be greatly appreciated and you will get rewarded!**

    As a workaround, you should deploy the APM in the AragonOS repository.

    Run the command below in AragonOS repo, substituting placeholder values:

    ```
    OWNER=<Your Public Key> ENS=<ENS Registry address from step>  DAO_FACTORY=<DAO Factory address from step 2> npx truffle exec --network <target network> scripts/deploy-apm.js
    ```

### Step 3

**Description:** Deploy [AragonID](https://github.com/aragon/aragon-id).

1. Clone the repo master branch.
2. Run `yarn` to install packages
3. Setup truffle-config on `node_modules/@aragon/truffle-config-v4/truffle-config.js` as previous step
4.  Update the `truffle.js` to point to the right truffle-config. Basically replace its contents with

    ```jsx
    module.exports = require("@aragon/truffle-config-v4")
    ```
5. run `yarn compile` to build the contracts
6.  Run the following script:

    ```
    OWNER=<Your public key> ENS=<ENS Registry address from step> npx truffle exec --network <target network> scripts/deploy-beta-aragonid.js
    ```

### Step 4

**Description:** Deploy standard [Aragon Apps](https://github.com/aragon/aragon-apps) to the AragonPM.

1. Clone [Aragon Apps](https://github.com/aragon/aragon-apps) repository
2.  Provide your Private Key

    Create `.env` file in the root directory of the [Aragon Apps](https://github.com/aragon/aragon-apps) repository with the following content:

    ```
    ETH_KEYS=0x<Your Private Key>
    ```
3.  Update `node_modules/@aragon/hardhat-config/hardhat.config.js` with the new network information. Ex:

    ```jsx
    mumbai: providerForNetwork('mumbai')
    ```
4.  Deploy an app

    Repeat this for each app inside the `\\apps` directory. We will use the Finance app here as an example.

    **IMPORTANT:** Do not try to deploy `voting-disputable` and `agreement` apps they require Aragon Court instance present on the target network.

    1. Navigate to the apps directory (`\\apps\\finance`)
    2.  Change `arapp.json`

        In the `environment` part add information about your target network.

        For the `registry` variable specify ENS address that we have obtained in step 2.

        ```
            "<target netwrok>": {
              "registry": "<ENS Registry address>", 
              "appName": "finance.aragonpm.eth", // app name
              "network": "<target network>"
            }
        ```
    3. Run `yarn`
    4. Run `yarn compile` to generate contracts
    5. Run `yarn build` to build the UI App part
    6.  Start a local version of IPFS with `ipfs daemon`

        If you don't have IPFS installed, check here [https://docs.ipfs.io/install/command-line/](https://docs.ipfs.io/install/command-line/) how to install it
    7.  Publish the App to APM

        ```jsx
        npx hardhat publish major --network mumbai --ipfs-api-url <http://localhost:5001>
        ```
    8. Download the files that were uploaded to IPFS with `ipfs get <CID>`. The CID is available from previous step
    9. Compress the folders that were downloaded and send to [product@aragon.org](mailto:product@aragon.org) so they can be pinned.

### Step 5

**Description:** Deploy standard [DAO Templates](https://github.com/aragon/dao-templates) to the AragonPM.

1. Clone [DAO Templates](https://github.com/aragon/dao-templates) repository
2.  Provide your Private Key

    Create `.env` file in the root directory of the [Aragon Apps](https://github.com/aragon/aragon-apps) repository with the following content:

    ```
    ETH_KEYS=0x<Your Private Key>
    ```
3.  Go to `/shared` directory and run `yarn` and then `yarn link`

    If you have problems with node version on installing dependencies, add `--ignore-engines` to the command
4.  Deploy a template

    Repeat this for each template inside the `/templates` directory. We will use the Company template here as an example.

    **IMPORTANT:** Please only try to deploy `company`, `reputation` and `membership` templates, as other templates do not contain all required components.

    1. Navigate to the templates directory (`/templates/company`)
    2. Run `yarn link @aragon/templates-shared`
    3. Run `yarn` to install dependencies
    4. setup truffle-config on `node_modules/@aragon/truffle-config-v4/truffle-config.js` as previous step
    5.  Change `arapp.json`

        In the `environment` part add information about your target network.

        For the `registry` variable specify ENS address that we have obtained in step 2.

        ```
           "<target network>": {
              "registry": "<ENS Registry address>", 
              "appName": "finance.aragonpm.eth", // app name
              "network": "<target network>",
        	    "wsRPC": "<RPC url for your target network, for example wss://matic-testnet-archive-ws.bwarelabs.com for Polygon>"
            }
        ```
    6. switch to node 10
    7. Run `yarn compile`
    8. switch to node 12
    9.  Change `package.json`

        Add a new script below to the `scripts` section.

        Please note that if you are using the official ENS, then you should also acquire the `aragonid.eth` domain for the step below to work.

        ```
        "deploy:<target network>": "truffle exec ./scripts/deploy.js --network <target network> --ens <ENS Registry address from step 2> --dao-factory <DAO Factory address from step 2>"
        ```
    10. Run `yarn deploy:<target network>` to deploy the Template

        This should deploy additionally [AragonId](https://github.com/aragon/aragon-id) and [MiniMe Token Factory](https://github.com/aragon/minime). Copy the [MiniMe Token Factory](https://github.com/aragon/minime) address and when deploying the next template add it to the script in step 7:

        ```
        "deploy:<target network>": "truffle exec ./scripts/deploy.js --network <target network> --ens <ENS Registry address from step 2> --dao-factory <DAO Factory address from step 2> --mini-me-factory <MiniMe Factory address that we have just deployed>"
        ```
    11. Start a local version of IPFS with `ipfs daemon`

        If you don't have IPFS installed, check here [https://docs.ipfs.io/install/command-line/](https://docs.ipfs.io/install/command-line/) how to install it
    12. Publish the Template to APM

        ```
        npx hardhat compile && npx hardhat publish major --contract <Template contract that we got in previous step> --network <target network> --ipfs-api-url <http://localhost:5001/>
        ```
