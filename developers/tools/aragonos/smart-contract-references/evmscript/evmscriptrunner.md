# EVMScriptRunner

## contract EVMScriptRunner

is [AppStorage](../apps/appstorage.md), [Initializable,](../common/initializable.md) [EVMScriptRegistryConstants](evmscriptregistryconstants.md), [KernelNamespaceConstants](../kernel/kernelnamespaceconstants.md)

Source: [contracts/evmscript/EVMScriptRunner.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/evmscript/EVMScriptRunner.sol)

## Index

* [ScriptResult](evmscriptrunner.md#scriptresult)
* [getEVMScriptExecutor](evmscriptrunner.md#getevmscriptexecutor)
* [getEVMScriptRegistry](evmscriptrunner.md#getevmscriptregistry)
* [protectState](evmscriptrunner.md#protectstate)
* [runScript](evmscriptrunner.md#runscript)

## Reference

### Events

#### **ScriptResult** <a href="#scriptresult" id="scriptresult"></a>

`event`` `**`ScriptResult`**`(address executor, bytes script, bytes input, bytes returnData)`

***

Parameters:

* `executor` - address
* `script` - bytes
* `input` - bytes
* `returnData` - bytes

### Modifiers

#### **protectState** <a href="#protectstate" id="protectstate"></a>

`modifier`` `**`protectState`**`()`

### Functions

#### **getEVMScriptExecutor** <a href="#getevmscriptexecutor" id="getevmscriptexecutor"></a>

`function`` `**`getEVMScriptExecutor`**`(bytes _script) public view returns (IEVMScriptExecutor)`

***

Parameters:

* `_script` - bytes

Returns:

* IEVMScriptExecutor

#### **getEVMScriptRegistry** <a href="#getevmscriptregistry" id="getevmscriptregistry"></a>

`function`` `**`getEVMScriptRegistry`**`() public view returns (IEVMScriptRegistry)`

***

Returns:

* IEVMScriptRegistry

#### **runScript** <a href="#runscript" id="runscript"></a>

`function`` `**`runScript`**`(bytes _script, bytes _input, address[] _blacklist) internal returns (bytes)`

***

Modifiers:

* [isInitialized protectState](evmscriptrunner.md#getevmscriptexecutor)

Parameters:

* `_script` - bytes
* `_input` - bytes
* `_blacklist` - address\[]

Returns:

* bytes
