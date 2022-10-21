# Slider

A slider component.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Component } from 'react'
import { Slider } from '@aragon/ui'

class App extends Component {
  state = {
    progress: 0,
  }
  render() {
    const { progress } = this.state
    return (
      <Slider
        value={progress}
        onUpdate={(value) => this.setState({ progress: value })}
      />
    )
  }
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 23.04.07.png>)

## Props <a href="#props" id="props"></a>

#### `value` <a href="#value" id="value"></a>

* Type: `Number`
* Default: `0`

#### `onUpdate` <a href="#onupdate" id="onupdate"></a>

* Type: `Function: (value: Number) -> *`
