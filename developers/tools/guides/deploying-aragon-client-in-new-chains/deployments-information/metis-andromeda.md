# Metis Andromeda

OWNER=0x187a34c86aA6378333cE9033Aa34718D2CEdEd2C npx truffle exec --network andromeda scripts/deploy-test-ens.js

Deploying ENSFactory...

\=========

\#ENSFactory:

Address: 0x741061b01d3a95a7734b594f1884b6c30e0fda96

Transaction hash: 0xd64e08455a7cbfce808032d4e28df334bb86124350358b4930070d05de037176

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-10-20T17:17:05.016Z

\=========

\====================

Deployed ENS: 0x843ddfab8406e752d03fa75dbb275070f368658d

OWNER=0x187a34c86aA6378333cE9033Aa34718D2CEdEd2C npx truffle exec --network andromeda scripts/deploy-daofactory.js

\=========

\#Kernel:

Address: 0x308fcc274a5dc405feed1e4d10c1def265219bca

Transaction hash: 0x11135c084fb82925e4eb5817da382d3dff7eeef576af7bd4a3ed40ab2b9e9e9c

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-12-19T19:39:04.305Z

\=========

\=========

\#ACL:

Address: 0x57e24f85ceacda3ef4f0fd04005589b88dc01a19

Transaction hash: 0x6399494122a4a16e59f3771510841f74f4014f7ba830c889b4803622d1822fbd

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-12-19T19:39:04.274Z

\=========

\=========

\#EVMScriptRegistryFactory:

Address: 0xca834b3f404c97273f34e108029eed776144d324

Transaction hash: 0x97be495d34ccfce8bf07c29810bc0f0d07c827a3681a4ab3193b0cfc5417727f

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-12-19T19:39:04.304Z

\=========

\=========

\#DAOFactory:

Address: 0x6d4fb6ff01a172774f42789fcfcdd84e68c28494

Transaction hash: 0xd462df441d7d369a7bd8df280ce6a1bb0113a36223a0bf797642b6a125851793

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-12-19T19:39:04.303Z

\=========

OWNER=0x187a34c86aA6378333cE9033Aa34718D2CEdEd2C ENS=0x843ddfab8406e752d03fa75dbb275070f368658d  DAO\_FACTORY=0x6d4fb6ff01a172774f42789fcfcdd84e68c28494 npx truffle exec --network andromeda scripts/deploy-apm.js

Deploying APM...

Owner: 0x187a34c86aA6378333cE9033Aa34718D2CEdEd2C

ENS: 0x843ddfab8406e752d03fa75dbb275070f368658d

TLD: eth (0x93cdeb708b7545dc668eb9280176169d1c33cfd8ed6f04690a0bcc88a93fc4ae)

Label: aragonpm (0x1542111b4698ac085139692eae7c6efb632a4ae2779f8686da94511ebbbff594)

\=========

Deploying APM bases...

\=========

\##APMRegistry:

Address: 0xbe6eac1ba0b2d20aea9e7924efee8e72d6193246

Transaction hash: 0xdd501ce538632c300763644c1975a65eebefbfda123e16e63ff7db4b7bf9c3c1

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-12-19T19:39:04.286Z

\=========

\=========

\#Repo:

Address: 0x57bf333951967a0cc0afcd58fc7959ca0eae6905

Transaction hash: 0x7834d4c6197265e4fe43a056f4daf1eebcc13ba1b968dcd14bba5d8c08bb97b0

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-12-19T19:39:04.288Z

\=========

\=========

\#ENSSubdomainRegistrar:

Address: 0x74b3b3504b5d6d1c6247009c9b1e3d8cff7bd445

Transaction hash: 0x5560b9884317a9a829a5e6fccc0e16c6c8ce5627fa5464d75480e11ae70a7199

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-12-19T19:39:04.296Z

\=========

Using provided DAOFactory (with EVMScripts): 0x6d4fb6ff01a172774f42789fcfcdd84e68c28494

Deploying APMRegistryFactory...

\=========

\#APMRegistryFactory:

Address: 0x6115b7f05ccef2d883ab64c88ba7e4bd1b877215

Transaction hash: 0xc087ce947b6925e722b169ae4a42ec9a0f5a8161d0087f7e0e68aba9a819a38f

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-12-19T19:39:04.300Z

\=========

Assigning ENS name (aragonpm.eth) to factory...

Creating subdomain and assigning it to APMRegistryFactory

Deploying APM...

\=========

\#APM:

Address: 0xe86688709aea59508a8de5824203148ae826c8a0

Transaction hash: 0x31d28ea2a4506e599bbb607a22b562cdcc82c3c9e13c8986b3d0cc067cf0a10e

\=========

OWNER=0x187a34c86aA6378333cE9033Aa34718D2CEdEd2C ENS=0x843ddfab8406e752d03fa75dbb275070f368658d npx truffle exec --network andromeda scripts/deploy-beta-aragonid.js

Deploying AragonID with ENS: 0x843ddfab8406e752d03fa75dbb275070f368658d and owner: 0x187a34c86aA6378333cE9033Aa34718D2CEdEd2C

\=========

\#FIFSResolvingRegistrar:

Address: 0xb5146fd572c669abc353902e43f47fda4609e38a

Transaction hash: 0x9c0efade2a6d698d2a9c7160966194bea4cfc0417cb301fca470bd028792409f

Compiler: solc@0.4.24+commit.e67f0147.Emscripten.clang (Optimizer: 10000 runs)

Compiled at: 2021-10-15T18:03:05.738Z

\=========

assigning ENS name to AragonID

Creating subdomain and assigning it to AragonID

assigning owner name

\===========

Deployed AragonID: 0xb5146fd572c669abc353902e43f47fda4609e38a
