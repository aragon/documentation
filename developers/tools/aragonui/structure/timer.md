# Timer

Displays a countdown or stopwatch.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Timer } from '@aragon/ui'

const NOW = Date.now()
const DAY = 1000 * 60 * 60 * 24

const endDate = new Date(NOW + 5 * DAY)
const startDate = new Date(NOW - 5 * DAY)

const App = () => (
  <div>
    <Timer end={endDate} />
    <Timer start={startDate} />
  </div>
)
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.45.03.png>)

## Props <a href="#props" id="props"></a>

#### `end` <a href="#end" id="end"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Date` | None          |

The end of the countdown, as a `Date` instance.

#### `start` <a href="#start" id="start"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Date` | None          |

The start of a timer, as a `Date` instance.

#### `format` <a href="#format" id="format"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Enum` | `'dhms'`      |

* Options: `[ 'yMdhms', 'yMdhm', 'yMdh','yMd', 'yM', 'Mdhms', 'Mdhm', 'Mdh', 'Md', 'dhms', 'dhm', 'hms', 'hm', 'ms', 'm', 's' ]`

Format output in years 'y', months 'M', days 'd', hours 'h', minutes 'm', seconds 's'

#### `maxUnits` <a href="#maxunits" id="maxunits"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `-1`          |

Is the number of units to be displayed regardless of the `format`. By default, it’s set to -1 which will display all the available units. If it’s set to a number `n`, which can be from `1` to all the units used in the `format` prop, it will display only the first `n` units, left to right.

#### `showEmpty` <a href="#showempty" id="showempty"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `False`       |

Display the units on the left side of the timer when they are equal to zero.

#### `showIcon` <a href="#showicon" id="showicon"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `True`        |

Display the clock icon on the left side of the timer.
