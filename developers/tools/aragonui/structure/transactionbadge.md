# TransactionBadge

A component to get a badge based on a transaction.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { TransactionBadge } from '@aragon/ui'

function App() {
  return <TransactionBadge transaction="0x281c36aee91…c31ef3fc115" />
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.41.43.png>)

## Props <a href="#props" id="props"></a>

#### `transaction` <a href="#transaction" id="transaction"></a>

| TYPE     | DEFAULT VALUE   |
| -------- | --------------- |
| `String` | None (required) |

The transaction hash.

If this is not supplied or an invalid transaction hash is supplied, the badge will display "Invalid".

#### `shorten` <a href="#shorten" id="shorten"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Bool` | `true`        |

If true, only render the first and last four characters of the transaction hash (excluding the '0x' prefix).

#### `networkType` <a href="#networktype" id="networktype"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `String` | `main`        |

Checks the type of network to get Etherscan's URL.

#### `disabled` <a href="#disabled" id="disabled"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Bool` | `true`        |

Disable the link.
