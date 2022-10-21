# connect()

{% hint style="info" %}
This file documents the **main exports of the library**.
{% endhint %}

## connect(location, connector, options)

Connects and returns an `Organization` for `location`.

| Name               | Type                                                          | Description                                                                                                                  |
| ------------------ | ------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `location`         | `String`                                                      | The Ethereum address or ENS domain of an Aragon organization.                                                                |
| `connector`        | `Connector` or `[String, Object]` or `String`                 | Accepts a `Connector` instance, and either a string or a tuple for embedded connectors and their config.                     |
| `options`          | `Object`                                                      | The optional configuration object.                                                                                           |
| `options.ethereum` | `EthereumProvider`                                            | An [EIP-1193](https://eips.ethereum.org/EIPS/eip-1193) compatible object.                                                    |
| `options.network`  | [`Networkish`](types.md#networkish)                           | The network to connect to. Defaults to `1`.                                                                                  |
| `options.ipfs`     | [`IpfsResolverDeclaration`](types.md#ipfsresolverdeclaration) | The IPFS gateway and cached results. Defaults to `'https://ipfs.eth.aragon.network/ipfs/{cid}{path}'` and `40` respectively. |
| returns            | `Promise<Organization>`                                       | An `Organization` instance.                                                                                                  |

This function can throw the following errors:

| Error type                                                 | Description                                       |
| ---------------------------------------------------------- | ------------------------------------------------- |
| [`ErrorInvalidConnector`](errors.md#errorinvalidconnector) | An unsupported or invalid connector was provided. |
| [`ErrorInvalidEthereum`](errors.md#errorinvalidethereum)   | The Ethereum provider doesn’t seem to be valid.   |
| [`ErrorInvalidLocation`](errors.md#errorinvalidlocation)   | The provided location doesn’t seem to be valid.   |
| [`ErrorInvalidNetwork`](errors.md#errorinvalidnetwork)     | The network is incorrect or unsupported.          |

### Example

```javascript
import connect from '@aragon/connect'

// Connections should get wrapped in a try / catch to capture connection errors
try {
  // Connect to an org through The Graph
  const org1 = await connect('org1.aragonid.eth', 'thegraph')

  // Specify a different Chain ID
  const org3 = await connect('org3.aragonid.eth', 'thegraph', { network: 4 })

  // Specify a configuration for the connector
  const org3 = await connect('org3.aragonid.eth', [
    'thegraph',
    { orgSubgraphUrl: 'http://…' },
  ])

  // Custom connector
  const org4 = await connect(
    'org4.aragonid.eth',

    // CustomConnector implements IConnector
    new CustomConnector()
  )
} catch (err) {
  if (err instanceof ConnectionError) {
    console.error('Connection error')
  } else {
    console.error(err)
  }
}
```



> <mark style="color:purple;">**Do you have a question? Leave your comments here at our Discourse forum**</mark>** 👇**

{% embed url="https://support.aragon.org/c/dev-support/20" %}
