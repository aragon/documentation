# Initializable

## contract Initializable

is [TimeHelpers](timehelpers.md)

Source: [contracts/common/Initializable.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/common/Initializable.sol)

## Index

* [getInitializationBlock](initializable.md#getinitializationblock)
* [hasInitialized](initializable.md#hasinitialized)
* [initialized](initializable.md#initialized)
* [initializedAt](initializable.md#initializedat)
* [isInitialized](initializable.md#isinitialized)
* [onlyInit](initializable.md#onlyinit)

## Reference

### Modifiers

#### **isInitialized** <a href="#isinitialized" id="isinitialized"></a>

`modifier`` `**`isInitialized`**`()`

#### **onlyInit** <a href="#onlyinit" id="onlyinit"></a>

`modifier`` `**`onlyInit`**`()`

### Functions

#### **getInitializationBlock** <a href="#getinitializationblock" id="getinitializationblock"></a>

`function`` `**`getInitializationBlock`**`() public view returns (uint256)`

***

Returns:

* Block number in which the contract was initialized

#### **hasInitialized** <a href="#hasinitialized" id="hasinitialized"></a>

`function`` `**`hasInitialized`**`() public view returns (bool)`

***

Returns:

* Whether the contract has been initialized by the time of the current block

#### **initialized** <a href="#initialized" id="initialized"></a>

`function`` `**`initialized`**`() internal`

***

Function to be called by top level contract after initialization has finished.

Modifiers:

* [onlyInit](initializable.md#getinitializationblock)

#### **initializedAt** <a href="#initializedat" id="initializedat"></a>

`function`` `**`initializedAt`**`(uint256 _blockNumber) internal`

***

Function to be called by top level contract after initialization to enable the contract at a future block number rather than immediately.

Modifiers:

* [onlyInit](initializable.md#getinitializationblock)

Parameters:

* `_blockNumber` - uint256
