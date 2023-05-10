# Link

A textual interactive element that can be used as an anchor (`<a>`) or as a button.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Link } from '@aragon/ui'

function App() {
  return <Link href="https://example.com/">Example</Link>
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.24.57.png>)

## Props <a href="#props" id="props"></a>

#### onClick <a href="#onclick" id="onclick"></a>

| TYPE       | DEFAULT VALUE |
| ---------- | ------------- |
| `Function` | None          |

Gets called when the user activates the link. Like for `Button`, it gets called when the enter key is pressed on the keyboard.

#### href <a href="#href" id="href"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `String` | None          |

When set, the component will act like a normal HTML anchor.

#### external <a href="#external" id="external"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `false`       |

Set to `true` to make the link external, which will add an underline. If a `href` is present, it will also add a `target="_blank"` attribute and [make it safe](https://mathiasbynens.github.io/rel-noopener/) by default.

#### Other props <a href="#other-props" id="other-props"></a>

Any other prop will be passed to the `ButtonBase` component.
