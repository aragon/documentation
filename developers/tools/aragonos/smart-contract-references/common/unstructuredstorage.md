# UnstructuredStorage

## library UnstructuredStorage

Source: [contracts/common/UnstructuredStorage.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/common/UnstructuredStorage.sol)

## Index

* [getStorageAddress](unstructuredstorage.md#getstorageaddress)
* [getStorageBool](unstructuredstorage.md#getstoragebool)
* [getStorageBytes32](unstructuredstorage.md#getstoragebytes32)
* [getStorageUint256](unstructuredstorage.md#getstorageuint256-1)
* [setStorageAddress](unstructuredstorage.md#setstorageaddress)
* [setStorageBool](unstructuredstorage.md#setstoragebool)
* [setStorageBytes32](unstructuredstorage.md#setstoragebytes32)
* [setStorageUint256](unstructuredstorage.md#setstorageuint256-2)

## Reference

### Functions

#### **getStorageAddress** <a href="#getstorageaddress" id="getstorageaddress"></a>

`function`` `**`getStorageAddress`**`(bytes32 position) internal view returns (address)`

***

Parameters:

* `position` - bytes32

Returns:

* address

#### **getStorageBool** <a href="#getstoragebool" id="getstoragebool"></a>

`function`` `**`getStorageBool`**`(bytes32 position) internal view returns (bool)`

***

Parameters:

* `position` - bytes32

Returns:

* bool

#### **getStorageBytes32** <a href="#getstoragebytes32" id="getstoragebytes32"></a>

`function`` `**`getStorageBytes32`**`(bytes32 position) internal view returns (bytes32)`

***

Parameters:

* `position` - bytes32

Returns:

* bytes32

#### **getStorageUint256** <a href="#getstorageuint256-1" id="getstorageuint256-1"></a>

`function`` `**`getStorageUint256`**`(bytes32 position) internal view returns (uint256)`

***

Parameters:

* `position` - bytes32

Returns:

* uint256

#### **setStorageAddress** <a href="#setstorageaddress" id="setstorageaddress"></a>

`function`` `**`setStorageAddress`**`(bytes32 position, address data) internal`

***

Parameters:

* `position` - bytes32
* `data` - address

#### **setStorageBool** <a href="#setstoragebool" id="setstoragebool"></a>

`function`` `**`setStorageBool`**`(bytes32 position, bool data) internal`

***

Parameters:

* `position` - bytes32
* `data` - bool

#### **setStorageBytes32** <a href="#setstoragebytes32" id="setstoragebytes32"></a>

`function`` `**`setStorageBytes32`**`(bytes32 position, bytes32 data) internal`

***

Parameters:

* `position` - bytes32
* `data` - bytes32

#### **setStorageUint256** <a href="#setstorageuint256-2" id="setstorageuint256-2"></a>

`function`` `**`setStorageUint256`**`(bytes32 position, uint256 data) internal`

***

Parameters:

* `position` - bytes32
* `data` - uint256
