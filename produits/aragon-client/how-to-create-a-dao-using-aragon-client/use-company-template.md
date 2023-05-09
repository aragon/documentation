# Utilisation du modèle de l'entreprise

{% hint style="info" %}
Dans cette section, vous apprendrez comment créer un DAO de société en utilisant le modèle de société dans le client Aragon.
{% endhint %}

{% hint style="danger" %}
Avant de commencer, assurez-vous d'avoir lu [Comment créer une DAO.](./)
{% endhint %}

## Qu'est-ce qu'une organisation d'entreprise ?

Une organisation d'entreprise est une organisation qui utilise des jetons transférables pour représenter une participation dans l'entreprise. Les décisions sont prises par le biais d'un vote pondéré par jeton, où un jeton équivaut à un vote.

## Créer un DAO Company (d'entreprise)&#x20;

Cliquez sur _**View details**_ (Afficher les détails), passez en revue les applications disponibles, cochez les cases pour installer les applications facultatives que vous souhaitez installer. Lorsque vous avez terminé, cliquez sur _**Use this template**_ (Utiliser ce modèle).

![Sélectionnez le modèle](<../../../.gitbook/assets/Schermata 2022-02-04 alle 18.41.40.png>)

![Modèle d'entreprise](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d86242f04286364bc8f6507/file-QeXiahqUec.png)

## Réclamer un nom

Sélectionnez le nom de votre DAO et remplissez l'onglet Nom de l'organisation. Aragon utilise l'[Ethereum Name Service](https://ens.domains) (ENS) (en anglais) pour attribuer des noms aux organisations.

{% hint style="warning" %}
Ce nom sera utile pour accéder à votre DAO. Ne l'oubliez pas !
{% endhint %}

![Sélectionnez le nom d'entreprise](<../../../.gitbook/assets/Schermata 2022-02-04 alle 18.52.45.png>)

## Configurer les paramètres de l'application Voting (de vote)

{% hint style="info" %}
Les paramètres de l'application de Voting (vote) ne peuvent actuellement pas être modifiés à partir du client frontal d'Aragon. Pour changer les paramètres de l'application de vote après la création de votre organisation, vous devez d'abord initialiser les permissions pour changer ces paramètres, puis vous pouvez changer les paramètres en utilisant l'[aragonCLI ](https://hack.aragon.org/developers/tools/aragoncli)(en anglais).
{% endhint %}

### Configurer les paramètres de vote

#### Le Support percentage (pourcentage de soutien)

Il s'agit du pourcentage relatif de jetons qui doivent voter _**Yes**_ (Oui) pour qu'une proposition soit approuvée. Par exemple, si le paramètre _**Support**_ est fixé à 50 %, plus de 50 % des jetons utilisés pour voter sur une proposition doivent voter _**Yes**_ (Oui) pour qu'elle soit adoptée.

#### Le Minimum Approval (minimum d'approbation) pourcentage

Il s'agit du pourcentage de l'offre totale de jetons qui doit voter _**Yes**_ (Oui) à une proposition avant qu'elle ne soit approuvée. Par exemple, si l'approbation _**Minimum Approval**_ (minimale) est fixée à 20 %, plus de 20 % des jetons en circulation doivent être approuvés pour que la proposition soit adoptée.

#### La Vote Duration (durée du vote)

Il s'agit de la durée pendant laquelle le vote sera ouvert à la participation. Par exemple, si la durée du vote est fixée à 24 heures, les détenteurs de jetons ont 24 heures pour participer au vote.

![Configurer les paramètres de vote](<../../../.gitbook/assets/Schermata 2022-02-04 alle 19.01.42.png>)

## Configurer les paramètres de l'application Token&#x20;

Choisissez un nom de jeton, un symbole, les détenteurs de jetons et le montant (solde) du jeton pour chaque détenteur de jeton. Vous pouvez ajouter le détenteur de jeton en utilisant le bouton _**Add more**_ (Ajouter plus).

{% hint style="warning" %}
Le nom et le symbole du jeton ne peuvent actuellement pas être modifiés. N'ajoutez pas plus de quelques détenteurs de jetons à votre organisation sur cet écran, sinon la transaction de création de votre organisation risque d'échouer. Vous pouvez ajouter d'autres détenteurs de jetons après la création de l'organisation.
{% endhint %}

![Paramètres de l'application Token](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624862c7d3a7e9ae173e4/file-wSKI8WfAzK.png)

## Examiner les informations sur l'organisation

Ouvrez chaque panneau pour vous assurer que les informations saisies pour lancer votre organisation sont correctes. Si une information est incorrecte, vous pouvez cliquer sur le bouton _**back**_ (Retour) pour revenir à un écran précédent et apporter les corrections nécessaires.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624af04286364bc8f650a/file-QLxk1Q0FZj.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624b704286364bc8f650b/file-IsP1SOVaHO.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624bf2c7d3a7e9ae173e5/file-Qn8KEkg3If.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624c604286364bc8f650c/file-Fqvyo6L3Kz.png)

## Lancer votre organisation

Vous devez maintenant signer une transaction pour créer votre organisation. Ouvrez votre fournisseur Ethereum si la fenêtre ne s'ouvre pas automatiquement. Cliquez sur le bouton \_**confirm** \_ (confirm) dans votre fournisseur Ethereum pour signer et diffuser la transaction.

Attendez que la transaction soit terminée.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624d704286364bc8f650d/file-arEtXF8S0j.png)

Ne fermez pas ou ne rafraîchissez pas la page avant que le processus ne soit terminé et que le DAO ne soit déployé.

## Cliquez sur "Get started" ("Commencer").&#x20;

{% hint style="success" %}
Votre nouvelle organisation de la société est prête à fonctionner !
{% endhint %}

Vous pouvez maintenant explorer [explorer votre nouvelle organisation de la sociéte](../explore-template-dao/).

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624ee04286364bc8f650e/file-a4bAYgLmxU.png)

{% hint style="info" %}
Si votre DAO ne s'ouvre pas automatiquement, allez [ici](../../../faq/products/aragon-client/where-is-my-dao.md) et découvrez comment y accéder.
{% endhint %}
