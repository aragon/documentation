# ContextMenu

A contextual menu.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { ContextMenu, ContextMenuItem } from '@aragon/ui'

const App = () => (
  <ContextMenu>
    <ContextMenuItem>Some Action</ContextMenuItem>
    <ContextMenuItem>Another Action</ContextMenuItem>
  </ContextMenu>
)
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.16.46.png>)

## Props <a href="#props" id="props"></a>

#### `zIndex` <a href="#zindex" id="zindex"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | 0             |

zIndex of ContextMenu.

#### disabled <a href="#disabled" id="disabled"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `false`       |

Disable the Context Menu Button.
