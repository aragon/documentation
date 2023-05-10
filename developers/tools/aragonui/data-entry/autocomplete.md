# AutoComplete

This component offers an list of options for an input box. You'll need to bring your own search functionality. Out of the box it can be used to render text items, but if needed these can be updated to a custom render.

Another component `AutoCompleteSelected` offers the extra functionality to select one of the items from the list and display it (custom render). When using this component consider the behaviour of AutoComplete as fully controlled, so you'll need to pass the value prop too.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { useState } from 'react'
import { _AutoComplete as AutoComplete } from '@aragon/ui'

const items = [
  'Bruce Wayne',
  'Bruce Banner',
  'Bruce Springsteen',
  'Bruce Lee',
  'Bruce Willis',
]

const FilterBasedOnWhatIsTyped = () => {
  const [searchTerm, setSearchTerm] = useState(null)
  const ref = useRef()

  return (
    <AutoComplete
      items={items.filter(
        name =>
          searchTerm &&
          name.toLowerCase().indexOf(searchTerm.toLowerCase()) > -1
      )}
      onChange={setSearchTerm}
      onSelect={value => {
        textRef.current.value = value
        setSearchTerm(null)
      }}
      ref={ref}
      placeholder="Hint: Bruce"
    />
  )
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.52.27.png>)

## Props <a href="#props" id="props"></a>

#### `items` <a href="#items" id="items"></a>

* Type: `Array`
* Default: `[]`

Use this property to define the items of the list. Objects can be used but that means you’ll have to pass down your own item renderer.

Note: remember to limit the number of `items` to an acceptable number, like 10 items.

#### `renderItem` <a href="#renderitem" id="renderitem"></a>

* Type: `Component`
* Default: Functional component for identity `x => x`

Use this property to define a custom renderer for the items on the list.

#### `itemButtonStyles` <a href="#itembuttonstyles" id="itembuttonstyles"></a>

* Type: `string`

Item elements get wrapped in button components, use this property to set css rules for the wrapping button.

#### `onSelect` <a href="#onselect" id="onselect"></a>

* Type: `Function`

Use this property to handle the users selection (via `click` or `enter`) of an item from the list

#### `onChange` <a href="#onchange" id="onchange"></a>

* Type: `Function`

Use this property to handle changes to the underlying input element.

#### `placeholder` <a href="#placeholder" id="placeholder"></a>

* Type: `string`

Use this property to set the `placeholder` property on the underlying input element.

#### `required` <a href="#required" id="required"></a>

* Type: `Boolean`
* Default: `false`

Use this property to set the `required` property on the underlying input element.

#### `value` <a href="#value" id="value"></a>

* Type: `string`

Use this property to set the `value` property on the underlying input element.

#### `wide` <a href="#wide" id="wide"></a>

* Type: `Boolean`
* Default: `false`

Use this property to set the `wide` property on the underlying `Text` component.

### AutoCompleteSelected properties <a href="#autocompleteselected-properties" id="autocompleteselected-properties"></a>

#### `selected` <a href="#selected" id="selected"></a>

* Type: `Object`

Use this property to set the `selected` item which will be rendered. When setting this property also provide the `value` property which to correctly manage this component as controlled.

#### `renderSelected` <a href="#renderselected" id="renderselected"></a>

* Type: `Component`
* Default: Functional component for identity `x => x`

Use this property to define a custom renderer for the selected item when an item has been selected.

#### `selectedButtonStyles` <a href="#selectedbuttonstyles" id="selectedbuttonstyles"></a>

* Type: `string`

The selected item gets wrapped in a button component, use this property to set css rules for the wrapping button.

#### `onSelectedClick` <a href="#onselectedclick" id="onselectedclick"></a>

* Type: `Function`

Use this property to handle the user interacting with the selected item wrapping button.
