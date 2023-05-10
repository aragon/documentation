# Box

`Box` is a component that renders as a surface as defined by aragonDS, and can optionally have a heading. It is commonly used in either slot of the `Split` component.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Box, Main, Split } from '@aragon/ui'

function App() {
  return (
    <Main>
      <Split
        primary={<Box>Primary content</Box>}
        secondary={<Box heading="Secondary">Secondary content</Box>}
      />
    </Main>
  )
}
```

## Props <a href="#props" id="props"></a>

#### `heading` <a href="#heading" id="heading"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

Displays a heading on top of the `Box`. Generally used when the `Box` is passed to the `secondary` prop of `Split`.

#### `children` <a href="#children" id="children"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

The content of `Box`.

#### `padding` <a href="#padding" id="padding"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | None          |

The padding applied to the content of the box (i.e. the part below the heading, when set).

Note: when used in the `primary` slot of the `Split` component, the content padding will adapt to the layout (one or two columns). Set it to any value to override this behavior.
