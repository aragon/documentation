# Fonds envoyés accidentellement à une adresse d'application Aragon

Si vous avez accidentellement envoyé des jetons à l'adresse d'une application installée dans une organisation Aragon, vous pouvez récupérer les jetons et les envoyer à la chambre forte de l'organisation en suivant ces étapes :

1. [Installez l'aragonCLI](https://hack.aragon.org/docs/cli-intro.html) (en anglais) qui est une interface en ligne de commande pour interagir avec les organisations Aragon.
2. Exécutez `aragon ipfs` dans votre Terminal afin de fournir à aragonCLI un moyen d'accéder aux données (e.g. ABIs) des organisations Aragon.
3. [Définessez une clé privée pour aragonCLI á utiliser](https://hack.aragon.org/docs/guides-faq#set-a-private-key) (en anglais), puis envoyez de l'éther à l'adresse de cette clé privée pour payer le gaz.
4. Envoyez la commande de transaction suivante depuis l'aragonCLI, en remplaçant chaque "adresse" par l'adresse correspondante pertinente pour votre transaction bloquée :

```powershell
dao exec OrganizationAddress AppAddress recoverToVault TokenContractAddress --environment aragon:mainnet
```

Où `OrganizationAddress` \_\_est l'adresse de l'organisation qui abrite les fonds bloqués, `AppAddress`est l'adresse de l'application à laquelle vous avez envoyé les fonds bloqués, et le `TokenContractAddress` est l'adresse du contrat de jeton pour le jeton que vous avez envoyé.

Par exemple, si vous avez envoyé [Dai](https://etherscan.io/token/0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359) (en anglais) à l'adresse de l'app Finance de l'organisation [genesis.aragonid.eth](https://mainnet.aragon.org/#/genesis/settings) (en anglais) alors la commande de transaction que vous enverriez à partir de l'aragonCLI serait :

```
dao exec 0x8A83D4bCE45b4C4F751f76cf565953D1E4A3BF0a 0x98516C82Bda8B3dE6E2670B718848949Ae6a4643 recoverToVault 0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359 --environment aragon:mainnet
```

Merci à Chris Hobcroft d'avoir documenté ces [étapes das ce commentaire GitHub](https://github.com/ethereum-cat-herders/funding/issues/2#issuecomment-477174751) (en anglais).
