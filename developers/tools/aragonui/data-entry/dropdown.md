# DropDown

A DropDown component.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { DropDown } from '@aragon/ui'

function App() {
  const [selected, setSelected] = useState(0)
  return (
    <DropDown
      items={['Wandering Thunder', 'Black Wildflower', 'Ancient Paper']}
      selected={selected}
      onChange={setSelected}
    />
  )
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.57.00.png>)

## Props <a href="#props" id="props"></a>

#### `header` <a href="#header" id="header"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

A header that will appear at the beginning of the items menu.

#### `items` <a href="#items" id="items"></a>

| TYPE    | DEFAULT VALUE   |
| ------- | --------------- |
| `Array` | None (required) |

Use this property to define the items of the DropDown menu.

#### placeholder <a href="#placeholder" id="placeholder"></a>

| TYPE         | DEFAULT VALUE      |
| ------------ | ------------------ |
| `React node` | `"Select an item"` |

The node displayed in the button when there is no selection.

#### renderLabel <a href="#renderlabel" id="renderlabel"></a>

| TYPE              | DEFAULT VALUE                          |
| ----------------- | -------------------------------------- |
| `React component` | `({ selectedLabel }) => selectedLabel` |

A function (or React component), used to display the button label.

#### **Props**

* `selectedLabel` (`String`): label of the selected item.
* `selectedIndex` (`Number`): index of the selected item.

#### onChange(index, items) <a href="#onchange-index-2c-items" id="onchange-index-2c-items"></a>

| TYPE       | DEFAULT VALUE   |
| ---------- | --------------- |
| `Function` | None (required) |

This callback is called whenever the user selects a new item.

#### **Arguments**

* `index` (`Number`): Index of the newly selected item in `props.items`.
* `items` (`Array`): the items passed in `props.items`.

#### selected <a href="#selected" id="selected"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `-1`          |

Set this prop to the index of the active item. Set to `-1` to unselect and display the placeholder.

#### wide <a href="#wide" id="wide"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `false`       |

Takes the full width if set to `true`.

#### width <a href="#width" id="width"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `String` | None          |

Use this prop to set the CSS width of the button.

#### disabled <a href="#disabled" id="disabled"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `false`       |

Disable the DropDown.
