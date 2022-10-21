# Popover

## Usage <a href="#usage" id="usage"></a>

A simple Popover component with basic styles. It gets rendered at the root level so it can be declared wherever you like.

#### Positioning relative to the "opener" <a href="#positioning-relative-to-the-22opener-22" id="positioning-relative-to-the-22opener-22"></a>

```jsx
import { Popover } from '@aragon/ui'

function App() {
  const [visible, setVisible] = useState(false)
  const opener = React.createRef()

  return (
    <div>
      <Button onClick={() => setVisible(true)} ref={opener}>
        Show
      </Button>
      <Popover
        visible={visible}
        opener={opener.current}
        onClose={() => setVisible(false)}
      >
        Popover
      </Popover>
    </div>
  )
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-26 alle 21.08.21.png>)

## Props <a href="#props" id="props"></a>

#### `opener` <a href="#opener" id="opener"></a>

| TYPE          | DEFAULT VALUE |
| ------------- | ------------- |
| `DOM Element` | null          |

Reference to the "opener"which is what the Popover is positioning relative to.

#### `closeOnOpenerFocus` <a href="#closeonopenerfocus" id="closeonopenerfocus"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `false`       |

While the Popover is opened, do not immediately close the Popover when the opener gets focused. This makes it possible to toggle its visibility from the opener, if its placement allows it.

#### `placement` <a href="#placement" id="placement"></a>

* Type: `String`
* Values: `top`, `bottom`, `left`and `right` which can be concatenated with `-start` and `-end` e.g. `top-start`

Placement of the Popover relative to the "opener". Checkout [Popper.js](https://popper.js.org/index.html) for placement visuals.

#### `zIndex` <a href="#zindex" id="zindex"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | 999           |

zIndex of Popover.

#### `onClose` <a href="#onclose" id="onclose"></a>

| TYPE       | DEFAULT VALUE |
| ---------- | ------------- |
| `Function` | None          |

The callback that is called when the popover request to be closed. If this callback returns `false`, the popover will get focused again. This is useful to ensure that the `blur` event still gets triggered after a close request got rejected.

#### `visible` <a href="#visible" id="visible"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `true`        |

Whether or not the Popover is visible.

#### `scaleEffect` <a href="#scaleeffect" id="scaleeffect"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `true`        |

Set to `false` to disable the scaling effect when the popover appears and disappears.
