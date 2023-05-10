# AddressField

A field component to display Ethereum Addresses.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { AddressField } from '@aragon/ui'

function App() {
  return <AddressField address="0xcafE1A77e84698c83CA8931F54A755176eF75f2C" />
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 23.08.14.png>)

## Props <a href="#props" id="props"></a>

#### `address` <a href="#address" id="address"></a>

| TYPE     | DEFAULT VALUE   |
| -------- | --------------- |
| `String` | None (Required) |

Adress to display in the field.

#### **Example:**

```jsx
<AddressField address="0xcafE1A77e84698c83CA8931F54A755176eF75f2C" />
```

#### `autofocus` <a href="#autofocus" id="autofocus"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `true`        |

Focus the text field when the component gets mounted.

#### `icon` <a href="#icon" id="icon"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Node` | None          |

Icon to display in the field. Can pass anything that can be rendered, such as num, string, DOM elements, an array of them, or fragments that contain them.

#### **Example:**

```jsx
<AddressField
  address="0xcafE1A77e84698c83CA8931F54A755176eF75f2C"
  icon={<img />}
/>
```
