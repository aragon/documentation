# Tag

A non-interactive component that can be used to display a small piece of information: general indicators, app / account identifiers, updates, or activity counters.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Main, Tag } from '@aragon/ui'

function App() {
  return (
    <Main>
      <Tag mode="new">New update</Tag>
    </Main>
  )
}
```

## Props <a href="#props" id="props"></a>

#### `mode` <a href="#mode" id="mode"></a>

| TYPE                                                   | DEFAULT VALUE |
| ------------------------------------------------------ | ------------- |
| `"indicator"`, `"identifier"`, `"new"` or `"activity"` | `"indicator"` |

Set of predefined color, background and size combinations (which can be overridden by the corresponding props).

#### `size` <a href="#size" id="size"></a>

| TYPE                    | DEFAULT VALUE               |
| ----------------------- | --------------------------- |
| `"normal"` or `"small"` | Depends of the current mode |

Defines size and padding for the rendered component.

#### `color` <a href="#color" id="color"></a>

| TYPE             | DEFAULT VALUE               |
| ---------------- | --------------------------- |
| `String` (color) | Depends of the current mode |

The text color.

#### `background` <a href="#background" id="background"></a>

| TYPE             | DEFAULT VALUE               |
| ---------------- | --------------------------- |
| `String` (color) | Depends of the current mode |

The background color.

#### `uppercase` <a href="#uppercase" id="uppercase"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `true`        |

Defines the text style uppercase transformation for the contents.

#### `limitDigits` <a href="#limitdigits" id="limitdigits"></a>

| TYPE                  | DEFAULT VALUE |
| --------------------- | ------------- |
| `Boolean` or `Number` | `false`       |

Use this to pass a number as the `label` prop of the Tag, and limit it to a certain number of digits. For example, `250` will be displayed as “99+” if the number of digits is `2`.

Set to `true` for the default number of digits (`2`), or set to the desired number.

#### `label` <a href="#label" id="label"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

The label of the Tag.

#### `icon` <a href="#icon" id="icon"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

The icon to be displayed in the label. It can be used alone or with `label`.

#### `children` <a href="#children" id="children"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

The child content (takes priority over `label` and `icon`).
