# SyncIndicator

When active, indicates a syncing state.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Main, SyncIndicator } from '@aragon/ui'

function App() {
  return (
    <Main>
      <SyncIndicator />
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

#### `label` <a href="#label" id="label"></a>

| TYPE   | DEFAULT VALUE     |
| ------ | ----------------- |
| `Node` | `"Syncing data…"` |

The label displayed by the indicator.

Note: the “folded hands” emoji 🙏 will be appended to the label. Use `children` if you wish to override this behavior.

#### `children` <a href="#children" id="children"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Node` | None          |

Use `children` to override `label` and its emoji decoration.

#### `shift` <a href="#shift" id="shift"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `0`           |

Use this property to shift the position of the sync indicator from its “end position” (right on left to right languages).
