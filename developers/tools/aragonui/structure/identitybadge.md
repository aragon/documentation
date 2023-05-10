# IdentityBadge

A component to get the Ethereum Identicon, an image that identifies Ethereum Accounts.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { IdentityBadge } from '@aragon/ui'

function App() {
  return (
    <IdentityBadge
      customLabel="Custom Label User"
      entity="0xc41e4c10b37d3397a99d4a90e7d85508a69a5c4c"
      connectedAccount
    />
  )
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.40.36.png>)

## Props <a href="#props" id="props"></a>

#### `badgeOnly` <a href="#badgeonly" id="badgeonly"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Bool` | `false`       |

Disables the badge as a button and avoids prompting the popover on click.

#### `compact` <a href="#compact" id="compact"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Bool` | `false`       |

Smaller version of the IdentityBadge. Should be used when the IdentityBadge is placed inline with text.

#### `connectedAccount` <a href="#connectedaccount" id="connectedaccount"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Bool` | `false`       |

If the given, assumes `entity` is the same as the connected account and renders "you" in the popover.

#### `entity` <a href="#entity" id="entity"></a>

| TYPE     | DEFAULT VALUE       |
| -------- | ------------------- |
| `String` | `""` (Empty string) |

The Ethereum entity. If the given string is a valid Ethereum address (also based on the checksum, if provided (more info)\[https://web3js.readthedocs.io/en/1.0/web3-utils.html#isaddress]), an Identicon will be automatically displayed.

#### `label` <a href="#label" id="label"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `String` | None          |

A label for the `entity`. If available, `label` is displayed instead of the `entity` on the badge.

#### `labelStyle` <a href="#labelstyle" id="labelstyle"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `String` | None          |

Styles to apply to the `label`.

#### `networkType` <a href="#networktype" id="networktype"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `String` | `main`        |

Checks the type of network to get an Etherscan URL from the `entity`.

#### `popoverTitle` <a href="#popovertitle" id="popovertitle"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Node` | `main`        |

The title of the popover. You can pass anything that can be rendered, such as a num, string, DOM element, an array of them, or React fragments that contain them.

#### `popoverAction` <a href="#popoveraction" id="popoveraction"></a>

| TYPE                     | DEFAULT VALUE |
| ------------------------ | ------------- |
| `BadgePopoverActionType` | None          |

The action of the popover

**popoverAction.label**

The node rendered in the popover's action button.

**popoverAction.onClick**

The onclick handler for the popover's action button.

#### `shorten` <a href="#shorten" id="shorten"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Bool` | `true`        |

If true and `entity` is a valid address, reduces `entity` to only the first and last four characters (excluding the "0x" prefix) for display. i.e: address="0xcafe…5f2C"
