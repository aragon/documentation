# Ajout d'un nouveau jeton pour l'intégration légale

{% hint style="info" %}
Dans cette section, nous montrons comment Aragon pourrait interagir avec une entité légale telle qu'une C-Corp du Delaware. Dans notre exemple, le DAO d'Aragon utilise également Gnosis Safe et EVM-CRISPR, afin de montrer comment un DAO existant pourrait avoir accès aux entités juridiques.
{% endhint %}

## Introduction

Les enveloppes juridiques sont un sujet difficile, et pour plus de clarté, l'auteur n'est pas un avocat et ne donne pas de conseils juridiques... l'objectif de ce travail est de montrer un exemple de la façon dont Aragon pourrait interagir avec une LLC, cependant cet exemple n'est pas destiné à servir de processus nécessairement utile, mais plutôt de point de départ pour la critique.....

## Démarrage rapide

Créez votre DAO en commençant [ici](https://client.aragon.org/#/) (en anglais). Pour cet exemple, j'ai créé un [DAO de réputation Aragon.](../how-to-create-a-dao-using-aragon-client/page-1.md)

![DAO de base avec un DAO de réputation - utilisé parce que ces jetons ne doivent pas être transférables.](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.35.12 PM.png>)

## Frappez votre jeton

Ensuite, rendez-vous sur  [EVM CRISPR](https://evm-crispr.blossom.software/#/terminal) où vous pourrez introduire un code pour créer un nouveau jeton.&#x20;

* Connectez votre porte-monnaie&#x20;
* Videz la console&#x20;
* Copiez et collez ces commandes

```
connect your-dao-here token-manager voting 
new token "Test Token" TEST token-manager:new
install token-manager:new token:TEST true 0
grant voting token-manager:new MINT_ROLE voting
grant voting token-manager:new BURN_ROLE voting
exec token-manager:new mint @me 100e18
```

* Cliquez sur la commande forward et signez la transaction sur votre porte-monnaie.&#x20;
* Une fois la transaction confirmée, cliquez sur _Go Vote_ et votez sur votre DAO.

![EVM CRISPR](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.10.14 PM.png>)

![Votez sur votre transaction EVM CRISPR](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.32.09 PM.png>)

Maintenant que vous avez créé vos nouveaux jetons, vous pouvez les voir dans votre liste de jetons.\


![C'est notre DAO](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.11.44 PM.png>)

## Enveloppe légale pour vous Aragon DAO

Passons maintenant à [Gnosis](https://gnosis-safe.io) (en anglais) où nous allons relier les points.&#x20;

* Créez un coffre-fort Gnosis (pour plus d'aide, cliquez [ici](https://help.gnosis-safe.io/en/articles/3876461-create-a-safe)) et déposez des fonds dans votre coffre-fort pour signer les transactions.&#x20;
* Chargez l'application Otoco&#x20;
* Nommez votre société et choisissez entre les DAO du Delaware, de l'UNA et du Wyoming.
* _Approve Payment_ (Approuver le paiement) et _Activate the Company_ (activer l'entreprise)

Les principales étapes sont présentées dans les images ci-dessous.

![Créer une chambre forte dans gnosis](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.04.21 PM.png>) ![Chargez l'application Otoco](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.04.31 PM.png>) ![Nommez votre entreprise et choisissez entre les DAO du Delaware, de l'UNA et du Wyoming.](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.05.46 PM.png>) ![Choisissez votre saveur et votre menthe !
](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.05.58 PM.png>)

Si vous voyez un message tel que "your entity smart contract is not a wallet" ("votre contrat intelligent d'entité n'est pas un portefeuille"), allez sur la page "_Asset wallet_" et ajoutez un propriétaire (une _Wallet address (_adresse de portefeuille) ou une _Gnosis Safe Address (_adresse sécurisée Gnosis)).

![](<../../../.gitbook/assets/Schermata 2022-06-07 alle 14.50.29.png>)

Allez ensuite sur la page Tokens et copiez-collez l'adresse de votre token (vous la trouverez sur la [page Organisation de vostre DAO](../explore-template-dao/system-setting/organization-setting.md)).

![Transférez les jetons de votre DAO à votre LLC Otoco.](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.11.31 PM.png>)

Maintenant vous avez un Delaware LLC avec des jetons frappés par Aragon !

![](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.15.49 PM.png>)





> <mark style="color:purple;">**Vous avez une question ? Laissez vos commentaires ici sur notre forum Discourse (en anglais).**</mark>**  👇**

{% embed url="https://support.aragon.org/t/aragon-client-legal-wrappers/173" %}
