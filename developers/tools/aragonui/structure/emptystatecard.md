# EmptyStateCard

EmptyStateCard extends the Card component to represent an empty state in your app.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Main, Button, EmptyStateCard } from '@aragon/ui'

function App() {
  return (
    <EmptyStateCard
      text="There is no content."
      action={<Button>>Action</Button>}
    />
  )
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.38.55.png>)

## Props <a href="#props" id="props"></a>

#### text <a href="#text" id="text"></a>

| TYPE         | DEFAULT VALUE   |
| ------------ | --------------- |
| `React node` | None (required) |

Set some text content for your EmptyStateCard.

#### **Example:**

```jsx
<EmptyStateCard text="You seem to not have any content on your wall." />
```

#### `illustration` <a href="#illustration" id="illustration"></a>

| TYPE         | DEFAULT VALUE          |
| ------------ | ---------------------- |
| `React node` | A default illustration |

An illustration to visually represent the empty state.

#### **Example:**

```jsx
<EmptyStateCard illustration={<img src={illustrationSrc} alt="" />} />
```

#### `action` <a href="#action" id="action"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

The action, usually represented by a `Button`.

{% hint style="info" %}
Note: the Button will automatically set `mode` to `"strong"` and `wide` to `true` when used inside EmptyStateCard.
{% endhint %}

#### **Example:**

```jsx
const App = () => (
  <EmptyStateCard
    text="No votes yet."
    action={<Button label="Create a new vote" onClick={createVote} />}
  />
)
```
