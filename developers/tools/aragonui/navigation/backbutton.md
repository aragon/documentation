# BackButton

A button used to go back to the previous screen. To be used with the `Bar` component. Adapts to the space available.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { BackButton, Bar, Main } from '@aragon/ui'

function App() {
  return (
    <Main>
      <Bar primary={<BackButton onClick={() => goBack()} />} />
    </Main>
  )
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.22.47.png>)

## Props <a href="#props" id="props"></a>

> Additional props will get passed to the internal `ButtonBase` component.

#### `label` <a href="#label" id="label"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `String` | `"Back"`      |

The label displayed on the button.

#### `onClick` <a href="#onclick" id="onclick"></a>

| TYPE                  | DEFAULT VALUE |
| --------------------- | ------------- |
| `Function`: `() -> *` | None          |

Gets called when the user activates the button, by either clicking on it or using the enter key of the keyboard.
