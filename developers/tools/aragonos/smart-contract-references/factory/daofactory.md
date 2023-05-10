# DAOFactory

## contract DAOFactory

Source: [contracts/factory/DAOFactory.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/factory/DAOFactory.sol)

## Index

* [DeployDAO](daofactory.md#deploydao)
* [DeployEVMScriptRegistry](daofactory.md#deployevmscriptregistry)
* [fallback](daofactory.md#fallback)
* [newDAO](daofactory.md#newdao)

## Reference

### Events

#### **DeployDAO** <a href="#deploydao" id="deploydao"></a>

`event`` `**`DeployDAO`**`(address dao)`

***

Parameters:

* `dao` - address

#### **DeployEVMScriptRegistry** <a href="#deployevmscriptregistry" id="deployevmscriptregistry"></a>

`event`` `**`DeployEVMScriptRegistry`**`(address reg)`

***

Parameters:

* `reg` - address

### Functions

#### **fallback** <a href="#fallback" id="fallback"></a>

`function (IKernel _baseKernel, IACL _baseACL, EVMScriptRegistryFactory _regFactory) public`

***

Create a new DAOFactory, creating DAOs with Kernels proxied to \`\_baseKernel\`, ACLs proxied to \`\_baseACL\`, and new EVMScriptRegistries created from \`\_regFactory\`.

Parameters:

* `_baseKernel` - Base Kernel
* `_baseACL` - Base ACL
* `_regFactory` - EVMScriptRegistry factory

#### **newDAO** <a href="#newdao" id="newdao"></a>

`function`` `**`newDAO`**`(address _root) public returns (Kernel)`

***

Create a new DAO with \`\_root\` set as the initial admin.

Parameters:

* `_root` - Address that will be granted control to setup DAO permissions

Returns:

* Newly created DAO
