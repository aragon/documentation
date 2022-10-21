# FloatIndicator

A component displayed over the rest of the interface, to indicate a temporary state.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Main, FloatIndicator } from '@aragon/ui'

function App() {
  return (
    <Main>
      <FloatIndicator>Fetching data…</FloatIndicator>
    </Main>
  )
}
```

## Props <a href="#props" id="props"></a>

#### `visible` <a href="#visible" id="visible"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `true`        |

Set to `true` to display the indicator.

#### `children` <a href="#children" id="children"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

The content of the indicator.

#### `shift` <a href="#shift" id="shift"></a>

* Type: `Number`
* Default value: `0`

Use this property to shift the position of the float indicator from its “end position” (right on left to right languages).
