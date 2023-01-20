# Utilisation d'Agent avec Frame

{% hint style="info" %}
Dans cette section, nous allons vous expliquer comment utiliser Agent App avec Frame wallet.
{% endhint %}

## Comment utiliser l'application Agent ?

La façon la plus simple d'utiliser l'application Agent pour interagir directement avec d'autres _contrats intelligents_ Ethereum est d'utiliser la fonctionnalité de compte intelligent de Frame. Frame est un fournisseur Ethereum natif du bureau, avec un support natif pour l'application Agent.

{% hint style="info" %}
Si vous avez déjà installé Frame et ajouté un "compte d'acteur", vous pouvez passer directement à la section **Add your Aragon Agent** (Ajouter votre agent Aragon).
{% endhint %}

{% hint style="info" %}
Si Frame n'est pas installé sur votre ordinateur, cliquez [ici.](https://app.gitbook.com/s/5JocmZjUHc2kDC6Rngio/products/setting-up-a-frame-wallet)
{% endhint %}

## Envoyez de l'ETH (ou de l'ETH de test) sur votre compte d'intérimaire

{% hint style="warning" %}
Avant de commencer, préparez-vous en envoyant des ETH (ou des ETH de test) sur votre compte intérimaire.
{% endhint %}

Votre **compte d'agent** est le compte qui détient au moins un **jeton de vote** (ou une partie s'il est divisible) dans votre organisation et est le compte que vous utiliserez pour **interagir avec les smart contracts** via Agent.&#x20;

L'ETH que vous envoyez sur ce compte est utilisé pour payer l'essence chaque fois que l'application Agent interagit avec d'autres smart contracts. Veillez à recharger l'ETH sur votre compte d'agent dès qu'il est faible afin d'éviter les erreurs de panne sèche lorsque vous interagissez avec d'autres contrats intelligents.

## Ajoutez votre compte d'agent

Ouvrez l'application de bureau Frame et cliquez sur le bouton _**plus-sign**_ (plus-signature) pour ajouter votre compte d'agent. Vous pouvez l'ajouter en utilisant un porte-monnaie matériel ou un porte-monnaie virtuel.

{% hint style="info" %}
Dans cet exemple, nous utiliserons un hot wallet puisque nous utilisons le Goerli Testnet et non de l'argent réel sur le Mainnet Ethereum. Cependant, il est recommandé d'utiliser un porte-monnaie matériel.
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bd9702c7d3a7e9ae1a220/file-wPNVEoD1j4.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bd9782c7d3a7e9ae1a221/file-BZzJ4WikKD.png)

![](../../../../../.gitbook/assets/file-Hdky5v4UL9.png)

## Ajoutez votre agent Aragon

* Allez au même écran sur Frame que vous avez utilisé pour ajouter votre compte intérimaire, puis ajoutez votre agent Aragon sous la section _**Smart accounts**_.&#x20;
* Entrez le nom de votre organisation Aragon, puis cliquez sur _**Next**_ (Suivant).

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bda5504286364bc8f90f9/file-2urBqXQ8j0.png)

* Sélectionnez ensuite le compte actif, en choisissant le compte avec l'adresse qui détient le(s) jeton(s) de vote de votre organisation si vous avez plus d'un compte à sélectionner.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bdabd04286364bc8f90fb/file-QPxHyh0odz.png)

* Sélectionnez l'adresse intérimaire, en choisissant l'adresse qui détient le(s) jeton(s) de vote de votre organisation.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bdb0b2c7d3a7e9ae1a22a/file-sfavzdmwav.png)

* Votre agent Aragon apparaîtra maintenant dans la liste des comptes disponibles à utiliser avec Frame.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bdb3b04286364bc8f9104/file-yCdIwFtn04.png)

## Utilisation de votre agent Aragon

Cliquez sur le logo Aragon pour utiliser votre compte Agent. Entrez votre mot de passe si vous utilisez un compte à chaud. Vous êtes maintenant prêt à interagir avec tout autre contrat intelligent Ethereum directement avec votre agent Aragon.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bddef04286364bc8f9121/file-JXtXhKiVAb.png)

{% hint style="warning" %}
N'oubliez pas qu'en fonction des autorisations définies dans votre organisation, les détenteurs de jetons de votre organisation devront peut-être se rendre dans l'application Voting et voter pour chaque transaction effectuée à l'aide de l'application Agent.
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bdf5e04286364bc8f912b/file-FFA5Mwilwm.png)
