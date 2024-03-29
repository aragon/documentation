# Global configuration

{% hint style="info" %}
The <mark style="color:blue;">arapp.json file</mark> contains metadata for your app, and the <mark style="color:blue;">manifest.json</mark> defines end-user specific configurations.
{% endhint %}

## The arapp.json file

The arapp.json file contains metadata for your app. These are the fields which need to be present:

* `roles`: An array of all the roles that your app has. Each role has the following properties:
  * `id`: The identifier of the role as it is defined in the contract.
  * `name`: A description of the role in the app.
  * `params`: The names of any parameters for the role.
* `environments`: An object containing deploy environment configurations.
  * `env_name`: An object containing the configuration for a specific environment. `env_name` can be any name you choose.
    * `appName`: The ENS name of your app where the aragonPM repo can be located.
    * `network`: The network to use for this environment.
    * `wsRPC`: (optional) If present is used by aragon.js as its data provider.
    * `registry`: (optional) The address of the ENS registry for this environment. Defaults to the default ENS registry for this network.
    * `apm`: An object containing apm options.
      * `ipfs`
        * `gateway`: An URI to the IPFS Gateway to read files from. Defaults to `http://localhost:8080/ipfs`.
        * `rpc`: An URI to the IPFS node used to publish files. Defaults to `http://localhost:5001#default`.
* `path`: The path to the main contract in your app.
* `links`: (optional) Array of links. Each object in that array should have name and address attributes. Used to links any linkable contracts into the deploying contract bytecode.

#### Example <a href="#example" id="example"></a>

This is the arapp.json of the app build in the [tutorial](../guides/your-first-aragon-app.md) configure with default environments:

```json
{
  "roles": [
    {
      "id": "INCREMENT_ROLE",
      "name": "Increment the counter",
      "params": []
    },
    {
      "id": "DECREMENT_ROLE",
      "name": "Decrement the counter",
      "params": []
    }
  ],
  "environments": {
    "aragon:local": {
      "network": "localhost",
      "appName": "foo.aragonpm.eth"
    },
    "aragon:rinkeby": {
      "apm": {
        "ipfs": {
          "gateway": "https://ipfs.eth.aragon.network/ipfs"
        }
      },
      "registry": "0x98df287b6c145399aaa709692c8d308357bc085d",
      "appName": "foo.open.aragonpm.eth",
      "wsRPC": "wss://rinkeby.eth.aragon.network/ws",
      "network": "rinkeby"
    },
    "aragon:staging": {
      "apm": {
        "ipfs": {
          "gateway": "https://ipfs.eth.aragon.network/ipfs"
        }
      },
      "registry": "0xfe03625ea880a8cba336f9b5ad6e15b0a3b5a939",
      "appName": "foo.open.aragonpm.eth",
      "wsRPC": "wss://rinkeby.eth.aragon.network/ws",
      "network": "rinkeby"
    },
    "aragon:mainnet": {
      "apm": {
        "ipfs": {
          "gateway": "https://ipfs.eth.aragon.network/ipfs"
        }
      },
      "registry": "0x314159265dd8dbb310642f98f50c066173c1259b",
      "appName": "foo.aragonpm.eth",
      "wsRPC": "wss://mainnet.eth.aragon.network/ws",
      "network": "mainnet"
    }
  },
  "path": "contracts/CounterApp.sol",
  "links": [
    {
      "name": "CounterExtension",
      "address": "0x82606d5d2dB55Ac1D36a011dbbA769c729349f56"
    }
  ]
}
```

#### How to use environments <a href="#how-to-use-environments" id="how-to-use-environments"></a>

If you want to learn how use environments in practice check the guides to learn [how to publish in diferent environments](../guides/publish-to-aragonpm.md).

## The manifest.json file <a href="#the-manifestjson-file" id="the-manifestjson-file"></a>

The manifest.json defines end-user specific configurations:

* `name`: Human-readable name of your app.
* `author`: (optional) Author of the app.
* `description`: Small description of the app.
* `detail_url`: (optional) Path to markdown file with details of the app.
* `source_url`: (optional) Link to the source code of the app.
* `icons`: (optional) An array of all the icons that your app has. Each icon has the following properties:
  * `src`: Path to the icon's image.
  * `sizes`: Size of the icon.
* `screenshots`: (optional) An array of all the screenshots that your app has. Each screenshot has the following properties:
  * `src`: Path to the screenshot's image.
* `script`: (optional) Background script path.
* `start_url`: Path to the starting URL.

