# AppProxyBase

## contract AppProxyBase

is [AppStorage](appstorage.md), [DepositableDelegateProxy](../common/depositabledelegateproxy.md), [KernelNamespaceConstants](../kernel/kernelnamespaceconstants.md)

Source: [contracts/apps/AppProxyBase.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/apps/AppProxyBase.sol)

## Index

* [fallback](appproxybase.md#fallback)
* [getAppBase](appproxybase.md#getappbase)

## Reference

### Functions

#### **fallback** <a href="#fallback" id="fallback"></a>

`function (IKernel _kernel, bytes32 _appId, bytes _initializePayload) public`

***

Initialize AppProxy.

Parameters:

* `_kernel` - Reference to organization kernel for the app
* `_appId` - Identifier for app
* `_initializePayload` - Payload for call to be made after setup to initialize

#### **getAppBase** <a href="#getappbase" id="getappbase"></a>

`function`` `**`getAppBase`**`(bytes32 _appId) internal view returns (address)`

***

Parameters:

* `_appId` - bytes32

Returns:

* address

