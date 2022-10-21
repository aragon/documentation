# Comment migrer de l'"ancien" DAI vers le "nouveau" DAI ?

Le jeton DAI, géré par [MakerDAO](https://makerdao.com) (en anglais), a été migré pour utiliser une autre adresse de jeton à 16:00 UTC le 18 novembre 2019.

Vous pouvez en savoir plus sur les détails spécifiques de la migration sur le [blog de MakerDAO](https://blog.makerdao.com/multi-collateral-dai-is-live/) (en anglais).

* L'ancien jeton DAI à _0x89d24a6b4ccb1b6faa2625fe562bdd9a23260359_ devient désormais **SAI.**
* Le nouveau contrat multi-collatéral du jeton DAI est _0x6b175474e89094c44da98b954eedeac495271d0f_.

Un outil de migration entre SAI et DAI est disponible sur [migrate.makerdao.com](https://migrate.makerdao.com) (en anglais).

Pour toutes les organisations détenant l'"ancien" jeton DAI (alias SAI), le client Aragon a commencé à afficher le nom correct suite à une mise à jour autour de 2019-11-25.

Pour les organisations détenant SAI, il y a deux chemins recommandés pour passer au DAI multi-collatéral:

* Transférez le SAI sur un compte externe ou un contrat multisig que vous contrôlez. De là, utilisez l'interface de migration sur [migrate.makerdao.com](https://migrate.makerdao.com) (en anglais) pour échanger les SAI en DAI, et déposez le nouveau DAI dans votre organisation.
* Installez une application [Agent app](../../produits/aragon-client/explore-template-dao/what-are-apps/agent-app/), si votre organisation n'en a pas encore installé une. Transférez les ISC dans l'application Agent, configurez les autorisations requises pour permettre les interactions avec l'application Agent et utilisez [migrate.makerdao.com](https://migrate.makerdao.com) (en anglais) via [Frame](https://frame.sh) (en anglais).

Pour les organisations détenant d'anciens SAI Collateralized Debt Position (CDP), les chemins de migration recommandés sont similaires si l'organisation ne détenait que des SAI : transférer la propriété des CDP SAI de l'organisation vers un compte externe, multisig, ou une application Agent installée avec laquelle vous pouvez interagir, et utiliser l'interface [migrate.makerdao.com](https://migrate.makerdao.com) (en anglais). Dans ce scénario, assurez-vous que le compte détenant la propriété du CDP SAI détient également suffisamment de $MKR pour rembourser tous les frais de stabilité dus.

Les organisations qui souhaitent créer de nouveaux coffres DAI doivent interagir avec l'application Oasis Trade en utilisant une application Agent et un cadre installés.
