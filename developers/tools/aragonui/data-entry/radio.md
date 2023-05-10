# Radio

A radio button component.

## Usage <a href="#usage" id="usage"></a>

```jsx
import React from 'react'
import { Radio } from '@aragon/ui'

class App extends React.Component {
  state = { checked: false }
  render() {
    return (
      <div>
        <label>
          <Radio
            id="strawberry"
            checked={this.state.checked}
            onChange={id => {
              console.log(
                `${singleChecked ? 'Unchecked' : 'Checked'} ${id}`
              )
              this.setState({ singleChecked: !singleChecked })
            }}
          />
          Click me
        </label>
      </div>
    )
  }
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 23.01.21.png>)

## Props <a href="#props" id="props"></a>

#### `checked` <a href="#checked" id="checked"></a>

* Type: `Boolean`
* Default: `false`

Whether it is checked or not.

#### `disabled` <a href="#disabled" id="disabled"></a>

* Type: `Boolean`
* Default: `false`

Set to `true` to disable the radio.

#### `id` <a href="#id" id="id"></a>

* Type: `String` or `Number`

When the `<Radio />` is nested in a `<RadioGroup />`, this value is passed to the `<RadioGroup />`'s `onChange` handler when the radio is checked.

If not, it is passed to the `onCheck` handler when the radio is checked.

#### `onChange` <a href="#onchange" id="onchange"></a>

* Type: `Function`: `(id: String|Number) -> *`

This callback is called whenever the user selects the radio.

#### **Arguments:**

* `id`: The value passed as the `id` prop.
