# APMRegistry

## contract APMRegistry

is [AragonApp](../apps/aragonapp.md), [AppProxyFactory](../factory/appproxyfactory.md), [APMInternalAppNames](apminternalappnames.md)

Source: [contracts/apm/APMRegistry.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/apm/APMRegistry.sol)

## Index

* [NewRepo](apmregistry.md#newrepo)
* [\_newRepo](apmregistry.md#\_newrepo)
* [initialize](apmregistry.md#initialize)
* [newClonedRepo](apmregistry.md#newclonedrepo)
* [newRepo](apmregistry.md#newrepo)
* [newRepoWithVersion](apmregistry.md#newrepowithversion)
* [repoAppId](apmregistry.md#repoappid)

## Reference

### Events

#### **NewRepo** <a href="#newrepo" id="newrepo"></a>

`event`` `**`NewRepo`**`(bytes32 id, string name, address repo)`



Parameters:

* `id` - bytes32
* `name` - string
* `repo` - address

### Functions

#### **\_newRepo** <a href="#_newrepo" id="_newrepo"></a>

`function`` `**`_newRepo`**`(string _name, address _dev) internal returns (Repo)`



Parameters:

* `_name` - string
* `_dev` - address

Returns:

* Repo

#### **initialize** <a href="#initialize" id="initialize"></a>

`function`` `**`initialize`**`(ENSSubdomainRegistrar _registrar) public`



NEEDS CREATE\_NAME\_ROLE and POINT\_ROOTNODE\_ROLE permissions on registrar, Initialize can only be called once. It saves the block number in which it was initialized, Initialize this APMRegistry instance and set \`\_registrar\` as the ENS subdomain registrar.

Modifiers:

* [onlyInit](../common/initializable.md#getinitializationblock)

Parameters:

* `_registrar` - ENSSubdomainRegistrar instance that holds registry root node ownership

#### **newClonedRepo** <a href="#newclonedrepo" id="newclonedrepo"></a>

`function`` `**`newClonedRepo`**`() internal returns (Repo)`



Returns:

* Repo

#### **newRepo** <a href="#newrepo" id="newrepo"></a>

`function`` `**`newRepo`**`(string _name, address _dev) public returns (Repo)`



Create new repo in registry with \`\_name\`.

Modifiers:&#x20;

* [auth](../apps/aragonapp.md#authp)

Parameters:

* `_name` - Repo name, must be ununsed
* `_dev` - Address that will be given permission to create versions

Returns:

* Repo

#### **newRepoWithVersion** <a href="#newrepowithversion" id="newrepowithversion"></a>

`function`` `**`newRepoWithVersion`**`(string _name, address _dev, uint16[] _initialSemanticVersion, address _contractAddress, bytes _contentURI) public returns (Repo)`

***

Create new repo in registry with \`\_name\` and publish a first version with contract \`\_contractAddress\` and content \`@fromHex(\_contentURI)\`.

Modifiers:&#x20;

* [auth](../apps/aragonapp.md#authp)

Parameters:

* `_name` - Repo name
* `_dev` - Address that will be given permission to create versions
* `_initialSemanticVersion` - Semantic version for new repo version
* `_contractAddress` - address for smart contract logic for version (if set to 0, it uses last versions' contractAddress)
* `_contentURI` - External URI for fetching new version's content

Returns:

* Repo

#### **repoAppId** <a href="#repoappid" id="repoappid"></a>

`function`` `**`repoAppId`**`() internal view returns (bytes32)`



Returns:

* bytes32
