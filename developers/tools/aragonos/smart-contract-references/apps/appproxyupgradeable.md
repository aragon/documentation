# AppProxyUpgradeable

## contract AppProxyUpgradeable

is [AppProxyBase](appproxybase.md)

Source: [contracts/apps/AppProxyUpgradeable.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/apps/AppProxyUpgradeable.sol)

## Index

* [fallback](appproxyupgradeable.md#fallback)
* [implementation](appproxyupgradeable.md#implementation)
* [proxyType](appproxyupgradeable.md#proxytype)

## Reference

### Functions

#### **fallback** <a href="#fallback" id="fallback"></a>

`function (IKernel _kernel, bytes32 _appId, bytes _initializePayload) public`

***

Initialize AppProxyUpgradeable (makes it an upgradeable Aragon app).

Modifiers:

Parameters:

* `_kernel` - Reference to organization kernel for the app
* `_appId` - Identifier for app
* `_initializePayload` - Payload for call to be made after setup to initialize

#### **implementation** <a href="#implementation" id="implementation"></a>

`function`` `**`implementation`**`() public view returns (address)`

***

ERC897, the address the proxy would delegate calls to.

Returns:

* address

#### **proxyType** <a href="#proxytype" id="proxytype"></a>

`function`` `**`proxyType`**`() public pure returns (uint256)`

***

ERC897, whether it is a forwarding (1) or an upgradeable (2) proxy.

Returns:

* uint256
