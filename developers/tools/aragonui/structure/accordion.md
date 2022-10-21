# Accordion

A simple accordion component.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Main, Accordion } from '@aragon/ui'

function App() {
  return (
    <Main>
      <Accordion
        items={[
          ['Row content', 'Expandable content'],
          [<div>Row content</div>, <div>Expandable content</div>],
        ]}
      />
    </Main>
  )
}
```

## Props <a href="#props" id="props"></a>

#### `items` <a href="#items" id="items"></a>

| TYPE               | DEFAULT VALUE   |
| ------------------ | --------------- |
| `Array` of `Array` | None (required) |

The items composing the accordion list. The first entry of each nested array is the content of the row, while the second entry is the content of the expandable part.
