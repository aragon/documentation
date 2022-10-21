# Info

An info component, which can be used to display normal messages, warnings or errors.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Info } from '@aragon/ui'

function MyApp = () => {
  return <Info title="Title">Some info</Info>
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-26 alle 21.00.56.png>)

## Props <a href="#props" id="props"></a>

#### `mode` <a href="#mode" id="mode"></a>

| TYPE                         | DEFAULT VALUE |
| ---------------------------- | ------------- |
| `"info", "warning", "error"` | `"info"`      |

Set the mode of the Info component. The styles can be individually overriden by `background`, `color`, `borderColor` and `titleColor`.

#### `title` <a href="#title" id="title"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `String` | None          |

Set a title for the info box.

**Example:**

```jsx
<Info title="My title">Some info</Info>
```

#### `background` <a href="#background" id="background"></a>

| TYPE  | DEFAULT VALUE |
| ----- | ------------- |
| Color | None          |

Set the background of the info box.

#### `color` <a href="#color" id="color"></a>

| TYPE  | DEFAULT VALUE |
| ----- | ------------- |
| Color | None          |

Set the text color.

#### `borderColor` <a href="#bordercolor" id="bordercolor"></a>

| TYPE  | DEFAULT VALUE |
| ----- | ------------- |
| Color | None          |

Set the border color of the info box.

#### `titleColor` <a href="#titlecolor" id="titlecolor"></a>

| TYPE  | DEFAULT VALUE |
| ----- | ------------- |
| Color | None          |

Set the title color.
