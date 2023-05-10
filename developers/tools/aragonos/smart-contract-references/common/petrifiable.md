# Petrifiable

## contract Petrifiable

is [Initializable](initializable.md)

Source: [contracts/common/Petrifiable.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/common/Petrifiable.sol)

## Index

* [isPetrified](petrifiable.md#ispetrified)
* [petrify](petrifiable.md#petrify)

## Reference

### Functions

#### **isPetrified** <a href="#ispetrified" id="ispetrified"></a>

`function`` `**`isPetrified`**`() public view returns (bool)`

***

Returns:

* bool

#### **petrify** <a href="#petrify" id="petrify"></a>

`function`` `**`petrify`**`() internal`

***

Function to be called by top level contract to prevent being initialized. Useful for freezing base contracts when they're used behind proxies.

Modifiers:

* [onlyInit](initializable.md#getinitializationblock)
