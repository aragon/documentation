# ScriptHelpers

## library ScriptHelpers

Source: [contracts/evmscript/ScriptHelpers.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/evmscript/ScriptHelpers.sol)

## Index

* [addressAt](scripthelpers.md#addressat)
* [getSpecId](scripthelpers.md#getspecid)
* [locationOf](scripthelpers.md#locationof)
* [toBytes](scripthelpers.md#tobytes)
* [uint256At](scripthelpers.md#uint256at)
* [uint32At](scripthelpers.md#uint32at)

## Reference

### Functions

#### **addressAt** <a href="#addressat" id="addressat"></a>

`function`` `**`addressAt`**`(bytes _data, uint256 _location) internal pure returns (address)`

***

Parameters:

* `_data` - bytes
* `_location` - uint256

Returns:

* address

#### **getSpecId** <a href="#getspecid" id="getspecid"></a>

`function`` `**`getSpecId`**`(bytes _script) internal pure returns (uint32)`

***

Parameters:

* `_script` - bytes

Returns:

* uint32

#### **locationOf** <a href="#locationof" id="locationof"></a>

`function`` `**`locationOf`**`(bytes _data, uint256 _location) internal pure returns (uint256)`

***

Parameters:

* `_data` - bytes
* `_location` - uint256

Returns:

* uint256

#### **toBytes** <a href="#tobytes" id="tobytes"></a>

`function`` `**`toBytes`**`(bytes4 _sig) internal pure returns (bytes)`

***

Parameters:

* `_sig` - bytes4

Returns:

* bytes

#### **uint256At** <a href="#uint256at" id="uint256at"></a>

`function`` `**`uint256At`**`(bytes _data, uint256 _location) internal pure returns (uint256)`

***

Parameters:

* `_data` - bytes
* `_location` - uint256

Returns:

* uint256

#### **uint32At** <a href="#uint32at" id="uint32at"></a>

`function`` `**`uint32At`**`(bytes _data, uint256 _location) internal pure returns (uint32)`

***

Parameters:

* `_data` - bytes
* `_location` - uint256

Returns:

* uint32
