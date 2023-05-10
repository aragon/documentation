# APMRegistryFactory

## contract APMRegistryFactory

is [APMInternalAppNames](../apm/apminternalappnames.md)

Source: [contracts/factory/APMRegistryFactory.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/factory/APMRegistryFactory.sol)

## Index

* [DeployAPM](apmregistryfactory.md#deployapm)
* [b](apmregistryfactory.md#b)
* [configureAPMPermissions](apmregistryfactory.md#configureapmpermissions)
* [fallback](apmregistryfactory.md#fallback)
* [newAPM](apmregistryfactory.md#newapm)

## Reference

### Events

#### **DeployAPM** <a href="#deployapm" id="deployapm"></a>

`event`` `**`DeployAPM`**`(bytes32 node, address apm)`

***

Parameters:

* `node` - bytes32
* `apm` - address

### Functions

#### **b** <a href="#b" id="b"></a>

`function`` `**`b`**`(string x) internal pure returns (bytes)`

***

Parameters:

* `x` - string

Returns:

* bytes

#### **configureAPMPermissions** <a href="#configureapmpermissions" id="configureapmpermissions"></a>

`function`` `**`configureAPMPermissions`**`(ACL _acl, APMRegistry _apm, address _root) internal`

***

Parameters:

* `_acl` - ACL
* `_apm` - APMRegistry
* `_root` - address

#### **fallback** <a href="#fallback" id="fallback"></a>

`function (DAOFactory _daoFactory, APMRegistry _registryBase, Repo _repoBase, ENSSubdomainRegistrar _ensSubBase, ENS _ens, ENSFactory _ensFactory) public`

***

Requires either a given ENS registrar or ENSFactory (used for generating a new ENS in test environments)., Create a new factory for deploying Aragon Package Managers (aragonPM).

Parameters:

* `_daoFactory` - Base factory for deploying DAOs
* `_registryBase` - APMRegistry base contract location
* `_repoBase` - Repo base contract location
* `_ensSubBase` - ENSSubdomainRegistrar base contract location
* `_ens` - ENS instance
* `_ensFactory` - ENSFactory (used to generated a new ENS if no ENS is given)

#### **newAPM** <a href="#newapm" id="newapm"></a>

`function`` `**`newAPM`**`(bytes32 _tld, bytes32 _label, address _root) public returns (APMRegistry)`

***

Create a new Aragon Package Manager (aragonPM) DAO, holding the \`\_label\` subdomain from parent \`\_tld\` and controlled by \`\_root\`.

Parameters:

* `_tld` - The parent node of the controlled subdomain
* `_label` - The subdomain label
* `_root` - Manager for the new aragonPM DAO

Returns:

* The new aragonPM's APMRegistry app
