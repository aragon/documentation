# Utiliser le modèle de réputation

{% hint style="info" %}
Dans cette section, vous apprendrez comment créer un DAO de réputation en utilisant le modèle de réputation dans le client Aragon.
{% endhint %}

{% hint style="danger" %}
Avant de commencer, assurez-vous d'avoir lu [Comment créer une DAO.](./)
{% endhint %}

Une organisation de réputation est une organisation qui utilise des **jetons non transférables** pour représenter la réputation. Les décisions sont prises au moyen **d'un vote pondéré en fonction de la réputation.**

## Création d'un DAO Reputation (de réputation)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.02.19.png>)

Cliquez sur _**View details**_ (Afficher les détails), passez en revue les applications disponibles, cochez les cases pour installer les applications facultatives que vous souhaitez installer. Lorsque vous avez terminé, cliquez sur _**Use this template**_ (Utiliser ce modèle).

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.22.29.png>)

## Réclamer un nom

Sélectionnez le nom de votre DAO et remplissez l'onglet _**Organization Name**_ (Nom de l'organisation). Aragon utilise l' [Ethereum Name Service](https://ens.domains) (ENS) pour attribuer des noms aux organisations.

{% hint style="warning" %}
Ce nom sera utile pour accéder à votre DAO. Ne l'oubliez pas !
{% endhint %}

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.23.36.png>)

## Configurer les paramètres de l'application de Voting (vote)

{% hint style="info" %}
Les paramètres de l'application de vote ne peuvent actuellement pas être modifiés à partir du client frontal d'Aragon. Pour changer les paramètres de l'application de vote après la création de votre organisation, vous devez d'abord initialiser les permissions pour changer ces paramètres, puis vous pouvez changer les paramètres en utilisant l'[aragonCLI](https://hack.aragon.org/docs/cli-intro.html).
{% endhint %}

### Configurer les paramètres de vote

#### Le Support percentage (pourcentage de soutien)

Il s'agit du pourcentage relatif de jetons qui doivent voter _**Yes**_ (Oui) pour qu'une proposition soit approuvée. Par exemple, si le paramètre _**Support**_ est fixé à 50 %, plus de 50 % des jetons utilisés pour voter sur une proposition doivent voter _**Yes**_ (Oui) pour qu'elle soit adoptée.

#### Le Minimum Approval (minimum d'approbation) pourcentage

Il s'agit du pourcentage de l'offre totale de jetons qui doit voter _**Yes**_ (Oui) à une proposition avant qu'elle ne soit approuvée. Par exemple, si l'_**Minimum Approval**_ (approbation minimale) est fixée à 20 %, plus de 20 % des jetons en circulation doivent être approuvés pour que la proposition soit adoptée.

#### La Vote Duration (durée du vote)

Il s'agit de la durée pendant laquelle le vote sera ouvert à la participation. Par exemple, si la durée du vote est fixée à 24 heures, les détenteurs de jetons ont 24 heures pour participer au vote.

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.08.36.png>)

## Configurer les paramètres de l'application Token

Choisissez un nom de jeton, un symbole, les détenteurs de jetons et le montant (solde) du jeton pour chaque détenteur de jeton. Vous pouvez ajouter le détenteur de jeton en utilisant le bouton _**Add more**_ (Ajouter plus).

{% hint style="warning" %}
Le nom et le symbole du jeton ne peuvent actuellement pas être modifiés. N'ajoutez pas plus de quelques détenteurs de jetons à votre organisation sur cet écran, sinon la transaction de création de votre organisation risque d'échouer. Vous pouvez ajouter d'autres détenteurs de jetons après la création de l'organisation.
{% endhint %}

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.25.03.png>)

## Examiner les informations sur l'organisation

Ouvrez chaque panneau pour vous assurer que les informations saisies pour lancer votre organisation sont correctes. Si une information est incorrecte, vous pouvez cliquer sur le bouton _**back**_ (Retour) pour revenir à un écran précédent et apporter les corrections nécessaires.

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.25.54.png>)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.26.03.png>)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.26.14.png>)

## Lancer votre organisation

Vous devez maintenant signer une transaction pour créer votre organisation. Ouvrez votre fournisseur Ethereum si la fenêtre ne s'ouvre pas automatiquement. Cliquez sur le bouton de _**confirm**_ (confirmation) dans votre fournisseur Ethereum pour signer et diffuser la transaction.&#x20;

Attendez que la transaction soit terminée.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624d704286364bc8f650d/file-arEtXF8S0j.png)

Ne fermez pas ou ne rafraîchissez pas la page avant que le processus ne soit terminé et que le DAO ne soit déployé.

## Cliquez sur"Get started" ("Commencer").

{% hint style="success" %}
Votre nouvelle organisation de réputation est prête à fonctionner !
{% endhint %}

Vous pouvez maintenant [explorer votre nouvelle organisation de réputation.](../explore-template-dao/)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.17.04.png>)

{% hint style="info" %}
Si votre DAO ne s'ouvre pas automatiquement, allez [ici](../../../faq/products/aragon-client/where-is-my-dao.md) et découvrez comment y accéder. [here](../../../faq/products/aragon-client/where-is-my-dao.md)
{% endhint %}
