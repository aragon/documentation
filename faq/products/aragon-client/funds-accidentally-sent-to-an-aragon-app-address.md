# How to Recover Funds accidentally sent to an Aragon App address

If you accidentally sent tokens to the address of an App installed in an Aragon organization, you can recover the tokens and send them to the organization's Vault, the organisation App which should hold your DAO funds. There are two ways to do this:

1. [Using the inbuilt (but hidden) **Console feature** from the DAO interface](funds-accidentally-sent-to-an-aragon-app-address.md#recover-your-funds-using-the-console-feature)
2. [Using **aragonCLI** from the command line](funds-accidentally-sent-to-an-aragon-app-address.md#undefined)

{% hint style="danger" %}
We strongly recommend using the _Console option_ since it is much easier
{% endhint %}



### Recover your funds using the Console feature

Use the following steps:

Open your DAO, and add `/console` to the end of your DAO web address. The URL would look like this: `https://client.aragon.org/#/<your-dao-name>/console`

{% hint style="warning" %}
Replace `<your-dao-name>` with the name of your DAO in the above URL
{% endhint %}



You should see something like the below:

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>



Next select `Exec` which is a command used to perform transactions in DAOs.

Here you select the App to which the funds were accidentally sent. In this example, funds were accidentally sent to the Finance App so we select `Finance`:

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>



In the source code of the Finance App on [Github ](https://github.com/aragon/aragon-apps/blob/631048d54b9cc71058abb8bd7c17f6738755d950/apps/finance/contracts/Finance.sol#L399-L410)you can find a function called `recoverToVault` , exactly what we need!

We will now call this function from the Aragon Console. To do so we will have to add `recoverToVault(address _token)` to the command in the console, but first we will replace `address _token` with the contract address of the token which were accidentally sent to the Finance App.

In the case of this example the address is `0x3255D2D022Ef80F58dA2D107235010367cCdF0fD` , so we will add  `recoverToVault(0x3255D2D022Ef80F58dA2D107235010367cCdF0fD)`to the command in the Console. The full command for this example is now the following:

```
exec/0xa4bb9c789cccdce9565ee5a6d066dccef05c6a42/recoverToVault(0x3255D2D022Ef80F58dA2D107235010367cCdF0fD)
```



Now click _Enter_:

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>



Now confirm the transaction by clicking _Create transaction_:

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>



Then confirm the transaction in your Web3 wallet (most often MetaMask).

{% hint style="danger" %}
Make sure you use a Web3 account which has either created the DAO or (and) is holding your DAO-tokens to sign this transaction
{% endhint %}

Now go to the Finance App in your organisation, and your funds should magically appear there! :sweat\_smile::tada:

In this example BRT tokens have been recovered from the Finance to the Vault App:

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

###

### Recover your funds using aragonCLI

Use the following steps:

1. [Install the aragonCLI](https://hack.aragon.org/developers/tools/aragoncli) which is a command line interface for interacting with Aragon organizations.
2. Run `aragon ipfs` in your Terminal in order to provide aragonCLI with a way to access data (e.g. ABIs) for Aragon organizations.
3. [Set a private key for the aragonCLI to use](https://hack.aragon.org/developers/tools/guides/how-to-sign-with-web3-providers), then send some ether to the address for this private key to pay for gas.
4. Send the following transaction command from the aragonCLI, replacing each "address" with the corresponding address relevant to your stuck transaction:

```powershell
dao exec OrganizationAddress AppAddress recoverToVault TokenContractAddress --environment aragon:mainnet
```

Where the `OrganizationAddress` \_\_ is the address of the organization housing the stuck funds, the `AppAddress` is the address of the app you sent the stuck funds to, and the `TokenContractAddress` is the address of the token contract for the token you sent.

For example, if you sent [Dai](https://etherscan.io/token/0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359) to the Finance app address of the <mark style="color:blue;">genesis.aragonid.eth</mark> organization, then the transaction command you would send to from the aragonCLI would be:

```
dao exec 0x8A83D4bCE45b4C4F751f76cf565953D1E4A3BF0a 0x98516C82Bda8B3dE6E2670B718848949Ae6a4643 recoverToVault 0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359 --environment aragon:mainnet
```

Thanks to Chris Hobcroft for documenting these steps in [this GitHub comment](https://github.com/ethereum-cat-herders/funding/issues/2#issuecomment-477174751).
