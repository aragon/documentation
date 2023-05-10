# IEVMScriptRegistry

## interface IEVMScriptRegistry

Source: [contracts/evmscript/IEVMScriptRegistry.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/evmscript/IEVMScriptRegistry.sol)

## Index

* [addScriptExecutor](ievmscriptregistry.md#addscriptexecutor)
* [disableScriptExecutor](ievmscriptregistry.md#disablescriptexecutor)
* [getScriptExecutor](ievmscriptregistry.md#getscriptexecutor)

## Reference

### Functions

#### **addScriptExecutor** <a href="#addscriptexecutor" id="addscriptexecutor"></a>

`abstract function`` `**`addScriptExecutor`**`(IEVMScriptExecutor executor) external returns (uint)`

***

Parameters:

* `executor` - IEVMScriptExecutor

Returns:

* uint

#### **disableScriptExecutor** <a href="#disablescriptexecutor" id="disablescriptexecutor"></a>

`abstract function`` `**`disableScriptExecutor`**`(uint256 executorId) external`

***

Parameters:

* `executorId` - uint256

#### **getScriptExecutor** <a href="#getscriptexecutor" id="getscriptexecutor"></a>

`abstract function`` `**`getScriptExecutor`**`(bytes script) public view returns (IEVMScriptExecutor)`

***

Parameters:

* `script` - bytes

Returns:

* IEVMScriptExecutor
