# Table

A table component.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Table, TableHeader, TableRow, TableCell, Text } from '@aragon/ui'

const App = () => (
  <Table
    header={
      <TableRow>
        <TableHeader title="Activity" />
      </TableRow>
    }
  >
    <TableRow>
      <TableCell>
        <Text>January</Text>
      </TableCell>
      <TableCell>
        <Text>February</Text>
      </TableCell>
    </TableRow>
    <TableRow>
      <TableCell>
        <Text>10 commits</Text>
      </TableCell>
      <TableCell>
        <Text>32 commits</Text>
      </TableCell>
    </TableRow>
  </Table>
)
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.37.36.png>)

## Props <a href="#props" id="props"></a>

#### `header` <a href="#header" id="header"></a>

* Type: `Node`

This is a table row containing a header of your choice.

#### **Example:**

```jsx
const MyTable = (props) => (
  <Table
    header={
      <TableRow>
        <TableHeader title="Records" />
      </TableRow>
    }
  >
    {/* Table content */}
  </Table>
)
```

#### `noSideBorders` <a href="#nosideborders" id="nosideborders"></a>

* Type: `Boolean`
* Default: `false`

Set this to `true` to remove the borders on the side of the table. Useful when the table need to take the full width of the screen.
