# Toast

The ToastHub component is used to display text message toasts.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { ToastHub, Toast, Button } from '@aragon/ui'

const App = () => (
  <ToastHub>
    <Toast>
      {toast => (
        <Button onClick={() => toast("hello world")</Button>}>Click me</Button>
      )}
    </Toast>
  </ToastHub>
)
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-26 alle 21.03.38.png>)

## Props <a href="#props" id="props"></a>

#### `timeout` <a href="#timeout" id="timeout"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `4000`        |

Set this property to change how long toasts will stick around.

#### `showIndicator` <a href="#showindicator" id="showindicator"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `false`       |

Set this property to `true` to add a small timout-indicator to toast messages.

#### `threshold` <a href="#threshold" id="threshold"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `Infinity`    |

Set this property to change the threshold of toasts being presented at the same time. This will be used as an aproximation or a guideline, but it will still allow bursts to at least show.

#### `position` <a href="#position" id="position"></a>

| TYPE                              | DEFAULT VALUE |
| --------------------------------- | ------------- |
| `"left"`, `"center"` or `"right"` | `"end"`       |

Set this property to change the position where toasts will appear.

#### `top` <a href="#top" id="top"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `false`       |

Set this property to `true` to make toasts appear from the top.

#### `shift` <a href="#shift" id="shift"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `0`           |

Use this property to shift the position of the toast from its “end position” (right on left to right languages).

## Compound components <a href="#compound-components" id="compound-components"></a>

#### `Toast` <a href="#toast" id="toast"></a>

The Toast component calls its render-child and passes a single function that allows you to create pop-up messages.
