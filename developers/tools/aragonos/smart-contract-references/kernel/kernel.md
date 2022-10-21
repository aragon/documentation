# Kernel

## contract Kernel

is [IKernel](ikernel.md), [KernelStorage](kernelstorage.md),[ KernelAppIds](kernelappids.md), [KernelNamespaceConstants](kernelnamespaceconstants.md), [Petrifiable](../common/petrifiable.md), [IsContract](../common/iscontract.md), [VaultRecoverable](../common/vaultrecoverable.md), [AppProxyFactory](../factory/appproxyfactory.md), [ACLSyntaxSugar](../acl/aclsyntaxsugar.md)

Source: [contracts/kernel/Kernel.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/kernel/Kernel.sol)

## Index

* [APP\_ADDR\_NAMESPACE](kernel.md#app\_addr\_namespace)
* [APP\_BASES\_NAMESPACE](kernel.md#app\_bases\_namespace)
* [CORE\_NAMESPACE](kernel.md#core\_namespace)
* [DEFAULT\_ACL\_APP\_ID](kernel.md#default\_acl\_app\_id)
* [KERNEL\_APP\_ID](kernel.md#kernel\_app\_id)
* [\_setApp](kernel.md#\_setapp)
* [\_setAppIfNew](kernel.md#\_setappifnew)
* [acl](kernel.md#acl)
* [auth](kernel.md#auth)
* [fallback](kernel.md#fallback)
* [getApp](kernel.md#getapp)
* [getRecoveryVault](kernel.md#getrecoveryvault)
* [hasPermission](kernel.md#haspermission)
* [initialize](kernel.md#initialize)
* [newAppInstance](kernel.md#newappinstance)
* [newAppInstance](kernel.md#newappinstance-1)
* [newPinnedAppInstance](kernel.md#newpinnedappinstance)
* [newPinnedAppInstance](kernel.md#newpinnedappinstance-1)
* [setApp](kernel.md#setapp)
* [setRecoveryVaultAppId](kernel.md#setrecoveryvaultappid)

## Reference

### Modifiers

#### **auth** <a href="#auth" id="auth"></a>

`modifier`` `**`auth`**`(bytes32 _role, uint256[] _params)`

***

Parameters:

* `_role` - bytes32
* `_params` - uint256\[]

### Functions

#### **APP\_ADDR\_NAMESPACE** <a href="#app_addr_namespace" id="app_addr_namespace"></a>

`function`` `**`APP_ADDR_NAMESPACE`**`() external pure returns (bytes32)`

***

Returns:

* bytes32

#### **APP\_BASES\_NAMESPACE** <a href="#app_bases_namespace" id="app_bases_namespace"></a>

`function`` `**`APP_BASES_NAMESPACE`**`() external pure returns (bytes32)`

***

Returns:

* bytes32

#### **CORE\_NAMESPACE** <a href="#core_namespace" id="core_namespace"></a>

`function`` `**`CORE_NAMESPACE`**`() external pure returns (bytes32)`

***

Returns:

* bytes32

#### **DEFAULT\_ACL\_APP\_ID** <a href="#default_acl_app_id" id="default_acl_app_id"></a>

`function`` `**`DEFAULT_ACL_APP_ID`**`() external pure returns (bytes32)`

***

Returns:

* bytes32

#### **KERNEL\_APP\_ID** <a href="#kernel_app_id" id="kernel_app_id"></a>

`function`` `**`KERNEL_APP_ID`**`() external pure returns (bytes32)`

***

Returns:

* bytes32

#### **\_setApp** <a href="#_setapp" id="_setapp"></a>

`function`` `**`_setApp`**`(bytes32 _namespace, bytes32 _appId, address _app) internal`

***

Parameters:

* `_namespace` - bytes32
* `_appId` - bytes32
* `_app` - address

#### **\_setAppIfNew** <a href="#_setappifnew" id="_setappifnew"></a>

`function`` `**`_setAppIfNew`**`(bytes32 _namespace, bytes32 _appId, address _app) internal`

***

Parameters:

* `_namespace` - bytes32
* `_appId` - bytes32
* `_app` - address

#### **acl** <a href="#acl" id="acl"></a>

`function`` `**`acl`**`() public view returns (IACL)`

***

Get the installed ACL app.

Returns:

* ACL app

#### **fallback** <a href="#fallback" id="fallback"></a>

`function (bool _shouldPetrify) public`

***

Constructor that allows the deployer to choose if the base instance should be petrified immediately.

Parameters:

* `_shouldPetrify` - Immediately petrify this instance so that it can never be initialized

#### **getApp** <a href="#getapp" id="getapp"></a>

`function`` `**`getApp`**`(bytes32 _namespace, bytes32 _appId) public view returns (address)`

***

Get the address of an app instance or base implementation.

Parameters:

* `_namespace` - App namespace to use
* `_appId` - Identifier for appReturns:Address of the app

#### **getRecoveryVault** <a href="#getrecoveryvault" id="getrecoveryvault"></a>

`function`` `**`getRecoveryVault`**`() public view returns (address)`

***

Get the address of the recovery Vault instance (to recover funds).

Returns:

* Address of the Vault

#### **hasPermission** <a href="#haspermission" id="haspermission"></a>

`function`` `**`hasPermission`**`(address _who, address _where, bytes32 _what, bytes _how) public view returns (bool)`

***

Function called by apps to check ACL on kernel or to check permission status.

Parameters:

* `_who` - Sender of the original call
* `_where` - Address of the app
* `_what` - Identifier for a group of actions in app
* `_how` - Extra data for ACL auth

Returns:

* Boolean indicating whether the ACL allows the role or not. Always returns false if the kernel hasn't been initialized yet.

#### **initialize** <a href="#initialize" id="initialize"></a>

`function`` `**`initialize`**`(IACL _baseAcl, address _permissionsCreator) public`

***

Initialize can only be called once. It saves the block number in which it was initialized., Initialize this kernel instance along with its ACL and set \`\_permissionsCreator\` as the entity that can create other permissions.

Modifiers:

* [onlyInit](../common/initializable.md#getinitializationblock)

Parameters:

* `_baseAcl` - Address of base ACL app
* `_permissionsCreator` - Entity that will be given permission over createPermission

#### **newAppInstance** <a href="#newappinstance" id="newappinstance"></a>

`function`` `**`newAppInstance`**`(bytes32 _appId, address _appBase) public returns (ERCProxy)`

***

Create a new instance of an app linked to this kernel, Create a new upgradeable instance of \`\_appId\` app linked to the Kernel, setting its code to \`\_appBase\`.

Modifiers:

* [auth](kernel.md#app\_addr\_namespace)

Parameters:

* `_appId` - Identifier for app
* `_appBase` - Address of the app's base implementation

Returns:

* AppProxy instance

#### **newAppInstance** <a href="#newappinstance" id="newappinstance"></a>

`function`` `**`newAppInstance`**`(bytes32 _appId, address _appBase, bytes _initializePayload, bool _setDefault) public returns (ERCProxy)`

***

Create a new instance of an app linked to this kernel and set its base implementation if it was not already set, Create a new upgradeable instance of \`\_appId\` app linked to the Kernel, setting its code to \`\_appBase\`. \`\_setDefault ? 'Also sets it as the default app instance.':''\`.

Modifiers:

* [auth](kernel.md#app\_addr\_namespace)

Parameters:

* `_appId` - Identifier for app
* `_appBase` - Address of the app's base implementation
* `_initializePayload` - Payload for call made by the proxy during its construction to initialize
* `_setDefault` - Whether the app proxy app is the default one. Useful when the Kernel needs to know of an instance of a particular app, like Vault for escape hatch mechanism.

Returns:

* AppProxy instance

#### **newPinnedAppInstance** <a href="#newpinnedappinstance" id="newpinnedappinstance"></a>

`function`` `**`newPinnedAppInstance`**`(bytes32 _appId, address _appBase) public returns (ERCProxy)`

***

Create a new pinned instance of an app linked to this kernel, Create a new non-upgradeable instance of \`\_appId\` app linked to the Kernel, setting its code to \`\_appBase\`.

Modifiers:

* [auth](kernel.md#app\_addr\_namespace)

Parameters:

* `_appId` - Identifier for app
* `_appBase` - Address of the app's base implementation

Returns:

* AppProxy instance

#### **newPinnedAppInstance** <a href="#newpinnedappinstance" id="newpinnedappinstance"></a>

`function`` `**`newPinnedAppInstance`**`(bytes32 _appId, address _appBase, bytes _initializePayload, bool _setDefault) public returns (ERCProxy)`

***

Create a new pinned instance of an app linked to this kernel and set its base implementation if it was not already set, Create a new non-upgradeable instance of \`\_appId\` app linked to the Kernel, setting its code to \`\_appBase\`. \`\_setDefault ? 'Also sets it as the default app instance.':''\`.

Modifiers:

* [auth](kernel.md#app\_addr\_namespace)

Parameters:

* `_appId` - Identifier for app
* `_appBase` - Address of the app's base implementation
* `_initializePayload` - Payload for call made by the proxy during its construction to initialize
* `_setDefault` - Whether the app proxy app is the default one. Useful when the Kernel needs to know of an instance of a particular app, like Vault for escape hatch mechanism.

Returns:

* AppProxy instance

#### **setApp** <a href="#setapp" id="setapp"></a>

`function`` `**`setApp`**`(bytes32 _namespace, bytes32 _appId, address _app) public`

***

Set the resolving address of an app instance or base implementation, Set the resolving address of \`\_appId\` in namespace \`\_namespace\` to \`\_app\`.

Modifiers:

* [auth](kernel.md#app\_addr\_namespace)

Parameters:

* `_namespace` - App namespace to use
* `_appId` - Identifier for app
* `_app` - Address of the app instance or base implementation

Returns:

* ID of app

#### **setRecoveryVaultAppId** <a href="#setrecoveryvaultappid" id="setrecoveryvaultappid"></a>

`function`` `**`setRecoveryVaultAppId`**`(bytes32 _recoveryVaultAppId) public`

***

Set the default vault id for the escape hatch mechanism.

Modifiers:

* [auth](kernel.md#app\_addr\_namespace)

Parameters:

* `_recoveryVaultAppId` - Identifier of the recovery vault app
