# AppProxyFactory

## contract AppProxyFactory

Source: [contracts/factory/AppProxyFactory.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/factory/AppProxyFactory.sol)

## Index

* [NewAppProxy](appproxyfactory.md#newappproxy)
* [newAppProxy](appproxyfactory.md#newappproxy-1)
* [newAppProxy](appproxyfactory.md#newappproxy-2)
* [newAppProxyPinned](appproxyfactory.md#newappproxypinned)
* [newAppProxyPinned](appproxyfactory.md#newappproxypinned-1)

## Reference

### Events

#### **NewAppProxy** <a href="#newappproxy" id="newappproxy"></a>

`event`` `**`NewAppProxy`**`(address proxy, bool isUpgradeable, bytes32 appId)`

***

Parameters:

* `proxy` - address
* `isUpgradeable` - bool
* `appId` - bytes32

### Functions

#### **newAppProxy** <a href="#newappproxy" id="newappproxy"></a>

`function`` `**`newAppProxy`**`(IKernel _kernel, bytes32 _appId) public returns (AppProxyUpgradeable)`

***

Create a new upgradeable app instance on \`\_kernel\` with identifier \`\_appId\`.

Parameters:

* `_kernel` - App's Kernel reference
* `_appId` - Identifier for app

Returns:

* AppProxyUpgradeable

#### **newAppProxy** <a href="#newappproxy" id="newappproxy"></a>

`function`` `**`newAppProxy`**`(IKernel _kernel, bytes32 _appId, bytes _initializePayload) public returns (AppProxyUpgradeable)`

***

Create a new upgradeable app instance on \`\_kernel\` with identifier \`\_appId\` and initialization payload \`\_initializePayload\`.

Parameters:

* `_kernel` - App's Kernel reference
* `_appId` - Identifier for app
* `_initializePayload` - bytes

Returns:

* AppProxyUpgradeable

#### **newAppProxyPinned** <a href="#newappproxypinned" id="newappproxypinned"></a>

`function`` `**`newAppProxyPinned`**`(IKernel _kernel, bytes32 _appId) public returns (AppProxyPinned)`

***

Create a new pinned app instance on \`\_kernel\` with identifier \`\_appId\`.

Parameters:

* `_kernel` - App's Kernel reference
* `_appId` - Identifier for app

Returns:

* AppProxyPinned

#### **newAppProxyPinned** <a href="#newappproxypinned" id="newappproxypinned"></a>

`function`` `**`newAppProxyPinned`**`(IKernel _kernel, bytes32 _appId, bytes _initializePayload) public returns (AppProxyPinned)`

***

Create a new pinned app instance on \`\_kernel\` with identifier \`\_appId\` and initialization payload \`\_initializePayload\`.

Parameters:

* `_kernel` - App's Kernel reference
* `_appId` - Identifier for app
* `_initializePayload` - Proxy initialization payload

Returns:

* AppProxyPinned
