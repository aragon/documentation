# Root

`Root` can be used to re render a component at the top level in the DOM tree. `Root.Provider` can be used to redefine the root level.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Root } from '@aragon/ui'

function App() {
  return (
    <div>
      <p>Rendered in the current element</p>
      <Root>
        <p>Rendered at the root level of the DOM tree</p>
      </Root>
    </div>
  )
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-26 alle 21.19.19.png>)
