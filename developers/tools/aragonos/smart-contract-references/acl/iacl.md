# IACL

## interface IACL

Source: [contracts/acl/IACL.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/acl/IACL.sol)\


## Index

* [hasPermission](iacl.md#haspermission)
* [initialize](iacl.md#initialize)

## Reference

### Functions

#### **hasPermission** <a href="#haspermission" id="haspermission"></a>

`abstract function`` `**`hasPermission`**`(address who, address where, bytes32 what, bytes how) public view returns (bool)`



Parameters:

* `who` - address
* `where` - address
* `what` - bytes32
* `how` - bytes

Returns:

* bool

#### **initialize** <a href="#initialize" id="initialize"></a>

`abstract function`` `**`initialize`**`(address permissionsCreator) external`

***

Parameters:

* `permissionsCreator` - address
