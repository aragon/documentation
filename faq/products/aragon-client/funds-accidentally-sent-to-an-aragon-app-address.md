# アラゴンアプリのアドレスに誤って送信した資金を回収する方法

もしあなたが誤ってインストールされたAppのアドレスにトークンを送ってしまった場合、トークンを回収し、あなたのDAO資金を管理するVaultに送ることができます。これを行うには2つの方法があります。

1. [インターフェースから内蔵のコンソール機能を利用する](funds-accidentally-sent-to-an-aragon-app-address.md#intfsukaranokonsruwosuru)
2. [コマンドラインからaragon CLIを利用する](funds-accidentally-sent-to-an-aragon-app-address.md#komandorainkaraaragon-cliwosuru)

{% hint style="danger" %}
コンソールを使用することを強くお勧めします。
{% endhint %}



### インターフェースから内蔵のコンソール機能を利用する <a href="#inter" id="inter"></a>

以下の手順で行います。

DAOを開き、DAOの Webアドレスの末尾に`/console`を追加します。URLはこのようになります。`https://client.aragon.org/#/<your-dao-name>/console`

{% hint style="warning" %}
上記URLのをあなたのDAOの名前に置き換えてください。
{% endhint %}



以下のような画面が表示されます。

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

次にDAOでトランザクションを実行するためのコマンドである`Exec`を選択します。

ここで、資金が誤って送られたアプリを選択します。この例では、資金が誤ってFinance Appに送られたので、`Finance`を選択します。

<figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

[Github（英語のみ）](https://github.com/aragon/aragon-apps/blob/631048d54b9cc71058abb8bd7c17f6738755d950/apps/finance/contracts/Finance.sol#L399-L410)のFinance Appのソースコードには、`recoverToVault`という関数があり、この関数を利用します。

それでは、Aragon コンソールからこの関数を呼び出してみましょう。コンソールのコマンドに`recoverToVault(address _token)`を追加する必要がありますが、まず`address _token`をFinance Appに誤って送信されたトークンのコントラクト アドレスに置き換えてください。

この例の場合、アドレスは`0x3255D2D022Ef80F58dA2D107235010367cCdF0fD`なので、コンソールのコマンドに`recoverToVault(0x3255D2D022Ef80F58dA2D107235010367cCdF0fD)`を追加してください。この例のコマンドは、次のようになります。

```
exec/0xa4bb9c789cccdce9565ee5a6d066dccef05c6a42/recoverToVault(0x3255D2D022Ef80F58dA2D107235010367cCdF0fD)
```

Enterを選択しましょう。

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

ここで、Create transactionをクリックして、トランザクションを確定します。

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

その後、Metamaskでトランザクションを承認します。

{% hint style="danger" %}
DAOを作成したアカウント、またはDAOトークンを保持しているアカウントでトランザクションに署名してください。
{% endhint %}

これで、Finance Appにアクセスすると、資金が表示されるはずです。

この例では、BRTトークンがFinance AppからVault Appに回収されています。

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### コマンドラインからaragon CLIを利用する

以下の手順で行います。

1. DAOとやり取りするためのコマンドラインインターフェイスである[argonCLIをインストール（英語のみ）](https://hack.aragon.org/developers/tools/aragoncli)します。
2. DAOのデータ（例：ABI）にアクセスする方法をargonCLIに提供するために、ターミナルで`aragon ipfs`を実行してください。
3. [aragonCLI が使用する秘密鍵を設定（英語のみ）](https://hack.aragon.org/developers/tools/guides/how-to-sign-with-web3-providers)し、ガス代を支払うためにこの秘密鍵のアドレスに少額のETHを入金してください。
4. aragonCLIから以下のトランザクションコマンドを送信します。addressを、あなたのスタックしたトランザクションに関連する対応するアドレスに置き換えてください。

```powershell
dao exec OrganizationAddress AppAddress recoverToVault TokenContractAddress --environment aragon:mainnet
```

`OrganizationAddress`はスタックした資金を収容しているシステムのアドレス、`AppAddress`はスタックした資金を送ったアプリのアドレス、`TokenContractAddress`は送ったトークンのコントラクトアドレスです。

例えば、genesis.aragonid.ethというDAOのFinance Appのアドレスに[DAI（英語のみ）](https://etherscan.io/token/0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359)を送った場合、aragonCLIから送信するトランザクションコマンドは次のようになります。

```
dao exec 0x8A83D4bCE45b4C4F751f76cf565953D1E4A3BF0a 0x98516C82Bda8B3dE6E2670B718848949Ae6a4643 recoverToVault 0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359 --environment aragon:mainnet
```

Chris Hobcroft氏が[GitHubのコメント（英語のみ）](https://github.com/ethereum-cat-herders/funding/issues/2#issuecomment-477174751)でこれらの手順を説明してくれたことに感謝します。
