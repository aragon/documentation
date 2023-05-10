# Switch

A simple switch component.

## Usage <a href="#usage" id="usage"></a>

```jsx
import React, { useState } from 'react'
import { Switch } from '@aragon/ui'

const App = () => {
  const [checked, setChecked] = useState(false)
  return <Switch checked={checked} onChange={setChecked} />
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 23.00.03.png>)

## Props <a href="#props" id="props"></a>

#### `checked` <a href="#checked" id="checked"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `false`       |

#### `disabled` <a href="#disabled" id="disabled"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `false`       |

#### `onChange` <a href="#onchange" id="onchange"></a>

| TYPE                                  | DEFAULT VALUE |
| ------------------------------------- | ------------- |
| `Function`: `(checked: Boolean) -> *` | `() => {}`    |
