# Tabs

A simple tabs component.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { useState } from 'react'
import { Tabs } from '@aragon/ui'

const App = () => {
  const [selected, setSelected] = useState(0)
  return (
    <Tabs
      items={['Orange', 'Pear', 'Cherry']}
      selected={selected}
      onChange={setSelected}
    />
  )
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.19.48.png>)

## Props <a href="#props" id="props"></a>

#### `items` (required) <a href="#items-required" id="items-required"></a>

* Type: `Array` of React nodes

The items that are going to be displayed in every tab.

#### `selected` <a href="#selected" id="selected"></a>

* Type: `Number`
* Default: `0`

The currently selected tab, using its index.

#### `onChange` <a href="#onchange" id="onchange"></a>

* Type: `Function`

When a tab is selected, this function gets called with the index of the tab as a parameter.
