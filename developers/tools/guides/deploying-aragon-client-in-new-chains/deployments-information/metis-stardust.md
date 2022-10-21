# Metis stardust

OWNER=0x187a34c86aA6378333cE9033Aa34718D2CEdEd2C npx truffle exec --network stardust scripts/deploy-test-ens.js

Deploying ENSFactory...

\=========

\#ENSFactory:

Address: 0x741061b01d3a95a7734b594f1884b6c30e0fda96

Transaction hash: 0xb1ffc68cdb4c3f0209dcbe5aa65f53a2d23134fc30cf5d50f9f376176a1346ca

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-10-20T17:17:05.016Z

\=========

\====================

Deployed ENS: 0x843ddfab8406e752d03fa75dbb275070f368658d

OWNER=0x187a34c86aA6378333cE9033Aa34718D2CEdEd2C npx truffle exec --network stardust scripts/deploy-daofactory.js

\=========

\#Kernel:

Address: 0xb93f5be5900c2d5fbae8e4f99b46ffb2db52ee21

Transaction hash: 0x58740d9a7d0172cdbe4e7af9fbcd91a4a6c495928870fd4e7242cef3dd499e9b

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-10-20T17:17:05.017Z

\=========

\=========

\#ACL:

Address: 0xcd74cf89eb90f2abb444e2d1784ee473f338b76b

Transaction hash: 0x31a626fd14dc0f2b915befc41a9247e6549b7a34aaadd68b22d5f415f8da6956

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-10-20T17:17:04.987Z

\=========

\=========

\#EVMScriptRegistryFactory:

Address: 0x9277acd65b5dc0f85867dfd40f5488be8d47ad18

Transaction hash: 0x6370cb421288b02480568153fb83e54fe6107033c17b98196422e1dc4e3b18f2

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-10-20T17:17:05.016Z

\=========

\=========

\#DAOFactory:

Address: 0xc4ddbd0472c2688f5d278dafc02e66ee176c8de3

Transaction hash: 0xc8e3f509173349bc9ee920a022be0191bbf99c50ca13a37dce628333a5e8fdf5

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-10-20T17:17:05.015Z

\=========

OWNER=0x187a34c86aA6378333cE9033Aa34718D2CEdEd2C ENS=0x843ddfab8406e752d03fa75dbb275070f368658d  DAO\_FACTORY=0xc4ddbd0472c2688f5d278dafc02e66ee176c8de3 npx truffle exec --network stardust scripts/deploy-apm.js

Deploying APM...

Owner: 0x187a34c86aA6378333cE9033Aa34718D2CEdEd2C

ENS: 0x843ddfab8406e752d03fa75dbb275070f368658d

TLD: eth (0x93cdeb708b7545dc668eb9280176169d1c33cfd8ed6f04690a0bcc88a93fc4ae)

Label: aragonpm (0x1542111b4698ac085139692eae7c6efb632a4ae2779f8686da94511ebbbff594)

\=========

Deploying APM bases...

\=========

\#APMRegistry:

Address: 0x85138280659cc0ca3f40579e2c8f2713fbaa8878

Transaction hash: 0x4da3ca96a6d70c9e7c341d0d7cc6cab05f97bf02f69e60bd27420e8fb40c1539

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-10-20T17:17:04.997Z

\=========

\=========

\#Repo:

Address: 0xfec29d921a138f819f4921b3e75a35d716addc3d

Transaction hash: 0xae38a197ad08a545c9ca754a0371586be1b4f70f2af279d5da4c7cf4ecb13656

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-10-20T17:17:05.002Z

\=========

\=========

\#ENSSubdomainRegistrar:

Address: 0x308fcc274a5dc405feed1e4d10c1def265219bca

Transaction hash: 0xf26a0ef64380d786e15fcd81f9d45a0b8d4ff7f48205d5c18cd050e17f4864ca

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-10-20T17:17:05.009Z

\=========

Using provided DAOFactory (with EVMScripts): 0xc4ddbd0472c2688f5d278dafc02e66ee176c8de3

Deploying APMRegistryFactory...

\=========

\#APMRegistryFactory:

Address: 0x57e24f85ceacda3ef4f0fd04005589b88dc01a19

Transaction hash: 0xba1e15744e18e7070f49a47be6c1ec6a5dc7d18b1457f1df4c9d6cc43495eb46

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-10-20T17:17:05.013Z

\=========

Assigning ENS name (aragonpm.eth) to factory...

Creating subdomain and assigning it to APMRegistryFactory

Deploying APM...

\=========

\##APM:

Address: 0x711995dd005d26bf4d3c0c6fae880d5c2239e7d7

Transaction hash: 0x641a3925401248e844abba78e11756fee99801b22639cf781f9130da7826fd51

\=========

OWNER=0x187a34c86aA6378333cE9033Aa34718D2CEdEd2C ENS=0x843ddfab8406e752d03fa75dbb275070f368658d npx truffle exec --network stardust scripts/deploy-beta-aragonid.js

Deploying AragonID with ENS: 0x843ddfab8406e752d03fa75dbb275070f368658d and owner: 0x187a34c86aA6378333cE9033Aa34718D2CEdEd2C

\=========

\#FIFSResolvingRegistrar:

Address: 0x5ec029be8a0d322a54bb9c672cc0feb7ddd5c88f

Transaction hash: 0xa1772b74594ec2133ceea66711c27993353aa0dbf791a3f495560fce0bd1cf3c

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-10-15T18:03:05.738Z

\=========

assigning ENS name to AragonID

Creating subdomain and assigning it to AragonID

assigning owner name

\===========

Deployed AragonID: 0x5ec029be8a0d322a54bb9c672cc0feb7ddd5c88f
