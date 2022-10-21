# ENSFactory

## contract ENSFactory

is [ENSConstants](../ens/ensconstants.md)

Source: [contracts/factory/ENSFactory.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/factory/ENSFactory.sol)

## Index

* [DeployENS](ensfactory.md#deployens)
* [newENS](ensfactory.md#newens)

## Reference

### Events

#### **DeployENS** <a href="#deployens" id="deployens"></a>

`event`` `**`DeployENS`**`(address ens)`

***

Parameters:

* `ens` - address

### Functions

#### **newENS** <a href="#newens" id="newens"></a>

`function`` `**`newENS`**`(address _owner) public returns (ENS)`

***

Create a new ENS and set \`\_owner\` as the owner of the top level domain.

Parameters:

* `_owner` - Owner of .eth

Returns:

* ENS
