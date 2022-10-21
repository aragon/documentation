# IEVMScriptExecutor

## interface IEVMScriptExecutor

Source: [contracts/evmscript/IEVMScriptExecutor.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/evmscript/IEVMScriptExecutor.sol)

## Index

* [execScript](ievmscriptexecutor.md#execscript)
* [executorType](ievmscriptexecutor.md#executortype)

## Reference

### Functions

#### **execScript** <a href="#execscript" id="execscript"></a>

`abstract function`` `**`execScript`**`(bytes script, bytes input, address[] blacklist) external returns (bytes)`

***

Parameters:

* `script` - bytes
* `input` - bytes
* `blacklist` - address\[]

Returns:

* bytes

#### **executorType** <a href="#executortype" id="executortype"></a>

`abstract function`` `**`executorType`**`() external pure returns (bytes32)`

***

Returns:

* bytes32
