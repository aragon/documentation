# LineChart

A component to draw line charts.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { LineChart } from '@aragon/ui'

function App() {
  return (
    <LineChart
      lines={[values]}
      springConfig={{ mass: 1, tension: 120, friction: 80 }}
      label={index => labels[index]}
      height={90}
      color={() => `#21aae7`}
    />
  )
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-26 alle 20.36.20.png>)

## Props <a href="#props" id="props"></a>

#### `springConfig` <a href="#springconfig" id="springconfig"></a>

This prop will define the motion of the chart.

| TYPE     | DEFAULT VALUE  |
| -------- | -------------- |
| `Spring` | `springs.lazy` |

`spring Presets`

There are presets to use for springConfig with different combinations of mass, tension and friction. More information can be found [here](https://www.react-spring.io/docs/hooks/api). See the following example to see how to use them.

* Presets: `springs.lazy`, `springs.smooth`, `springs.swift`, `springs.instant`

#### **Example:**

```jsx
import { LineChart, springs } from '@aragon/ui'

function App() {
  return <LineChart values={[0.2, 0.3, 0.2]} springConfig={spring.slow} />
}
```

#### `total` <a href="#total" id="total"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `-1`          |

The expected total (x axis of the chart). When not provided, the length of `values` is used instead.

#### `width` <a href="#width" id="width"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | None          |

The width of the chart. When not set, the SVG takes the width of its parent.

#### `height` <a href="#height" id="height"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | 200           |

* Type: `Number`
* Default: `200`

The height of the chart.

#### `dotRadius` <a href="#dotradius" id="dotradius"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `7 / 2`       |

The radius of every dot in the chart.

#### `animDelay` <a href="#animdelay" id="animdelay"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `500`         |

The delay before displaying the chart the first time it gets rendered.

#### `borderColor` <a href="#bordercolor" id="bordercolor"></a>

| TYPE     | DEFAULT VALUE              |
| -------- | -------------------------- |
| `String` | `rgba(209, 209, 209, 0.5)` |

The border color.

#### `labelColor` <a href="#labelcolor" id="labelcolor"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `String` | `#6d777b`     |

The label color.

#### `reset` <a href="#reset" id="reset"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `false`       |

Can be used to restart the transition. Set to `true`, then to `false` again.

#### `lines` <a href="#lines" id="lines"></a>

Pass the values that will be used to draw the lines. The color atribute in Subtypes overrides the `color` prop.

| TYPE                | SUBTYPES                                                                                                                                                                                          | DEFAULT VALUE |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- |
| `Array of Subtypes` | <p><code>id(Number)</code>,<br><code>values(Array of Numbers from 0 to 1 - Required)</code>,<br><code>color(String)</code> or<br><code>values(Array of Numbers from 0 to 1 - Required)</code></p> | `[]`          |

#### `label` <a href="#label" id="label"></a>

| TYPE                 |
| -------------------- |
| `Function` or `null` |

Example:

```jsx
<LineChart label={index => ((index % 26) + 10).toString(36)} />
```

This function gets called to render a label on the x axis.

#### `color` <a href="#color" id="color"></a>

| TYPE       |
| ---------- |
| `Function` |

#### Example:

```jsx
<LineChart
  color={(index, { lines }) => {
    return `hsl(${(index * (360 / lines.length) + 40) % 360}, 60%, 70%)`
  }}
/>
```

This function gets called to render the color of a line.
