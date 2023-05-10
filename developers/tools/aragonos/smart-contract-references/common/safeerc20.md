# SafeERC20

## library SafeERC20

Source: [contracts/common/SafeERC20.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/common/SafeERC20.sol)

## Index

* [safeApprove](safeerc20.md#safeapprove)
* [safeTransfer](safeerc20.md#safetransfer)
* [safeTransferFrom](safeerc20.md#safetransferfrom)
* [staticAllowance](safeerc20.md#staticallowance)
* [staticBalanceOf](safeerc20.md#staticbalanceof)
* [staticTotalSupply](safeerc20.md#statictotalsupply)

## Reference

### Functions

#### **safeApprove** <a href="#safeapprove" id="safeapprove"></a>

`function`` `**`safeApprove`**`(ERC20 _token, address _spender, uint256 _amount) internal returns (bool)`

***

Same as a standards-compliant ERC20.approve() that never reverts (returns false). Note that this makes an external call to the token.



Parameters:

* `_token` - ERC20
* `_spender` - address
* `_amount` - uint256

Returns:

* bool

#### **safeTransfer** <a href="#safetransfer" id="safetransfer"></a>

`function`` `**`safeTransfer`**`(ERC20 _token, address _to, uint256 _amount) internal returns (bool)`

***

Same as a standards-compliant ERC20.transfer() that never reverts (returns false). Note that this makes an external call to the token.

Parameters:

* `_token` - ERC20
* `_to` - address
* `_amount` - uint256

Returns:

* bool

#### **safeTransferFrom** <a href="#safetransferfrom" id="safetransferfrom"></a>

`function`` `**`safeTransferFrom`**`(ERC20 _token, address _from, address _to, uint256 _amount) internal returns (bool)`

***

Same as a standards-compliant ERC20.transferFrom() that never reverts (returns false). Note that this makes an external call to the token.

Parameters:

* `_token` - ERC20
* `_from` - address
* `_to` - address
* `_amount` - uint256

Returns:

* bool

#### **staticAllowance** <a href="#staticallowance" id="staticallowance"></a>

`function`` `**`staticAllowance`**`(ERC20 _token, address _owner, address _spender) internal view returns (uint256)`

***

Static call into ERC20.allowance(). Reverts if the call fails for some reason (should never fail).

Parameters:

* `_token` - ERC20
* `_owner` - address
* `_spender` - address

Returns:

* uint256

#### **staticBalanceOf** <a href="#staticbalanceof" id="staticbalanceof"></a>

`function`` `**`staticBalanceOf`**`(ERC20 _token, address _owner) internal view returns (uint256)`

***

Static call into ERC20.balanceOf(). Reverts if the call fails for some reason (should never fail).

Parameters:

* `_token` - ERC20
* `_owner` - address

Returns:

* uint256

#### **staticTotalSupply** <a href="#statictotalsupply" id="statictotalsupply"></a>

`function`` `**`staticTotalSupply`**`(ERC20 _token) internal view returns (uint256)`

***

Static call into ERC20.totalSupply(). Reverts if the call fails for some reason (should never fail).

Parameters:

* `_token` - ERC20

Returns:

* uint256
