# SearchInput

A text input component with a set adornment that changes into a button when text is introduced in the input and when clicked on clears the input.

## Usage <a href="#usage" id="usage"></a>

```jsx
function App() {
  const [value, setValue] = useState('')
  return <SearchInput value={value} onChange={setValue} />
}
```

## Props <a href="#props" id="props"></a>

> Additional props will get passed to the internal `TextInput` component.

#### `onChange` <a href="#onchange" id="onchange"></a>

| TYPE       | DEFAULT VALUE |
| ---------- | ------------- |
| `Function` | None          |

The input box value and the two native `change` or `click` events.
