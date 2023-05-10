# AragonApp

## contract AragonApp

is [AppStorage](appstorage.md), [Autopetrified](../common/autopetrified.md), [VaultRecoverable](../common/vaultrecoverable.md), [ReentrancyGuard](../common/reentrancyguard.md), [EVMScriptRunner](../evmscript/evmscriptrunner.md), [ACLSyntaxSugar](../acl/aclsyntaxsugar.md)

Source: [contracts/apps/AragonApp.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/apps/AragonApp.sol)

## Index

* [auth](aragonapp.md#auth)
* [authP](aragonapp.md#authp)
* [canPerform](aragonapp.md#canperform)
* [getRecoveryVault](aragonapp.md#getrecoveryvault)

## Reference

### Modifiers

#### **auth** <a href="#auth" id="auth"></a>

`modifier`` `**`auth`**`(bytes32 _role)`

***

Parameters:

* `_role` - bytes32

#### **authP** <a href="#authp" id="authp"></a>

`modifier`` `**`authP`**`(bytes32 _role, uint256[] _params)`

***

Parameters:

* `_role` - bytes32
* `_params` - uint256\[]

### Functions

#### **canPerform** <a href="#canperform" id="canperform"></a>

`function`` `**`canPerform`**`(address _sender, bytes32 _role, uint256[] _params) public view returns (bool)`

***

Check whether an action can be performed by a sender for a particular role on this app.

Parameters:

* `_sender` - Sender of the call
* `_role` - Role on this app
* `_params` - Permission params for the role

Returns:

* Boolean indicating whether the sender has the permissions to perform the action. Always returns false if the app hasn't been initialized yet.

#### **getRecoveryVault** <a href="#getrecoveryvault" id="getrecoveryvault"></a>

`function`` `**`getRecoveryVault`**`() public view returns (address)`

***

Get the recovery vault for the app.

Returns:

* Recovery vault address for the app
