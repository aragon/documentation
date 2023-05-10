# TextCopy

A read-only text input component that allows the user to copy the value to the clipboard.

Extra props will be passed to the `TextInput` component which is used internally.

## Usage <a href="#usage" id="usage"></a>

```jsx
<TextCopy value="Something to copy" />
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 23.13.34.png>)

## Props <a href="#props" id="props"></a>

#### `adornment` <a href="#adornment" id="adornment"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

Allows to set an adornment that will get used on the left side of the text field (in left to right languages). The copy button is always displayed on the other side.

#### `autofocus` <a href="#autofocus" id="autofocus"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `false`       |

Focus the text field when the component gets mounted.

#### `message` <a href="#message" id="message"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `String` | `"Copied"`    |

The message that gets displayed when the copy is successful.

#### `monospace` <a href="#monospace" id="monospace"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `true`        |

Set this to false to disable the use of the monospace font (e.g. for Ethereum addresses).

#### `onCopy` <a href="#oncopy" id="oncopy"></a>

| TYPE                 | DEFAULT VALUE |
| -------------------- | ------------- |
| `Function` or `null` | None          |

When not set, a toast will get displayed on copy, with the `message` provided.

When set to `null`, disables the message entirely.

When set to a function, calls this function when the copy is successful, with the `message` as a parameter.

#### `value` <a href="#value" id="value"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `String` | None          |

The field content (single line).
