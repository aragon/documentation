# DateRangePicker

A component for selecting a date range.

## Usage <a href="#usage" id="usage"></a>

```jsx
import React, { useState } from 'react'
import { DateRangePicker } from '@aragon/ui'

const DateRange = () => {
  const [range, setRange] = useState({
    start: null,
    end: null,
  })
  return (
    <DateRangePicker
      startDate={range.start}
      endDate={range.end}
      onChange={setRange}
    />
  )
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.54.46.png>)

## Props <a href="#props" id="props"></a>

#### `format` <a href="#format" id="format"></a>

* Type: `String`
* Default: `'MM/DD/YYYY'`

Format for the displayed dates.

#### `onChange` <a href="#onchange" id="onchange"></a>

* Type: `Function`: `({start, end}: {start: Date, end: Date}) -> *`
* Default: `() => {}`

This callback is called whenever the user selects clicks "Apply" after selecting a date.

#### `startDate` <a href="#startdate" id="startdate"></a>

* Type: `Date`
* Default: none

Selected start date.

#### `endDate` <a href="#enddate" id="enddate"></a>

* Type: `Date`
* Default: none

Selected end date.
