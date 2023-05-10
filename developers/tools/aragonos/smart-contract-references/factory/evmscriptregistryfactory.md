# EVMScriptRegistryFactory

## contract EVMScriptRegistryFactory

is [EVMScriptRegistryConstants](../evmscript/evmscriptregistryconstants.md)

Source: [contracts/factory/EVMScriptRegistryFactory.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/factory/EVMScriptRegistryFactory.sol)

## Index

* [fallback](evmscriptregistryfactory.md#fallback)
* [newEVMScriptRegistry](evmscriptregistryfactory.md#newevmscriptregistry)

## Reference

### Functions

#### **fallback** <a href="#fallback" id="fallback"></a>

`function () public`

***

Create a new EVMScriptRegistryFactory.

#### **newEVMScriptRegistry** <a href="#newevmscriptregistry" id="newevmscriptregistry"></a>

`function`` `**`newEVMScriptRegistry`**`(Kernel _dao) public returns (EVMScriptRegistry)`

***

Install a new pinned instance of EVMScriptRegistry on \`\_dao\`.

Parameters:

* `_dao` - Kernel

Returns:

* Installed EVMScriptRegistry
