# IVaultRecoverable

## interface IVaultRecoverable

Source: [contracts/common/IVaultRecoverable.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/common/IVaultRecoverable.sol)

## Index

* [RecoverToVault](ivaultrecoverable.md#recovertovault)
* [allowRecoverability](ivaultrecoverable.md#allowrecoverability)
* [getRecoveryVault](ivaultrecoverable.md#getrecoveryvault)
* [transferToVault](ivaultrecoverable.md#transfertovault)

## Reference

### Events

#### **RecoverToVault** <a href="#recovertovault" id="recovertovault"></a>

`event`` `**`RecoverToVault`**`(address vault, address token, uint256 amount)`

***

Parameters:

* `vault` - address
* `token` - address
* `amount` - uint256

### Functions

#### **allowRecoverability** <a href="#allowrecoverability" id="allowrecoverability"></a>

`abstract function`` `**`allowRecoverability`**`(address token) external view returns (bool)`

***

Parameters:

* `token` - address

Returns:

* bool

#### **getRecoveryVault** <a href="#getrecoveryvault" id="getrecoveryvault"></a>

`abstract function`` `**`getRecoveryVault`**`() external view returns (address)`

***

Returns:

* address

#### **transferToVault** <a href="#transfertovault" id="transfertovault"></a>

`abstract function`` `**`transferToVault`**`(address token) external`

***

Parameters:

* `token` - address
