# TextInput

A basic text input component that can be used in single or multi-line modes.

## Usage <a href="#usage" id="usage"></a>

```jsx
function App() {
  const [value, setValue] = useState('')
  return (
    <TextInput
      value={value}
      onChange={event => {
        setValue(event.target.value)
      }}
    />
  )
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 23.05.24.png>)

## Props <a href="#props" id="props"></a>

#### `adornment` <a href="#adornment" id="adornment"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | `null`        |

Allows to add an icon or any other component inside of a `TextInput`.

#### `adornmentPosition` <a href="#adornmentposition" id="adornmentposition"></a>

| TYPE                 | DEFAULT VALUE |
| -------------------- | ------------- |
| `"start"` or `"end"` | `"start"`     |

Set this to change the position of the adornment. `'start'` is displayed on the left, and `'end'` on the right. Note: in the future, the position will be reversed in right-to-left languages.

#### `adornmentSettings.width` <a href="#adornmentsettings.width" id="adornmentsettings.width"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `36`          |

The total width of the adornment.

#### `adornmentSettings.padding` <a href="#adornmentsettings.padding" id="adornmentsettings.padding"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `4`           |

The horizontal padding of the adornment.

#### `autofocus` <a href="#autofocus" id="autofocus"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `false`       |

Focus the text field when the component gets mounted.

#### `onChange` <a href="#onchange" id="onchange"></a>

| TYPE       | DEFAULT VALUE |
| ---------- | ------------- |
| `Function` | None          |

The native `change` event. Gets passed to either the `input` element, or `textarea` element if `multiline` is true.

#### `type` <a href="#type" id="type"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `String` | `"text"`      |

Any valid `<input>` type. See [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Form\_%3Cinput%3E\_types).

This prop is ignored if `multiline` is `true`.

#### `multiline` <a href="#multiline" id="multiline"></a>

* Type: `Boolean`
* Default: `false`

Set to true to use multiple lines. Internally uses a `textarea` HTML element.

#### `wide` <a href="#wide" id="wide"></a>

* Type: `Boolean`
* Default: `false`

Set to true to obtain an input that expands horizontally.
