# EthIdenticon

A component to get the Ethereum Identicon, an image that identifies Ethereum Accounts.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { EthIdenticon } from '@aragon/ui'

const App = () => (
  <EthIdenticon
    address="0xcafE1A77e84698c83CA8931F54A755176eF75f2C"
    scale={3}
    radius={1}
    soften={0.7}
  />
)
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.47.23.png>)

## Props <a href="#props" id="props"></a>

#### `address` <a href="#address" id="address"></a>

| TYPE     | DEFAULT VALUE   |
| -------- | --------------- |
| `String` | None (Required) |

Ethereum adress.

#### `scale` <a href="#scale" id="scale"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `1`           |

Size of the image.

#### `radius` <a href="#radius" id="radius"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `0`           |

Border radius of the image. It helps to show curved edges or make circles.

#### `soften` <a href="#soften" id="soften"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `0.3`         |

Softens the colors of the image.
