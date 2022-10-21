# Button

A simple Button component, available in different modes.

Even though `children` can be used to set its content, it is generally preferred to use `label` and `icon`. It will make it possible for the `Button` to adapt in certain cases: for example, when used in the `Header` component, it will automatically switch between a label and an icon, depending on the viewport size (except if `display` is set to something else than `auto`).

## Usage <a href="#usage" id="usage"></a>

```jsx
function App() {
  return <Button label="Click me" />
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.13.30.png>)

## Props <a href="#props" id="props"></a>

#### `label` <a href="#label" id="label"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

The textual content of the button.

#### `icon` <a href="#icon" id="icon"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

The icon to incorporate in the button. When only an icon is desired, it is recommended to set a `label` with the `display` prop set to `"icon"`: the label will then be set on the `title` attribute of the element.

#### `display` <a href="#display" id="display"></a>

| TYPE                             | DEFAULT VALUE |
| -------------------------------- | ------------- |
| `auto`, `all`, `icon` or `label` | `auto`        |

Use this prop to force a specific display mode.

#### **Example:**

```jsx
<Button icon={<IconDownload />} label="Download" />
```

#### `children` <a href="#children" id="children"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

Having children on a `Button` will override `label`, `icon`, and `display`. It is generally not recommended but can be useful in some situtations.

#### `mode` <a href="#mode" id="mode"></a>

| TYPE                                       | DEFAULT VALUE |
| ------------------------------------------ | ------------- |
| `normal`, `strong`, `positive`, `negative` | `normal`      |

Set this property to the desired variant.

#### **Example:**

```jsx
<Button mode="strong">Accept</Button>
```

#### `size` <a href="#size" id="size"></a>

| TYPE                        | DEFAULT VALUE |
| --------------------------- | ------------- |
| `medium`, `small` or `mini` | `medium`      |

Use this property to change the size of the button.

#### **Example:**

```jsx
<Button size="small">Accept</Button>
```

#### `wide` <a href="#wide" id="wide"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `false`       |

Set to true to obtain a button that expands horizontally.

#### **Example:**

```jsx
<Button wide>Accept</Button>
```
