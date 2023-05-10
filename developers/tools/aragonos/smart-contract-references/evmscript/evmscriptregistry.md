# EVMScriptRegistry

## contract EVMScriptRegistry

is [IEVMScriptRegistry](ievmscriptregistry.md), [EVMScriptRegistryConstants](evmscriptregistryconstants.md), [AragonApp](../apps/aragonapp.md)

Source: [contracts/evmscript/EVMScriptRegistry.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/evmscript/EVMScriptRegistry.sol)

## Index

* [DisableExecutor](evmscriptregistry.md#disableexecutor)
* [EnableExecutor](evmscriptregistry.md#enableexecutor)
* [addScriptExecutor](evmscriptregistry.md#addscriptexecutor)
* [disableScriptExecutor](evmscriptregistry.md#disablescriptexecutor)
* [enableScriptExecutor](evmscriptregistry.md#enablescriptexecutor)
* [executorExists](evmscriptregistry.md#executorexists)
* [getScriptExecutor](evmscriptregistry.md#getscriptexecutor)
* [initialize](evmscriptregistry.md#initialize)

## Reference

### Events

#### **DisableExecutor** <a href="#disableexecutor" id="disableexecutor"></a>

`event`` `**`DisableExecutor`**`(uint256 executorId, address executorAddress)`



Parameters:

* `executorId` - uint256
* `executorAddress` - address

#### **EnableExecutor** <a href="#enableexecutor" id="enableexecutor"></a>

`event`` `**`EnableExecutor`**`(uint256 executorId, address executorAddress)`



Parameters:

* `executorId` - uint256
* `executorAddress` - address

### Modifiers

#### **executorExists** <a href="#executorexists" id="executorexists"></a>

`modifier`` `**`executorExists`**`(uint256 _executorId)`



Parameters:

* `_executorId` - uint256

### Functions

#### **addScriptExecutor** <a href="#addscriptexecutor" id="addscriptexecutor"></a>

`function`` `**`addScriptExecutor`**`(IEVMScriptExecutor _executor) external returns (uint256)`



Add a new script executor with address \`\_executor\` to the registry.

Modifiers:

* [auth](../apps/aragonapp.md#authp)

Parameters:

* `_executor` - Address of the IEVMScriptExecutor that will be added to the registry

Returns:

* id Identifier of the executor in the registry

#### **disableScriptExecutor** <a href="#disablescriptexecutor" id="disablescriptexecutor"></a>

`function`` `**`disableScriptExecutor`**`(uint256 _executorId) external`



Disable script executor with ID \`\_executorId\`.

Modifiers:

* [authP](../apps/aragonapp.md#canperform)

Parameters:

* `_executorId` - Identifier of the executor in the registry

#### **enableScriptExecutor** <a href="#enablescriptexecutor" id="enablescriptexecutor"></a>

`function`` `**`enableScriptExecutor`**`(uint256 _executorId) external`



Enable script executor with ID \`\_executorId\`.

Modifiers:

* [authP executorExists](evmscriptregistry.md#addscriptexecutor)

Parameters:

* `_executorId` - Identifier of the executor in the registry

#### **getScriptExecutor** <a href="#getscriptexecutor" id="getscriptexecutor"></a>

`function`` `**`getScriptExecutor`**`(bytes _script) public view returns (IEVMScriptExecutor)`

``

Get the script executor that can execute a particular script based on its first 4 bytes.

Parameters:

* `_script` - EVMScript being inspected

Returns:

* IEVMScriptExecutor

#### **initialize** <a href="#initialize" id="initialize"></a>

`function`` `**`initialize`**`() public`

``

Initialize the registry.

Modifiers:

* [onlyInit](../common/initializable.md#getinitializationblock)
