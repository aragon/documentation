# ACL

## contract ACL

is [IACL](iacl.md), [TimeHelpers](../common/timehelpers.md), [AragonApp](../apps/aragonapp.md), [ACLHelpers](aclhelpers.md)

Source: [contracts/acl/ACL.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/acl/ACL.sol)

## Index

* [ChangePermissionManager](acl.md#changepermissionmanager)
* [SetPermission](acl.md#setpermission)
* [SetPermissionParams](acl.md#setpermissionparams)
* [\_createPermission](acl.md#\_createpermission)
* [\_evalLogic](acl.md#\_evallogic)
* [\_evalParam](acl.md#\_evalparam)
* [\_saveParams](acl.md#\_saveparams)
* [\_setPermission](acl.md#\_setpermission)
* [\_setPermissionManager](acl.md#\_setpermissionmanager)
* [burnPermissionManager](acl.md#burnpermissionmanager)
* [checkOracle](acl.md#checkoracle)
* [compare](acl.md#compare)
* [createBurnedPermission](acl.md#createburnedpermission)
* [createPermission](acl.md#createpermission)
* [evalParams](acl.md#evalparams)
* [getPermissionManager](acl.md#getpermissionmanager)
* [getPermissionParam](acl.md#getpermissionparam)
* [getPermissionParamsLength](acl.md#getpermissionparamslength)
* [grantPermission](acl.md#grantpermissionp)
* [grantPermissionP](acl.md#grantpermissionp)
* [hasPermission](acl.md#haspermission)
* [hasPermission](acl.md#haspermission-1)
* [hasPermission](acl.md#haspermission-2)
* [initialize](acl.md#initialize)
* [noPermissionManager](acl.md#nopermissionmanager)
* [onlyPermissionManager](acl.md#onlypermissionmanager)
* [permissionHash](acl.md#permissionhash)
* [removePermissionManager](acl.md#removepermissionmanager)
* [revokePermission](acl.md#revokepermission)
* [roleHash](acl.md#rolehash)
* [setPermissionManager](acl.md#setpermissionmanager)

## Reference

### Events

#### **ChangePermissionManager** <a href="#changepermissionmanager" id="changepermissionmanager"></a>

`event`` `**`ChangePermissionManager`**`(address app, bytes32 role, address manager)`

***

Parameters:

* `app` - address
* `role` - bytes32
* `manager` - address

#### **SetPermission** <a href="#setpermission" id="setpermission"></a>

`event`` `**`SetPermission`**`(address entity, address app, bytes32 role, bool allowed)`

***

Parameters:

* `entity` - address
* `app` - address
* `role` - bytes32
* `allowed` - bool

#### **SetPermissionParams** <a href="#setpermissionparams" id="setpermissionparams"></a>

`event`` `**`SetPermissionParams`**`(address entity, address app, bytes32 role, bytes32 paramsHash)`

***

Parameters:

* `entity` - address
* `app` - address
* `role` - bytes32
* `paramsHash` - bytes32

### Modifiers

#### **noPermissionManager** <a href="#nopermissionmanager" id="nopermissionmanager"></a>

`modifier`` `**`noPermissionManager`**`(address _app, bytes32 _role)`

***

Parameters:

* `_app` - address
* `_role` - bytes32

#### **onlyPermissionManager** <a href="#onlypermissionmanager" id="onlypermissionmanager"></a>

`modifier`` `**`onlyPermissionManager`**`(address _app, bytes32 _role)`

***

Parameters:

* `_app` - address
* `_role` - bytes32

### Functions

#### **\_createPermission** <a href="#_createpermission" id="_createpermission"></a>

`function`` `**`_createPermission`**`(address _entity, address _app, bytes32 _role, address _manager) internal`

***

Internal createPermission for access inside the kernel (on instantiation).

Parameters:

* `_entity` - address
* `_app` - address
* `_role` - bytes32
* `_manager` - address

#### **\_evalLogic** <a href="#_evallogic" id="_evallogic"></a>

`function`` `**`_evalLogic`**`(Param _param, bytes32 _paramsHash, address _who, address _where, bytes32 _what, uint256[] _how) internal view returns (bool)`

***

Parameters:

* `_param` - Param
* `_paramsHash` - bytes32
* `_who` - address
* `_where` - address
* `_what` - bytes32
* `_how` - uint256\[]

Returns:&#x20;

* bool

#### **\_evalParam** <a href="#_evalparam" id="_evalparam"></a>

`function`` `**`_evalParam`**`(bytes32 _paramsHash, uint32 _paramId, address _who, address _where, bytes32 _what, uint256[] _how) internal view returns (bool)`

***

Parameters:

* `_paramsHash` - bytes32
* `_paramId` - uint32
* `_who` - address
* `_where` - address
* `_what` - bytes32
* `_how` - uint256\[]

Returns:&#x20;

* bool

#### **\_saveParams** <a href="#_saveparams" id="_saveparams"></a>

`function`` `**`_saveParams`**`(uint256[] _encodedParams) internal returns (bytes32)`

***

Parameters:

* `_encodedParams` - uint256\[]

Returns:&#x20;

* bytes32

#### **\_setPermission** <a href="#_setpermission" id="_setpermission"></a>

`function`` `**`_setPermission`**`(address _entity, address _app, bytes32 _role, bytes32 _paramsHash) internal`

***

Internal function called to actually save the permission.

Parameters:

* `_entity` - address
* `_app` - address
* `_role` - bytes32
* `_paramsHash` - bytes32

#### **\_setPermissionManager** <a href="#_setpermissionmanager" id="_setpermissionmanager"></a>

`function`` `**`_setPermissionManager`**`(address _newManager, address _app, bytes32 _role) internal`

***

Internal function that sets management.

Parameters:

* `_newManager` - address
* `_app` - address
* `_role` - bytes32

#### **burnPermissionManager** <a href="#burnpermissionmanager" id="burnpermissionmanager"></a>

`function`` `**`burnPermissionManager`**`(address _app, bytes32 _role) external`

***

Burn \`\_role\` in \`\_app\`, so no modification can be made to it (grant, revoke, permission manager).

Modifiers:

* [onlyPermissionManager](acl.md#\_createpermission)

Parameters:

* `_app` - Address of the app in which the permission is being burned
* `_role` - Identifier for the group of actions being burned

#### **checkOracle** <a href="#checkoracle" id="checkoracle"></a>

`function`` `**`checkOracle`**`(IACLOracle _oracleAddr, address _who, address _where, bytes32 _what, uint256[] _how) internal view returns (bool)`

***

Parameters:

* `_oracleAddr` - IACLOracle
* `_who` - address
* `_where` - address
* `_what` - bytes32
* `_how` - uint256\[]

Returns:&#x20;

* bool

#### **compare** <a href="#compare" id="compare"></a>

`function`` `**`compare`**`(uint256 _a, Op _op, uint256 _b) internal pure returns (bool)`

***

Parameters:

* `_a` - uint256
* `_op` - Op
* `_b` - uint256

Returns:&#x20;

* bool

#### **createBurnedPermission** <a href="#createburnedpermission" id="createburnedpermission"></a>

`function`` `**`createBurnedPermission`**`(address _app, bytes32 _role) external`

***

Burn non-existent \`\_role\` in \`\_app\`, so no modification can be made to it (grant, revoke, permission manager).

Modifiers:

* [authnoPermissionManager](acl.md#onlypermissionmanager)

Parameters:

* `_app` - Address of the app in which the permission is being burned
* `_role` - Identifier for the group of actions being burned

#### **createPermission** <a href="#createpermission" id="createpermission"></a>

`function`` `**`createPermission`**`(address _entity, address _app, bytes32 _role, address _manager) external`

***

Creates a permission that wasn't previously set and managed. If a created permission is removed it is possible to reset it with createPermission. This is the \*\*ONLY\*\* way to create permissions and set managers to permissions that don't have a manager. In terms of the ACL being initialized, this function implicitly protects all the other state-changing external functions, as they all require the sender to be a manager., Create a new permission granting \`\_entity\` the ability to perform actions requiring \`\_role\` on \`\_app\`, setting \`\_manager\` as the permission's manager.

Modifiers:

* [authnoPermissionManager](acl.md#onlypermissionmanager)

Parameters:

* `_entity` - Address of the whitelisted entity that will be able to perform the role
* `_app` - Address of the app in which the role will be allowed (requires app to depend on kernel for ACL)
* `_role` - Identifier for the group of actions in app given access to perform
* `_manager` - Address of the entity that will be able to grant and revoke the permission further.

#### **evalParams** <a href="#evalparams" id="evalparams"></a>

`function`` `**`evalParams`**`(bytes32 _paramsHash, address _who, address _where, bytes32 _what, uint256[] _how) public view returns (bool)`

***

Parameters:

* `_paramsHash` - bytes32
* `_who` - address
* `_where` - address
* `_what` - bytes32
* `_how` - uint256\[]

Returns:&#x20;

* bool

#### **getPermissionManager** <a href="#getpermissionmanager" id="getpermissionmanager"></a>

`function`` `**`getPermissionManager`**`(address _app, bytes32 _role) public view returns (address)`

***

Get manager for permission.

Parameters:

* `_app` - Address of the app
* `_role` - Identifier for a group of actions in app

Returns:&#x20;

* address of the manager for the permission

#### **getPermissionParam** <a href="#getpermissionparam" id="getpermissionparam"></a>

`function`` `**`getPermissionParam`**`(address _entity, address _app, bytes32 _role, uint _index) external view returns (uint8, uint8, uint240)`

***

Get parameter for permission.

Parameters:

* `_entity` - Address of the whitelisted entity that will be able to perform the role
* `_app` - Address of the app
* `_role` - Identifier for a group of actions in app
* `_index` - Index of parameter in the array

Returns:&#x20;

* Parameter (id, op, value)

#### **getPermissionParamsLength** <a href="#getpermissionparamslength" id="getpermissionparamslength"></a>

`function`` `**`getPermissionParamsLength`**`(address _entity, address _app, bytes32 _role) external view returns (uint)`

***

Get parameters for permission array length.

Parameters:

* `_entity` - Address of the whitelisted entity that will be able to perform the role
* `_app` - Address of the app
* `_role` - Identifier for a group of actions in app

Returns:&#x20;

* Length of the array

#### **grantPermission** <a href="#grantpermission" id="grantpermission"></a>

`function`` `**`grantPermission`**`(address _entity, address _app, bytes32 _role) external`

***

Grants permission if allowed. This requires \`msg.sender\` to be the permission manager, Grant \`\_entity\` the ability to perform actions requiring \`\_role\` on \`\_app\`.

Parameters:

* `_entity` - Address of the whitelisted entity that will be able to perform the role
* `_app` - Address of the app in which the role will be allowed (requires app to depend on kernel for ACL)
* `_role` - Identifier for the group of actions in app given access to perform

#### **grantPermissionP** <a href="#grantpermissionp" id="grantpermissionp"></a>

`function`` `**`grantPermissionP`**`(address _entity, address _app, bytes32 _role, uint256[] _params) public`

***

Grants a permission with parameters if allowed. This requires \`msg.sender\` to be the permission manager, Grant \`\_entity\` the ability to perform actions requiring \`\_role\` on \`\_app\`.



Modifiers:

* [onlyPermissionManager](acl.md#\_createpermission)

Parameters:

* `_entity` - Address of the whitelisted entity that will be able to perform the role
* `_app` - Address of the app in which the role will be allowed (requires app to depend on kernel for ACL)
* `_role` - Identifier for the group of actions in app given access to perform
* `_params` - Permission parameters

#### **hasPermission** <a href="#haspermission" id="haspermission"></a>

`function`` `**`hasPermission`**`(address _who, address _where, bytes32 _what, bytes _how) public view returns (bool)`

***

Function called by apps to check ACL on kernel or to check permission statu.

Parameters:

* `_who` - Sender of the original call
* `_where` - Identifier for a group of actions in app
* `_what` - bytes32
* `_how` - Permission parameters

Returns:&#x20;

* boolean indicating whether the ACL allows the role or not

#### **hasPermission** <a href="#haspermission" id="haspermission"></a>

`function`` `**`hasPermission`**`(address _who, address _where, bytes32 _what, uint256[] _how) public view returns (bool)`

***

Parameters:

* `_who` - address
* `_where` - address
* `_what` - bytes32
* `_how` - uint256\[]

Returns:&#x20;

* bool

#### **hasPermission** <a href="#haspermission" id="haspermission"></a>

`function`` `**`hasPermission`**`(address _who, address _where, bytes32 _what) public view returns (bool)`

***

Parameters:

* `_who` - address
* `_where` - address
* `_what` - bytes32

Returns:

* bool

#### **initialize**

`function`` `**`initialize`**`(address _permissionsCreator) public`

***

Initialize can only be called once. It saves the block number in which it was initialized., Initialize an ACL instance and set \`\_permissionsCreator\` as the entity that can create other permissions.



Modifiers:&#x20;

* [onlyInit](https://hack.aragon.org/docs/common\_Initializable.html#onlyInit)

Parameters:

* `_permissionsCreator` - Entity that will be given permission over createPermission

#### **permissionHash** <a href="#permissionhash" id="permissionhash"></a>

`function`` `**`permissionHash`**`(address _who, address _where, bytes32 _what) internal pure returns (bytes32)`

***

Parameters:

* `_who` - address
* `_where` - address
* `_what` - bytes32

Returns:

* bytes32

#### **removePermissionManager** <a href="#removepermissionmanager" id="removepermissionmanager"></a>

`function`` `**`removePermissionManager`**`(address _app, bytes32 _role) external`

***

Remove the manager of \`\_role\` in \`\_app\`.

Modifiers:

* [onlyPermissionManager](acl.md#\_createpermission)

Parameters:

* `_app` - Address of the app in which the permission is being unmanaged
* `_role` - Identifier for the group of actions being unmanaged

#### **revokePermission** <a href="#revokepermission" id="revokepermission"></a>

`function`` `**`revokePermission`**`(address _entity, address _app, bytes32 _role) external`

***

Revokes permission if allowed. This requires \`msg.sender\` to be the the permission manager, Revoke from \`\_entity\` the ability to perform actions requiring \`\_role\` on \`\_app\`.



Modifiers:

* [onlyPermissionManager](acl.md#\_createpermission)

Parameters:

* `_entity` - Address of the whitelisted entity to revoke access from
* `_app` - Address of the app in which the role will be revoked
* `_role` - Identifier for the group of actions in app being revoked

#### **roleHash** <a href="#rolehash" id="rolehash"></a>

`function`` `**`roleHash`**`(address _where, bytes32 _what) internal pure returns (bytes32)`

***

Parameters:

* `_where` - address
* `_what` - bytes32

Returns:

* bytes32

#### **setPermissionManager** <a href="#setpermissionmanager" id="setpermissionmanager"></a>

`function`` `**`setPermissionManager`**`(address _newManager, address _app, bytes32 _role) external`

***

Set \`\_newManager\` as the manager of \`\_role\` in \`\_app\`.

Modifiers:

* [onlyPermissionManager](acl.md#\_createpermission)

Parameters:

* `_newManager` - Address for the new manager
* `_app` - Address of the app in which the permission management is being transferred
* `_role` - Identifier for the group of actions being transferred
