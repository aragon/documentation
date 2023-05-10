# Split

`Split` creates a two column layout when the available horizontal space makes it possible. If not, it renders as a single column. Its slots generally contain components like `Box` or `DataView`.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Box, DataView, Main, Split } from '@aragon/ui'

function App() {
  return (
    <Main>
      <Split
        primary={<DataView />}
        secondary={<Box heading="Secondary">Secondary content</Box>}
      />
    </Main>
  )
}
```

## Props <a href="#props" id="props"></a>

#### `primary` <a href="#primary" id="primary"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

In two columns mode, this takes the wider space. It appears on the left (for left-to-right languages) or the right if `invert` is set to `horizontal`.

In single column mode, it appears above the `secondary` slot, or below if `invert` is set to `vertical`.

#### `secondary` <a href="#secondary" id="secondary"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

In two columns mode, this is the narrower part. It appears on the right (for left to right languages) or the left if `invert` is set to `horizontal`.

In single column mode, it appears below the `primary` slot, or above if `invert` is set to `vertical`.

#### `invert` <a href="#invert" id="invert"></a>

| TYPE                                     | DEFAULT VALUE |
| ---------------------------------------- | ------------- |
| `"none"`, `"horizontal"` or `"vertical"` | `"none"`      |

Invert the two slots, vertically or horizontally.
