# ENSSubdomainRegistrar

## contract ENSSubdomainRegistrar

is [AragonApp](../apps/aragonapp.md), [ENSConstants](ensconstants.md)

Source: [contracts/ens/ENSSubdomainRegistrar.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/ens/ENSSubdomainRegistrar.sol)

## Index

* [DeleteName](enssubdomainregistrar.md#deletename)
* [NewName](enssubdomainregistrar.md#newname)
* [\_createName](enssubdomainregistrar.md#\_createname)
* [\_pointToResolverAndResolve](enssubdomainregistrar.md#\_pointtoresolverandresolve)
* [createName](enssubdomainregistrar.md#createname)
* [createNameAndPoint](enssubdomainregistrar.md#createnameandpoint)
* [deleteName](enssubdomainregistrar.md#deletename-1)
* [getAddr](enssubdomainregistrar.md#getaddr)
* [getNodeForLabel](enssubdomainregistrar.md#getnodeforlabel)
* [initialize](enssubdomainregistrar.md#initialize)
* [pointRootNode](enssubdomainregistrar.md#pointrootnode)

## Reference

### Events

#### **DeleteName** <a href="#deletename" id="deletename"></a>

`event`` `**`DeleteName`**`(bytes32 node, bytes32 label)`

***

Parameters:

* `node` - bytes32
* `label` - bytes32

#### **NewName** <a href="#newname" id="newname"></a>

`event`` `**`NewName`**`(bytes32 node, bytes32 label)`

***

Parameters:

* `node` - bytes32
* `label` - bytes32

### Functions

#### **\_createName** <a href="#_createname" id="_createname"></a>

`function`` `**`_createName`**`(bytes32 _label, address _owner) internal returns (bytes32)`

***

Parameters:

* `_label` - bytes32
* `_owner` - address

Returns:

* bytes32

#### **\_pointToResolverAndResolve** <a href="#_pointtoresolverandresolve" id="_pointtoresolverandresolve"></a>

`function`` `**`_pointToResolverAndResolve`**`(bytes32 _node, address _target) internal`

***

Parameters:

* `_node` - bytes32
* `_target` - address

#### **createName** <a href="#createname" id="createname"></a>

`function`` `**`createName`**`(bytes32 _label, address _owner) external returns (bytes32)`

***

Create a new ENS subdomain record for \`\_label\` and assign ownership to \`\_owner\`.

Modifiers:

* [auth](../apps/aragonapp.md#authp)

Parameters:

* `_label` - Label of new subdomain
* `_owner` - Owner of new subdomain

Returns:

* node Hash of created node

#### **createNameAndPoint** <a href="#createnameandpoint" id="createnameandpoint"></a>

`function`` `**`createNameAndPoint`**`(bytes32 _label, address _target) external returns (bytes32)`

***

Create a new ENS subdomain record for \`\_label\` that resolves to \`\_target\` and is owned by this ENSSubdomainRegistrar.

Modifiers:

* [auth](../apps/aragonapp.md#authp)

Parameters:

* `_label` - Label of new subdomain
* `_target` - Ethereum address this new subdomain label will point to

Returns:

* node Hash of created node

#### **deleteName** <a href="#deletename" id="deletename"></a>

`function`` `**`deleteName`**`(bytes32 _label) external`

***

Deregister ENS subdomain record for \`\_label\`.

Modifiers:

* [auth](../apps/aragonapp.md#authp)

Parameters:

* `_label` - Label of subdomain to deregister

#### **getAddr** <a href="#getaddr" id="getaddr"></a>

`function`` `**`getAddr`**`(bytes32 node) internal view returns (address)`

***

Parameters:

* `node` - bytes32

Returns:

* address

#### **getNodeForLabel** <a href="#getnodeforlabel" id="getnodeforlabel"></a>

`function`` `**`getNodeForLabel`**`(bytes32 _label) internal view returns (bytes32)`

***

Parameters:

* `_label` - bytes32

Returns:

* bytes32

#### **initialize** <a href="#initialize" id="initialize"></a>

`function`` `**`initialize`**`(AbstractENS _ens, bytes32 _rootNode) public`

***

Initialize can only be called once. It saves the block number in which it was initialized. This contract must be the owner of the \`\_rootNode\` node so that it can create subdomains. Initialize this ENSSubdomainRegistrar instance with \`\_ens\` as the root ENS registry and \`\_rootNode\` as the node to allocate subdomains under.

Modifiers:

* [onlyInit](../common/initializable.md#getinitializationblock)

Parameters:

* `_ens` - Address of ENS registry
* `_rootNode` - Node to allocate subdomains under

#### **pointRootNode** <a href="#pointrootnode" id="pointrootnode"></a>

`function`` `**`pointRootNode`**`(address _target) external`

***

Resolve this ENSSubdomainRegistrar's root node to \`\_target\`.

Modifiers:

* [auth](../apps/aragonapp.md#authp)

Parameters:

* `_target` - Ethereum address root node will point to
