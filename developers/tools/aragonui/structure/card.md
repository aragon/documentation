# Card

A Card component.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Main, Card } from '@aragon/ui'

function App() {
  return (
    <Main>
      <Card>Card content</Card>
    </Main>
  )
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.29.53.png>)

## Props <a href="#props" id="props"></a>

#### `width` <a href="#width" id="width"></a>

* Type: `String`
* Default: `282px`

Set the width of your card in pixels.

#### **Example:**

```jsx
const MyCard = () => (
  <Card width="500px">{/* Your card's content goes here */}</Card>
)
```

#### `height` <a href="#height" id="height"></a>

* Type: `String`
* Default: `322px`

Set the height of your card in pixels.

#### **Example:**

```jsx
const MyCard = () => (
  <Card height="800px">{/* Your card's content goes here */}</Card>
)
```
