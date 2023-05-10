# Field

A wrapper component for form fields.

## Usage <a href="#usage" id="usage"></a>

```jsx
import { Field } from '@aragon/ui'

const App = () => (
  <Field label="Enter name here:">
    <input />
  </Field>
)
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 23.14.59.png>)

## Props <a href="#props" id="props"></a>

#### `label` <a href="#label" id="label"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `String` | None          |

Set a label for your Field.

#### **Example:**

```jsx
const App = () => <Field label="Billing Address">{/* Field Input(s) */}</Field>
```

#### `required` <a href="#required" id="required"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | None          |

Marks the field as a required field. If not provided, `Field` will attempt to detect if the field is required by checking if any of its children contain a truthy `required` prop.

#### `children` <a href="#children" id="children"></a>

| TYPE                       | DEFAULT VALUE |
| -------------------------- | ------------- |
| `React node` or `Function` | None          |

The field content, usually a form element like `TextInput`.

When a function is passed, it will take an object as parameter containing an `id` key, whose value is set to a unique id that can be passed to the desired form element.

#### Example:

```jsx
<Field label="Phone number">
  {({ id }) => (
    <p>
      <TextInput placeholder="Prefix" value="+44" />
      <TextInput placeholder="Number" value="" id={id} />
    </p>
  )}
</Field>
```
