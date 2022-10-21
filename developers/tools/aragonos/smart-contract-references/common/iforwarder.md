# IForwarder

## interface IForwarder

Source: [contracts/common/IForwarder.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/common/IForwarder.sol)

## Index

* [canForward](iforwarder.md#canforward)
* [forward](iforwarder.md#forward)
* [isForwarder](iforwarder.md#isforwarder)

## Reference

### Functions

#### **canForward** <a href="#canforward" id="canforward"></a>

`abstract function`` `**`canForward`**`(address sender, bytes evmCallScript) public view returns (bool)`

***

Parameters:

* `sender` - address
* `evmCallScript` - bytes

Returns:

* bool

#### **forward** <a href="#forward" id="forward"></a>

`abstract function`` `**`forward`**`(bytes evmCallScript) public`

***

Parameters:

`evmCallScript` - bytes

#### **isForwarder** <a href="#isforwarder" id="isforwarder"></a>

`abstract function`` `**`isForwarder`**`() external pure returns (bool)`

Returns:

* bool
