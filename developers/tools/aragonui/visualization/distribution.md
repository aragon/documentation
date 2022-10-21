# Distribution

This component can be used to visualize the distribution of a given value. It is often used inside the `Box` component, but can be used elsewhere too.

## Usage <a href="#usage" id="usage"></a>

```jsx
<Box>
  <Distribution
    heading="Fruit shares"
    items={[
      { item: 'Bananas', percentage: 37 },
      { item: 'Apples', percentage: 22 },
      { item: 'Cherries', percentage: 15 },
      { item: 'Oranges', percentage: 12 },
      { item: 'Grapefruits', percentage: 12 },
      { item: 'Rest', percentage: 2 },
    ]}
  />
</Box>
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-26 alle 20.37.35.png>)

## Props <a href="#props" id="props"></a>

#### colors <a href="#colors" id="colors"></a>

| TYPE    | DEFAULT VALUE                |
| ------- | ---------------------------- |
| `Array` | Set of colors from the theme |

The different colors used to represent the items. If there are more items than colors, it will rotate.

#### showLegend <a href="#showlegend" id="showlegend"></a>

| TYPE      | DEFAULT VALUE |
| --------- | ------------- |
| `Boolean` | `true`        |

Set to `false` to display the bar only.

#### heading <a href="#heading" id="heading"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

An optional heading.

#### itemTitle({ item, percentage, index }) <a href="#itemtitle-7b-item-2c-percentage-2c-index-7d" id="itemtitle-7b-item-2c-percentage-2c-index-7d"></a>

| TYPE       | DEFAULT VALUE |
| ---------- | ------------- |
| `Function` | None          |

This function gets called to generate the title attribute for each item.

#### renderLegendItem({ color, index, item, percentage }) <a href="#renderlegenditem-7b-color-2c-index-2c-item-2c-percentage-7d" id="renderlegenditem-7b-color-2c-index-2c-item-2c-percentage-7d"></a>

| TYPE       | DEFAULT VALUE |
| ---------- | ------------- |
| `Function` | None          |

This function gets called to render individual items in the legend. You can also pass a React component.

#### renderFullLegendItem({ bullet, color, index, item, percentage }) <a href="#renderfulllegenditem-7b-bullet-2c-color-2c-index-2c-item-2c-percentage-7d" id="renderfulllegenditem-7b-bullet-2c-color-2c-index-2c-item-2c-percentage-7d"></a>

| TYPE       | DEFAULT VALUE |
| ---------- | ------------- |
| `Function` | None          |

This function gets called to render the full line of individual items in the legend. You can also pass a React component.

#### items <a href="#items" id="items"></a>

| TYPE    | DEFAULT VALUE   |
| ------- | --------------- |
| `Array` | None (required) |

The items represented in the distribution. Every item in the array must be an object composed of two entries: `item`, which can be any type of value, and `percentage`, which has to be a `Number`.

Note: the total of the percentages for all the items doesn’t have to be `100`. The bar will get displayed properly with any total, which can be useful in certain cases.
