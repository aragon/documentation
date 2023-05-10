# Repo

## contract Repo

is [AragonApp](../apps/aragonapp.md)

Source: [contracts/apm/Repo.sol](https://github.com/aragon/aragonOS/blob/v4.4.0/contracts/apm/Repo.sol)

## Index

* [NewVersion](repo.md#newversion)
* [getBySemanticVersion](repo.md#getbysemanticversion)
* [getByVersionId](repo.md#getbyversionid)
* [getLatest](repo.md#getlatest)
* [getLatestForContractAddress](repo.md#getlatestforcontractaddress)
* [getVersionsCount](repo.md#getversionscount)
* [initialize](repo.md#initialize)
* [isValidBump](repo.md#isvalidbump)
* [newVersion](repo.md#newversion-1)
* [semanticVersionHash](repo.md#semanticversionhash)

## Reference

### Events

#### **NewVersion** <a href="#newversion" id="newversion"></a>

`event`` `**`NewVersion`**`(uint256 versionId, uint16[] semanticVersion)`



Parameters:

* `versionId` - uint256
* `semanticVersion` - uint16\[]

### Functions

#### **getBySemanticVersion** <a href="#getbysemanticversion" id="getbysemanticversion"></a>

`function`` `**`getBySemanticVersion`**`(uint16[] _semanticVersion) public view returns (uint16[], address, bytes)ù`



Parameters:

* `_semanticVersion` - uint16\[]

Returns:

* uint16\[]
* address
* bytes

#### **getByVersionId** <a href="#getbyversionid" id="getbyversionid"></a>

`function`` `**`getByVersionId`**`(uint _versionId) public view returns (uint16[], address, bytes)`

***

Parameters:

* `_versionId` - uint

Returns:

* uint16\[]
* address
* bytes

#### **getLatest** <a href="#getlatest" id="getlatest"></a>

`function`` `**`getLatest`**`() public view returns (uint16[], address, bytes)`

***

Returns:

* uint16\[]
* address
* bytes

#### **getLatestForContractAddress** <a href="#getlatestforcontractaddress" id="getlatestforcontractaddress"></a>

`function`` `**`getLatestForContractAddress`**`(address _contractAddress) public view returns (uint16[], address, bytes)`

***

Parameters:

* `_contractAddress` - address

Returns:

* uint16\[]
* address
* bytes

#### **getVersionsCount** <a href="#getversionscount" id="getversionscount"></a>

`function`` `**`getVersionsCount`**`() public view returns (uint256)`

***

Returns:

* uint256

#### **initialize** <a href="#initialize" id="initialize"></a>

`function`` `**`initialize`**`() public`

***

Initialize can only be called once. It saves the block number in which it was initialized., Initialize this Repo.

Modifiers:

* [onlyInit](../common/initializable.md#getinitializationblock)

#### **isValidBump** <a href="#isvalidbump" id="isvalidbump"></a>

`function`` `**`isValidBump`**`(uint16[] _oldVersion, uint16[] _newVersion) public pure returns (bool)`

***

Parameters:

* `_oldVersion` - uint16\[]
* `_newVersion` - uint16\[]

Returns:

* bool

#### **newVersion** <a href="#newversion" id="newversion"></a>

`function`` `**`newVersion`**`(uint16[] _newSemanticVersion, address _contractAddress, bytes _contentURI) public`

***

Create new version with contract \`\_contractAddress\` and content \`@fromHex(\_contentURI)\`.

Modifiers:

* [auth](../apps/aragonapp.md#authp)

Parameters:

* `_newSemanticVersion` - Semantic version for new repo version
* `_contractAddress` - address for smart contract logic for version (if set to 0, it uses last versions' contractAddress)
* `_contentURI` - External URI for fetching new version's content

#### **semanticVersionHash** <a href="#semanticversionhash" id="semanticversionhash"></a>

`function`` `**`semanticVersionHash`**`(uint16[] version) internal pure returns (bytes32)`

***

Parameters:

* `version` - uint16\[]

Returns:

* bytes32
