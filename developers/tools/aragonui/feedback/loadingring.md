# LoadingRing

An animated loading indicator.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Main, LoadingRing } from '@aragon/ui'

function App() {
  return <Main><LoadingRing /></Main>
}
```

## Props <a href="#props" id="props"></a>

#### `paused` <a href="#paused" id="paused"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `false`       |

Set to `true` to pause the animation. Can be useful to optimize performances if the component is rendered but hidden.

#### `mode` <a href="#mode" id="mode"></a>

| TYPE                             | DEFAULT VALUE |
| -------------------------------- | ------------- |
| `"two-parts"` or `"half-circle"` | `"two-parts"` |

One of the predefined styles for the loading ring. The default is “two-parts”, which is smaller than “half-circle”.
