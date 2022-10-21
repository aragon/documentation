# CallsScript

## contract CallsScript

is [BaseEVMScriptExecutor](baseevmscriptexecutor.md)

Source: [contracts/evmscript/executors/CallsScript.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/evmscript/executors/CallsScript.sol)

## Index

* [LogScriptCall](callsscript.md#logscriptcall)
* [execScript](callsscript.md#execscript)
* [executorType](callsscript.md#executortype)

## Reference

### Events

#### **LogScriptCall** <a href="#logscriptcall" id="logscriptcall"></a>

`event`` `**`LogScriptCall`**`(address sender, address src, address dst)`

***

Parameters:

* `sender` - address
* `src` - address
* `dst` - address

### Functions

#### **execScript** <a href="#execscript" id="execscript"></a>

`function`` `**`execScript`**`(bytes _script, bytes , address[] _blacklist) external returns (bytes)`

***

Executes a number of call scripts.

Modifiers:

* [isInitialized](../common/initializable.md#getinitializationblock)

Parameters:

* `_script` - \[ specId (uint32) ] many calls with this structure -> \[ to (address: 20 bytes) ] \[ calldataLength (uint32: 4 bytes) ] \[ calldata (calldataLength bytes) ]- bytes
* `_blacklist` - Addresses the script cannot call to, or will revert.

Returns:

* Always returns empty byte array

#### **executorType** <a href="#executortype" id="executortype"></a>

`function`` `**`executorType`**`() external pure returns (bytes32)`

***

Returns:

* bytes32
