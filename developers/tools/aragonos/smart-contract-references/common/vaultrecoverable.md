# VaultRecoverable

## contract VaultRecoverable

is [IVaultRecoverable](ivaultrecoverable.md), [EtherTokenConstant](ethertokenconstant.md), [IsContract](iscontract.md)

Source: [contracts/common/VaultRecoverable.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/common/VaultRecoverable.sol)

## Index

* [allowRecoverability](vaultrecoverable.md#allowrecoverability)
* [getRecoveryVault](vaultrecoverable.md#getrecoveryvault)
* [transferToVault](vaultrecoverable.md#transfertovault)

## Reference

### Functions

#### **allowRecoverability** <a href="#allowrecoverability" id="allowrecoverability"></a>

`function`` `**`allowRecoverability`**`(address token) public view returns (bool)`

***

By default deriving from AragonApp makes it recoverable.

Parameters:

* `token` - Token address that would be recovered

Returns:

* bool whether the app allows the recovery

#### **getRecoveryVault** <a href="#getrecoveryvault" id="getrecoveryvault"></a>

`abstract function`` `**`getRecoveryVault`**`() public view returns (address)`

***

Returns:

* address

#### **transferToVault** <a href="#transfertovault" id="transfertovault"></a>

`function`` `**`transferToVault`**`(address _token) external`

***

Send funds to recovery Vault. This contract should never receive funds, but in case it does, this function allows one to recover them.

Parameters

* `_token` - Token balance to be sent to recovery vault.
