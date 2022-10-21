# KernelProxy

## contract KernelProxy

is [IKernelEvents,](ikernelevents.md) [KernelStorage,](kernelstorage.md) [KernelAppIds](kernelappids.md), [KernelNamespaceConstants](kernelnamespaceconstants.md), [IsContract](../common/iscontract.md), [DepositableDelegateProxy](../common/depositabledelegateproxy.md)

Source: [contracts/kernel/KernelProxy.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/kernel/KernelProxy.sol)

## Index

* [fallback](kernelproxy.md#fallback)
* [implementation](kernelproxy.md#implementation)
* [proxyType](kernelproxy.md#proxytype)

## Reference

### Functions

#### **fallback** <a href="#fallback" id="fallback"></a>

`function (IKernel _kernelImpl) public`

***

KernelProxy is a proxy contract to a kernel implementation. The implementation can update the reference, which effectively upgrades the contract.

Parameters:

* `_kernelImpl` - Address of the contract used as implementation for kernel

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
