# ProgressBar

## Usage <a href="#usage" id="usage"></a>

```jsx
import { ProgressBar } from '@aragon/ui'

const App = () => (
  <ProgressBar value={0.3} />
)
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-26 alle 21.02.03.png>)

## Props <a href="#props" id="props"></a>

#### `color` <a href="#color" id="color"></a>

* Type: `String`
* Default: `accent` color from `theme`

To change the color of the active bar.

#### `value` <a href="#value" id="value"></a>

* Type: `Number`
* Values: from `0` to `1`, or `-1`.
* Default: `-1`

The value, between `0` and `1`. Set to `-1` for the indeterminate state.

#### `animate` <a href="#animate" id="animate"></a>

* Type: `Boolean`
* Default: `true`

Set this to `false` to disable the animations. Useful to improve the performances if the progress bar is not visible but rendered.
