# Modal

The `Modal` component is used to render a structured container for modal windows.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Modal, Button } from '@aragon/ui'

const App = () => {
  const [opened, setOpened] = useState(false)

  const open = () => setOpened(true)
  const close = () => setOpened(false)

  return (
    <>
      <Button onClick={open}>Open modal</Button>
      <Modal visible={opened} onClose={close}>
        {/* modal content */}
      </Modal>
    </>
  )
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-26 alle 21.09.38.png>)

## Props <a href="#props" id="props"></a>

#### `visible` <a href="#visible" id="visible"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | Required      |

Use this property to show/hide the Modal.

#### `width` <a href="#width" id="width"></a>

| TYPE                             | DEFAULT VALUE                                    |
| -------------------------------- | ------------------------------------------------ |
| `Function`, `Number` or `String` | `viewport => Math.min(viewport.width - 48, 600)` |

Use this property to assign a dynamic width to the modal.

If a function is set, the data coming from Viewport will be passed to it.

If a number is set or returned from the function, `px` will automatically be added to it.

#### `padding` <a href="#padding" id="padding"></a>

| TYPE                             | DEFAULT VALUE |
| -------------------------------- | ------------- |
| `Function`, `Number` or `String` | `24`          |

The inner padding of the modal.

If a function is set, the data coming from Viewport will be passed to it.

If a number is set or returned from the function, `px` will automatically be added to it.

#### `onClose` <a href="#onclose" id="onclose"></a>

| TYPE       | DEFAULT VALUE |
| ---------- | ------------- |
| `Function` | None          |

This callback is called when the `ESC` key is pressed or the user clicks outside of the modal container.

#### `onClosed` <a href="#onclosed" id="onclosed"></a>

| TYPE       | DEFAULT VALUE |
| ---------- | ------------- |
| `Function` | None          |

This callback is called after the closing transition has completed and the content has been unmounted.

#### `closeButton` <a href="#closebutton" id="closebutton"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `true`        |

Whether or not to display a close button.
