# AppStorage

## contract AppStorage

Source: [contracts/apps/AppStorage.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/apps/AppStorage.sol)

## Index

* [appId](appstorage.md#appid)
* [kernel](appstorage.md#kernel)
* [setAppId](appstorage.md#setappid)
* [setKernel](appstorage.md#setkernel)

## Reference

#### Functions

#### **appId** <a href="#appid" id="appid"></a>

`function`` `**`appId`**`() public view returns (bytes32)`

***

Returns:

* bytes32

#### **kernel** <a href="#kernel" id="kernel"></a>

`function`` `**`kernel`**`() public view returns (IKernel)`

***

Returns:

* IKernel

#### **setAppId** <a href="#setappid" id="setappid"></a>

`function`` `**`setAppId`**`(bytes32 _appId) internal`

***

Parameters:

* `_appId` - bytes32

#### **setKernel** <a href="#setkernel" id="setkernel"></a>

`function`` `**`setKernel`**`(IKernel _kernel) internal`

***

Parameters:

* `_kernel` - IKernel
