# TransactionProgress

## Usage <a href="#usage" id="usage"></a>

```jsx
function App() {
  const [visible, setVisible] = useState(false)
  const opener = useRef()

  return (
    <div>
      <div ref={opener}>
        <Button onClick={() => setVisible(true)}>Check transaction</Button>
      </div>
      <TransactionProgress
        transactionHashUrl="https://etherscan.io/tx/0x5c50…2060"
        progress={0.3}
        visible={visible}
        endTime={new Date(Date.now() + 100000)}
        onClose={() => setVisible(false)}
        opener={opener}
        slow
      />
    </div>
  )
}
```

## Demonstration

![](<../../../../.gitbook/assets/Schermata 2022-06-25 alle 22.48.33.png>)

## Props <a href="#props" id="props"></a>

#### `transactionHash` <a href="#transactionhash" id="transactionhash"></a>

* Type: `String`

Hash of transaction which will be opened on Etherscan.

#### `progress` <a href="#progress" id="progress"></a>

* Type: `number`

Progress of transaction.

#### `endTime` <a href="#endtime" id="endtime"></a>

* Type: `Date` object

Estimated end time of transaction.

#### `slow` <a href="#slow" id="slow"></a>

* Type: `Bool`
* Default: `false`

Set to true to inform the user that a transaction is taking longer than expected.

#### `handleClose` <a href="#handleclose" id="handleclose"></a>

* Type: `Function`

Provide a function that handles closing of the component.
