# Pagination

A component to navigate through paginated content.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Box, Main, Pagination } from '@aragon/ui'

function App() {
  const [selected, setSelected] = useState(0)
  return (
    <Main>
      <Box>
        <Pagination pages={20} selected={selected} onChange={setSelected} />
      </Box>
    </Main>
  )
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.21.22.png>)

## Props <a href="#props" id="props"></a>

#### `onChange` <a href="#onchange" id="onchange"></a>

| TYPE                              | DEFAULT VALUE |
| --------------------------------- | ------------- |
| `Function`: `(item: Number) -> *` | None          |

Gets called when the selected page changes. Takes the new index as a unique parameter.

#### `pages` <a href="#pages" id="pages"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `0`           |

The total amount of pages.

#### `selected` <a href="#selected" id="selected"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `0`           |

The currently selected page (zero based numbering).

#### `touchMode` <a href="#touchmode" id="touchmode"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `false`       |

When `true`, adapts the component to touch screens by making the targets bigge
