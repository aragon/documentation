# IKernel

## contract IKernel

is [IKernelEvents](ikernelevents.md), [IVaultRecoverable](../common/ivaultrecoverable.md)

Source: [contracts/kernel/IKernel.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/kernel/IKernel.sol)

## Index

* [acl](ikernel.md#acl)
* [getApp](ikernel.md#getapp)
* [hasPermission](ikernel.md#haspermission)
* [setApp](ikernel.md#setapp)

## Reference

### Functions

#### **acl** <a href="#acl" id="acl"></a>

`abstract function`` `**`acl`**`() public view returns (IACL)`

***

Returns:

* IACL

#### **getApp** <a href="#getapp" id="getapp"></a>

`abstract function`` `**`getApp`**`(bytes32 namespace, bytes32 appId) public view returns (address)`

***

Parameters:

* `namespace` - bytes32
* `appId` - bytes32

Returns:

* address

#### **hasPermission** <a href="#haspermission" id="haspermission"></a>

`abstract function`` `**`hasPermission`**`(address who, address where, bytes32 what, bytes how) public view returns (bool)`

***

Parameters:

* `who` - address
* `where` - address
* `what` - bytes32
* `how` - bytes

Returns:

* bool

#### **setApp** <a href="#setapp" id="setapp"></a>

`abstract function`` `**`setApp`**`(bytes32 namespace, bytes32 appId, address app) public`

***

Parameters:

* `namespace` - bytes32
* `appId` - bytes32
* `app` - address
