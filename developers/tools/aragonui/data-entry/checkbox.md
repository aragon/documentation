# CheckBox

A checkbox component.

## Usage <a href="#usage" id="usage"></a>

```jsx
import React from 'react'
import { Checkbox } from '@aragon/ui'

class App extends React.Component {
  state = { checked: false }
  render() {
    return (
      <div>
        <label>
          <Checkbox
            checked={this.state.checked}
            onChange={checked => this.setState({ checked })}
          />
          Click me
        </label>
      </div>
    )
  }
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 23.02.58.png>)

## Props <a href="#props" id="props"></a>

#### `checked` <a href="#checked" id="checked"></a>

* Type: `Boolean`
* Default: `false`

Set to `true` to check the checkbox.

#### `disabled` <a href="#disabled" id="disabled"></a>

* Type: `Boolean`
* Default: `false`

Set to `true` to disable the checkbox.

#### `indeterminate` <a href="#indeterminate" id="indeterminate"></a>

* Type: `Boolean`
* Default: `false`

Set to `true` to set the checkbox to an indeterminate state (between checked and unchecked), represented by a dash.

Following the way it behave on the web platform, if set to `true`, `checked` is ignored. When clicked, `onChange` is called with `false`.

#### `onChange` <a href="#onchange" id="onchange"></a>

* Type: `Function`: `(checked: Boolean) -> *`
* Default: `undefined`

This callback is called whenever the user selects the checkbox, using a pointer device or the keyboard.

#### **Arguments:**

* `checked`: The requested state for the check prop.
