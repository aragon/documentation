# Main

Provides the base needed by the other components (styles and context providers) to work properly.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Main } from '@aragon/ui'

function App () {
  return (
    <Main>
      {/* Your app goes here */}
    </Main>
  )
}
```

## Props <a href="#props" id="props"></a>

#### `assetsUrl` <a href="#assetsurl" id="assetsurl"></a>

| TYPE     | DEFAULT VALUE  |
| -------- | -------------- |
| `String` | `./aragon-ui/` |

Set this to configure the URL of the directory containing your aragonUI assets.

#### `layout` <a href="#layout" id="layout"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `true`        |

Enable `<Layout />`.

#### `scrollView` <a href="#scrollview" id="scrollview"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `true`        |

Enable `<ScrollView />`.

#### `theme` <a href="#theme" id="theme"></a>

| TYPE                 | DEFAULT VALUE |
| -------------------- | ------------- |
| `String` or `Object` | `light`       |

The main theme used by aragonUI.
