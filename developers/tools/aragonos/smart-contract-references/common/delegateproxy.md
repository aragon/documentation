# DelegateProxy

## contract DelegateProxy

is [ERCProxy](../kernel/kernelproxy.md#proxytype), [IsContract](iscontract.md)

Source: [contracts/common/DelegateProxy.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/common/DelegateProxy.sol)

## Index

* [delegatedFwd](delegateproxy.md#delegatedfwd)

## Reference

### Functions

#### **delegatedFwd** <a href="#delegatedfwd" id="delegatedfwd"></a>

`function`` `**`delegatedFwd`**`(address _dst, bytes _calldata) internal`

***

Performs a delegatecall and returns whatever the delegatecall returned (entire context execution will return!).

Parameters:

* `_dst` - Destination address to perform the delegatecall
* `_calldata` - Calldata for the delegatecall
