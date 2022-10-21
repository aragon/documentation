# AppProxyPinned

## contract AppProxyPinned

is [IsContract](../common/iscontract.md), [AppProxyBase](appproxybase.md)

Source: [contracts/apps/AppProxyPinned.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/apps/AppProxyPinned.sol)

## Index

* [fallback](appproxypinned.md#fallback)
* [implementation](appproxypinned.md#implementation)
* [pinnedCode](appproxypinned.md#pinnedcode)
* [proxyType](appproxypinned.md#proxytype)
* [setPinnedCode](appproxypinned.md#setpinnedcode)

## Reference

### Functions

#### **fallback** <a href="#fallback" id="fallback"></a>

`function (IKernel _kernel, bytes32 _appId, bytes _initializePayload) public`

***

Initialize AppProxyPinned (makes it an un-upgradeable Aragon app).

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

#### **pinnedCode** <a href="#pinnedcode" id="pinnedcode"></a>

`function`` `**`pinnedCode`**`() internal view returns (address)`

***

Returns:

* address

#### **proxyType** <a href="#proxytype" id="proxytype"></a>

`function`` `**`proxyType`**`() public pure returns (uint256)`

***

ERC897, whether it is a forwarding (1) or an upgradeable (2) proxy.

Returns:

* uint256

#### **setPinnedCode** <a href="#setpinnedcode" id="setpinnedcode"></a>

`function`` `**`setPinnedCode`**`(address _pinnedCode) internal`

***

Parameters:

* `_pinnedCode` - address
