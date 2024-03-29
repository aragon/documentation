# DataView

DataView is a component that can adapt to several different ways of representing and selecting data, switching from a table layout to a list layout depending on the available space.

## Usage <a href="#usage" id="usage"></a>

```jsx
<DataView
  fields={['Account', 'Amount']}
  entries={[
    { account: addr(), amount: '-7.900,33 ANT' },
    { account: addr(), amount: '-8.760,90 ANT' },
    { account: addr(), amount: '+5.321 ANT' },
  ]}
  renderEntry={({ account, amount }) => {
    return [<IdentityBadge entity={account} />, <Amount>{amount}</Amount>]
  }}
/>
```

## Props <a href="#props" id="props"></a>

#### fields <a href="#fields" id="fields"></a>

| TYPE    | DEFAULT VALUE   |
| ------- | --------------- |
| `Array` | None (required) |

The different fields of data, displayed in the column headers in table mode.

```jsx
<DataView fields={['Account', 'Amount']} />
```

An object form exists, allowing to set additional settings:

```jsx
<DataView
  fields={[
    // `priority` allows to change the fields
    // order when DataView is in list mode.
    { label: 'Account', priority: 1 },
    { label: 'Amount', priority: 2 },
  ]}
/>
```

#### **field.label**

The content displayed for the field.

#### **field.priority**

List mode only. Set this to any number to set the field priority.

#### **field.align**

Table mode only. Forces the table header to be aligned on a specific side: `end` or `start`.

#### **field.childStart**

Table mode only. Set this to `true` on the field you want the expansion rows to be aligned. See `renderEntryExpansion()` for more details.

#### entries <a href="#entries" id="entries"></a>

| TYPE    | DEFAULT VALUE   |
| ------- | --------------- |
| `Array` | None (required) |

The actual data entries. An array of any kind of data structure. Every value set in this array will be passed to `renderEntry`.

{% hint style="warning" %}
Important: `entries` should always be cached, for example by using `useMemo()`, rather than being passed inline. That way, `DataView` will know that your entries haven’t changed, and won’t do unnecessary renders or reset the pagination state.
{% endhint %}

Example with an array of objects:

```jsx
<DataView
  fields={['Account', 'Amount']}
  entries={[
    { account: addr(), amount: '-7.900,33 ANT' },
    { account: addr(), amount: '-8.760,90 ANT' },
    { account: addr(), amount: '+5.321 ANT' },
  ]}
  renderEntry={({ account, amount }) => {
    return [<IdentityBadge entity={account} />, <Amount>{amount}</Amount>]
  }}
/>
```

An array of arrays:

```jsx
<DataView
  fields={['Account', 'Amount']}
  entries={[
    [addr(), '-7.900,33 ANT'],
    [addr(), '-8.760,90 ANT'],
    [addr(), '+5.321 ANT'],
  ]}
  renderEntry={([account, amount]) => {
    return [<IdentityBadge entity={account} />, <Amount>{amount}</Amount>]
  }}
/>
```

Or anything else, like a string:

```jsx
<DataView
  fields={['Account', 'Amount']}
  entries={[
    `${addr()} | -7.900,33 ANT`,
    `${addr()} | -8.760,90 ANT`,
    `${addr()} | +5.321 ANT`,
  ]}
  renderEntry={entry => {
    const [account, amount] = entry.split(' | ')
    return [<IdentityBadge entity={account} />, <Amount>{amount}</Amount>]
  }}
/>
```

#### heading <a href="#heading" id="heading"></a>

| TYPE         | DEFAULT VALUE |
| ------------ | ------------- |
| `React node` | None          |

Set this to add a header inside the `DataView` surface.

#### mode <a href="#mode" id="mode"></a>

| TYPE                              | DEFAULT VALUE |
| --------------------------------- | ------------- |
| `"adaptive"`, `"table"`, `"list"` | `"adaptive"`  |

Set this to force the display mode of DataView.

#### page <a href="#page" id="page"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | None          |

Index of the current page. When not provided, `DataView` will manage the pagination itself.

#### onPageChange <a href="#onpagechange" id="onpagechange"></a>

| TYPE       | DEFAULT VALUE |
| ---------- | ------------- |
| `Function` | None          |

Gets called when a page change is requested. Use with `page` to manage the pagination in a [controlled](https://reactjs.org/docs/forms.html#controlled-components) way.

#### entriesPerPage <a href="#entriesperpage" id="entriesperpage"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `Number` | `10`          |

Number of items per page. Set to `-1` to display the items without pagination.

#### selection <a href="#selection" id="selection"></a>

| TYPE    | DEFAULT VALUE |
| ------- | ------------- |
| `Array` | None          |

A list of selected items, using their indexes. When not provided, `DataView` will manage the selection itself. See also `onSelectEntries()`.

#### onSelectEntries(entries, indexes) <a href="#onselectentries-entries-2c-indexes" id="onselectentries-entries-2c-indexes"></a>

| TYPE       | DEFAULT VALUE |
| ---------- | ------------- |
| `Function` | None          |

Gets called when the entries selection changes. If not set, the checkboxes won’t be displayed. Use with `selection` to manage the selection in a [controlled](https://reactjs.org/docs/forms.html#controlled-components) way.

Note: only one of `onSelectEntries` and `renderEntryExpansion` can be set at a time.

#### renderEntry(entry, index, { selected, mode }) <a href="#renderentry-entry-2c-index-2c-7b-selected-2c-mode-7d" id="renderentry-entry-2c-index-2c-7b-selected-2c-mode-7d"></a>

| TYPE       | DEFAULT VALUE   |
| ---------- | --------------- |
| `Function` | None (required) |

Renders an entry by returning an array of nodes with items corresponding to every field.

#### **Note: hooks in render props**

Hooks won’t work in one of the `render` prefixed methods. The reason is that these are not components, but functions called conditionally from `DataView`.

This is not possible:

```jsx
<DataView
  fields={['Account', 'Amount']}
  entries={[
    [addr(), '-7.900,33 ANT'],
    [addr(), '-8.760,90 ANT'],
    [addr(), '+5.321 ANT'],
    [addr(), '-328,65 ANT'],
    [addr(), '+3.321 ANT'],
    [addr(), '-328,65 ANT'],
  ]}
  renderEntry={({ account, amount }) => {
    const { accountConnected } = useAragonApi()
    return [
      <div>
        <IdentityBadge entity={account} />
        {accountConnected === account && <span>You</span>}
      </div>,
      <Amount>{amount}</Amount>,
    ]
  }}
/>
```

But hooks can be used in components, so we can create one:

```jsx
function Account({ address }) {
  const { accountConnected } = useAragonApi()
  return (
    <div>
      <IdentityBadge entity={address} />
      {accountConnected === address && <span>You</span>}
    </div>
  )
}

function App() {
  return (
    <DataView
      fields={['Account', 'Amount']}
      entries={[
        [addr(), '-7.900,33 ANT'],
        [addr(), '-8.760,90 ANT'],
        [addr(), '+5.321 ANT'],
        [addr(), '-328,65 ANT'],
        [addr(), '+3.321 ANT'],
        [addr(), '-328,65 ANT'],
      ]}
      renderEntry={([address, amount]) => {
        return [<Account address={account} />, <Amount>{amount}</Amount>]
      }}
    />
  )
}
```

#### renderEntryActions(entry, index, { selected, mode }) <a href="#renderentryactions-entry-2c-index-2c-7b-selected-2c-mode-7d" id="renderentryactions-entry-2c-index-2c-7b-selected-2c-mode-7d"></a>

| TYPE       | DEFAULT VALUE |
| ---------- | ------------- |
| `Function` | None          |

Renders the actions of an entry, usually as a `ContextMenu`.

#### renderEntryExpansion(entry, index, { selected, mode }) <a href="#renderentryexpansion-entry-2c-index-2c-7b-selected-2c-mode-7d" id="renderentryexpansion-entry-2c-index-2c-7b-selected-2c-mode-7d"></a>

| TYPE       | DEFAULT VALUE |
| ---------- | ------------- |
| `Function` | None          |

Make it possible for the user to expand a given entry, and reveal more content related to it. This content can be a series of rows that will adhere to the table layout or a custom React tree.

It should return one of these:

* A non empty array, to be displayed as individual rows.
* A React node, to remove any specific layout constraint.
* `null` or an empty array, to make the entry not expandable.

When a non-empty array is returned, each of its entries will be displayed as a row, whose height is determined by the value of `tableRowHeight` − even in list view mode. The alignment of these rows can also start from a specific column in table mode: see `field.childStart`.

When a React node is returned, there are no layout constraints anymore and the expansion's height depends on the returned content.

{% hint style="info" %}
Note: only one of `onSelectEntries` and `renderEntryExpansion` can be set at a time.
{% endhint %}

#### renderSelectionCount(count) <a href="#renderselectioncount-count" id="renderselectioncount-count"></a>

| TYPE       | DEFAULT VALUE |
| ---------- | ------------- |
| `Function` | None          |

Renders the label used to indicate the current selection. If not provided, “X items selected” will be displayed.

#### tableRowHeight <a href="#tablerowheight" id="tablerowheight"></a>

| TYPE     | DEFAULT VALUE     |
| -------- | ----------------- |
| `Number` | `8 * GU` (`64px`) |

The height of a row, in `px`.

#### status <a href="#status" id="status"></a>

| TYPE     | DEFAULT VALUE |
| -------- | ------------- |
| `String` | `default`     |

Can be `default`, `loading`, `empty-filters` and `empty-search`. The correct illustration and text styles are used depending on the status.

#### emptyState <a href="#emptystate" id="emptystate"></a>

Use this prop to customize the empty state of `DataView`. The type of empty state currently active is determined by the `status` prop.

This prop accepts two types: a configuration object or a function.

#### **Configuration object**

The object can define one of the possible values of `status` as keys, and an object.

This object can contain the following values:

* `title`, `subtitle` and `illustration` are React nodes that can override any of these parts. Set to `null` to disable.
* `displayLoader` is a boolean that can be used to display a loader before the title.
* `clearLabel` is the content of the clearing link, and can contain any React node. Set to `null` to disable. See also `onStatusEmptyClear`.

Any undefined `status`, or undefined key on that object will use the default. `null` can be passed to disable a specific part of the empty state.

The default values are the following:

```jsx
<DataView
  emptyState={{
    default: {
      displayLoader: false,
      title: 'No data available.',
      subtitle: null,
      illustration: <img src="empty-state-illustration-blue.png" alt="" />,
      clearLabel: null,
    },
    loading: {
      displayLoader: true,
      title: 'No data available.',
      subtitle: null,
      illustration: <img src="empty-state-illustration-blue.png" alt="" />,
      clearLabel: null,
    },
    'empty-filters': {
      displayLoader: false,
      title: 'No results found.',
      subtitle: 'We can’t find any item matching your filter selection.',
      illustration: <img src="empty-state-illustration-red.png" alt="" />,
      clearLabel: 'Clear filters',
    },
    'empty-search': {
      displayLoader: false,
      title: 'No results found.',
      subtitle: 'We can’t find any item matching your search query.',
      illustration: <img src="empty-state-illustration-red.png" alt="" />,
      clearLabel: 'Clear filters',
    },
  }}
/>
```

#### **Function mode**

The function allows to completely override the empty state content. It takes the current `status` as a unique parameter, and is expected to return a React node, or `null` to let DataView display the default.

Use it this way:

```jsx
<DataView
  emptyState={status => {
    if (status === 'loading') {
      return <div>Loading!</div>
    }

    // Use the default for other `status` values.
    return null
  }}
/>
```

#### onStatusEmptyClear <a href="#onstatusemptyclear" id="onstatusemptyclear"></a>

| TYPE       | DEFAULT VALUE |
| ---------- | ------------- |
| `Function` | None          |

Called when one of the default clearing links gets clicked. This is happening in `empty-filters` or `empty-search` by default, or if a custom status has a non-empty `clearLabel`.

#### statusEmpty <a href="#statusempty" id="statusempty"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Node` | None          |

If you want to customize the `default` status content.

{% hint style="info" %}
**Note: this prop is deprecated and will be removed in a future version. Please use `emptyState` instead.**
{% endhint %}

#### statusLoading <a href="#statusloading" id="statusloading"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Node` | None          |

If you want to customize the `loading` status content.

{% hint style="info" %}
**Note: this prop is deprecated and will be removed in a future version. Please use `emptyState` instead.**
{% endhint %}

#### statusEmptyFilters <a href="#statusemptyfilters" id="statusemptyfilters"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Node` | None          |

If you want to customize the `empty-filters` status content.

{% hint style="info" %}
**Note: this prop is deprecated and will be removed in a future version. Please use `emptyState` instead.**
{% endhint %}

#### statusEmptySearch <a href="#statusemptysearch" id="statusemptysearch"></a>

| TYPE   | DEFAULT VALUE |
| ------ | ------------- |
| `Node` | None          |

If you want to customize the `empty-search` status content.

{% hint style="info" %}
**Note: this prop is deprecated and will be removed in a future version. Please use `emptyState` instead.**
{% endhint %}
