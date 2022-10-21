# TimeHelpers

## contract TimeHelpers

Source: [contracts/common/TimeHelpers.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/common/TimeHelpers.sol)

## Index

* [getBlockNumber](timehelpers.md#getblocknumber)
* [getBlockNumber64](timehelpers.md#getblocknumber64)
* [getTimestamp](timehelpers.md#gettimestamp)
* [getTimestamp64](timehelpers.md#gettimestamp64)

## Reference

### Functions

#### **getBlockNumber** <a href="#getblocknumber" id="getblocknumber"></a>

`function`` `**`getBlockNumber`**`() internal view returns (uint256)`

***

Returns the current block number. Using a function rather than \`block.number\` allows us to easily mock the block number in tests.



Returns:

* uint256

#### **getBlockNumber64** <a href="#getblocknumber64" id="getblocknumber64"></a>

`function`` `**`getBlockNumber64`**`() internal view returns (uint64)`

***

Returns the current block number, converted to uint64. Using a function rather than \`block.number\` allows us to easily mock the block number in tests.

Returns:

* uint64

#### **getTimestamp** <a href="#gettimestamp" id="gettimestamp"></a>

`function`` `**`getTimestamp`**`() internal view returns (uint256)`

***

Returns the current timestamp. Using a function rather than \`block.timestamp\` allows us to easily mock it in tests.

Returns:

* uint256

#### **getTimestamp64** <a href="#gettimestamp64" id="gettimestamp64"></a>

`function`` `**`getTimestamp64`**`() internal view returns (uint64)`

***

Returns the current timestamp, converted to uint64. Using a function rather than \`block.timestamp\` allows us to easily mock it in tests.

Returns:

* uint64
