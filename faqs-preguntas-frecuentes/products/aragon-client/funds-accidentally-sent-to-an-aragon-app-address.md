# Fondos enviados accidentalmente a una dirección de la app de Aragon

Si accidentalmente envió tokens a la dirección de una app instalada en una organización de Aragon, puede recuperar los tokens y enviarlos al Vault (Bóveda) de la organización siguiendo estos pasos:&#x20;

1. [Instale el aragonCLI](https://hack.aragon.org/docs/cli-intro.html) (disponible actualmente solo en inglés) que es una interfaz de línea de comandos para interactuar con las organizaciones de Aragon.&#x20;
2. Ejecute `aragon ipfs` en su Terminal para proporcionar a aragonCLI una forma de acceder a los datos (por ejemplo, ABIs) de las organizaciones de Aragon.&#x20;
3. [Establezca una clave privada para que aragonCLI la utilice ](https://hack.aragon.org/docs/guides-faq#set-a-private-key)(disponible actualmente solo en inglés), luego envía algo de éter a la dirección de esta clave privada para pagar la gasolina.&#x20;
4. Envía el siguiente comando de transacción desde la aragonCLI, sustituyendo cada "dirección" por la correspondiente a su transacción atascada:

```powershell
dao exec OrganizationAddress AppAddress recoverToVault TokenContractAddress --environment aragon:mainnet
```

Donde la `OrganizationAddress` \_\_  es la dirección de la organización que alberga los fondos atascados, la `AppAddress` es la dirección de la app a la que enviaste los fondos atascados, y la `TokenContractAddress` es la dirección del contrato de tokens para el token que enviaste.&#x20;

Por ejemplo, si envió [Dai](https://etherscan.io/token/0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359) a la dirección de la app de Finanzas de la organización [genesis.aragonid.eth](https://mainnet.aragon.org/#/genesis/settings), entonces el comando de transacción que enviaría desde la aragonCLI sería

```
dao exec 0x8A83D4bCE45b4C4F751f76cf565953D1E4A3BF0a 0x98516C82Bda8B3dE6E2670B718848949Ae6a4643 recoverToVault 0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359 --environment aragon:mainnet
```

Gracias a Chris Hobcroft por documentar estos pasos en este [comentario de GitHub ](https://github.com/ethereum-cat-herders/funding/issues/2#issuecomment-477174751)(disponible actualmente solo en inglés).
