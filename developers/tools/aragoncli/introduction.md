# Introduction

{% hint style="info" %}
The aragonCLI (Command Line Interface) is used to <mark style="color:blue;">create, develop, configure</mark> and <mark style="color:blue;">manage Aragon DAOs</mark> and <mark style="color:blue;">Applications</mark>.
{% endhint %}

## Installation

### Installation pre-requisites <a href="#installation-pre-requisites" id="installation-pre-requisites"></a>

The following must be installed prior to installation:

* Node + npm + yarn
  * We recommend to install Node using Node Version Manager or NVM. You can find instructions on how to install NVM and Node [here](https://techstacker.com/run-multiple-node-versions-node-nvm/).
  * After downloading and unpacking, you must add the /bin folder to your $PATH.

{% hint style="danger" %}
Dependencies of aragonCLI are constantly [updated](https://github.com/aragon/aragon-cli/pulls?q=) which result in Node version errors. Use [**NVM**](https://techstacker.com/run-multiple-node-versions-node-nvm/) **** to install and select the right Node version. For compatibility across OS use **`Node v12.7 LTS`** version.



Also using _yarn_ instead of _npm_ as package manager is advised in some cases. Find how to install [yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable).
{% endhint %}

For Linux:

* git
  * Install this using the command `sudo apt install git`
* python
  * Install this using the command `sudo apt install python`
* make
  * Install this using the command `sudo apt install make`
* g++
  * Install this using the command `sudo apt install g++`

For Mac:

* git
  * Install this using the [official installer](https://sourceforge.net/projects/git-osx-installer/). We recommend using the package manager [Homebrew](https://brew.sh/), in this case use the command `brew install git`.

Note: Python comes pre-installed on Mac.

For Windows:

* windows-build-tools
  * Install with `npm i windows-build-tools`

### Install aragonCLI <a href="#install-aragoncli" id="install-aragoncli"></a>

The aragonCLI can be installed from NPM:

```
npm install -g @aragon/cli
```

{% hint style="danger" %}
Dependencies of aragonCLI are constantly [updated](https://github.com/aragon/aragon-cli/pulls?q=) which result in Node version errors. Use [**NVM**](https://techstacker.com/run-multiple-node-versions-node-nvm/) **** to install and select the right Node version. For compatibility across OS use **`Node v12.7 LTS`** version.



Also using _yarn_ instead of _npm_ as package manager is advised in some cases. Find how to install [yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable).
{% endhint %}

In case the above does not work, aragonCLI can also be built and installed from the source with the following commands:

```
git clone https://github.com/aragon/aragon-cli.git
cd aragon-cli
yarn
cd packages
yarn
npm run build
cd cli
npm install -g
cd ../create-aragon-app
npm install -g
cd ../toolkit
npm install -g
cd ../../..
```

{% hint style="danger" %}
If you're seeing errors similar to:

`EACCES: permission denied`

It's probably because you originally installed Node with root permissions. Because of this, writing to your npm directory (`npm -i -g`) requires root permissions too.

While it's not a good idea to have Node installed this way, one way to quickly give yourself root permissions is to run the slightly modified command:

`sudo npm i -g --unsafe-perm @aragon/cli`

An arguably better way to fix the problem is to follow the steps outlined in this [stackoverflow answer.](https://stackoverflow.com/a/24404451)
{% endhint %}

After installing aragonCLI, the main `aragon` executable will be available for use. Also, the `dao` alias will be available which is a shortcut for `aragon dao` commands.

### **The \~/.aragon directory**

The aragonCLI creates the `.aragon` directory under the user's home directory, where it saves the state of the devchain and the [Aragon client](../the-basics/the-aragon-client.md). At the moment, this folder is only automatically created after running `aragon devchain` once, but can also be created by via `mkdir ~/.aragon`.

### **Set a private key**

{% hint style="danger" %}
**Warning**

The default mnemonic for the Aragon CLI is the same for all users. If you are going to deploy contracts to public networks it is highly recommended that you use your own web3 provider and set your own private key.
{% endhint %}

You can configure a private key for the Aragon CLI in `~/.aragon`. To do so you will need to create a file `<network>_key.json` (eg. `rinkeby_key.json`) with this structure:

```json
{
  "rpc": "https://<network>.infura.io",
  "keys": ["put-your-priv-key-here"]
}
```

{% hint style="info" %}
You can easily create a new file from the terminal. Find how to do it for [Linux and Mac](https://origin.geeksforgeeks.org/how-to-create-a-text-file-using-the-command-line-in-linux/) and for [Windows](https://techpp.com/2021/08/22/create-file-using-command-prompt-guide/).
{% endhint %}

Then if you use `--env aragon:<network>` when using the aragonCLI it will use that account.

You can also define an `~/.aragon/mnemonic.json` file like:

```json
{
  "mnemonic": "explain tackle mirror kit ..."
}
```

### **Install IPFS**

Since `v6.0.0` we separate the installation of `go-ipfs` from the aragonCLI. If you do not have it installed globally on your system we have a couple of commands to help with that:`aragon ipfs install` and `aragon ipfs uninstall`.

## Global options <a href="#global-options" id="global-options"></a>

Options that change the behaviour of the `aragon` command:

* `--environment`: The environment in your `arapp.json` that you want to use. Defaults to `aragon:local`. Check the other [default environments](global-configuration.md). You can also use it with the `--env` alias.
* `--gas-price`: Gas price in Gwei. Defaults to `2`.
* `--use-frame`: Use Frame as a signing provider and web3 provider.
* `--ens-registry`: Address of the ENS registry. This will be overwritten if the selected environment from your arapp.json includes a `registry` property.
* `--ipfs-gateway`: An URI to the IPFS Gateway to read files from. Defaults to `http://localhost:8080/ipfs`.
* `--ipfs-rpc`: An URI to the IPFS node used to publish files. Defaults to `http://localhost:5001#default`.
* `--cwd`: Project working directory.
* `--debug`: Show more output to terminal.
* `--silent`: Silence output to terminal.

#### Example <a href="#example" id="example"></a>

```
aragon <command> --environment aragon:mainnet --gas-price 1 --use-frame --debug
```

## create-aragon-app <a href="#create-aragon-app" id="create-aragon-app"></a>

This command will set up an Aragon app project so you can start building your app from a functional boilerplate.

```
npx create-aragon-app <app-name> [boilerplate]
```

* `app-name`: The name or ENS domain name for your app in an aragonPM Registry (e.g. `myapp` or `myapp.aragonpm.eth`). If only the name is provided it will create your app on the default `aragonpm.eth` registry.
*   `boilerplate`: (optional) the Github repo name or alias for a boilerplate to set up your app. The currently available boilerplates are:

    * `react`: this boilerplate contains a very basic Counter app and a webapp for interacting with it. It showcases the end-to-end interaction with an Aragon app, from the contracts to the webapp. Also it comes with a DAO Template which will allow for using your app to interact with other Aragon apps like the Voting app. You can read more about DAO Template [here](broken-reference).
    * `bare`: this boilerplate will just set up your app directory structure but contains no functional code.
    * `tutorial`: this boilerplate is the one used in the ["Your first Aragon app"](../guides/your-first-aragon-app.md) guide.
    * other available boilerplates you can find [here](https://github.com/aragon?q=boilerplate\&type=all\&language=\&sort=).



{% hint style="warning" %}
**Note**\
Npx is an independent package, it's not necessary to have `@aragon/cli` installed to use it. [npx](https://medium.com/@maybekatz/introducing-npx-an-npm-package-runner-55f7d4bd282b) comes with npm 5.2+. If you use npm 5.1 or earlier, you can't use `npx`. Instead, install `create-aragon-app` globally
{% endhint %}



> <mark style="color:purple;">**Do you have a question? Leave your comments here at our Discourse forum**</mark>** 👇**

{% embed url="https://support.aragon.org/c/dev-support/20" %}
