# RadioGroup

A single-selection group of radios.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Component } from 'react'
import { Radio, RadioGroup } from '@aragon/ui'

const RADIO_LABELS = ['First', 'Second', 'Third']

class App extends Component {
  state = {
    activeId: 'first',
  }
  handleChange = activeId => {
    this.setState({ activeId })
  }
  render() {
    const { activeId } = this.state
    return (
      <RadioGroup onChange={this.handleChange} selected={activeId}>
        {RADIO_LABELS.map((label, i) => {
          const radioId = label.toLowerCase()
          return (
            <label key={i}>
              <Radio id={radioId} />
              {label}
            </label>
          )
        })}
      </RadioGroup>
    )
  }
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 23.09.29.png>)

## Props <a href="#props" id="props"></a>

#### `className` <a href="#classname" id="classname"></a>

* Type: `String`

Sets the class name of the `radiogroup` container.

#### `selected` <a href="#selected" id="selected"></a>

* Type: `Function`: `(id: String|Number) -> *`

Id of selected radio, if any.

#### `onChange` <a href="#onchange" id="onchange"></a>

* Type: `Function`: `(id: String|Number) -> *`

This callback is called whenever the user selects a nested `<Radio />`.

#### **Arguments:**

* `id`: The value passed as the `<Radio />`'s `id` prop.

#### `children` <a href="#children" id="children"></a>

An arbitrary component tree that should eventually render at least one or more `<Radio />`s.
