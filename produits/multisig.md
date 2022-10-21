# Configuration d'un portefeuille MultiSig

{% hint style="info" %}
Dans cette section, nous allons voir comment les DAOs du client Aragon peuvent être gérés par un porte-monnaie MultiSig.
{% endhint %}

Ici, nous allons utiliser [**Gnosis Safe MultiSig**](https://help.gnosis-safe.io/en/articles/3876461-create-a-safe), (en anglais) mais vous pouvez suivre une approche similaire pour tout autre portefeuille MultiSig qui prend en charge l'interaction des contrats.

{% hint style="info" %}
Ici, nous allons utiliser [Gnosis Safe MultiSig](https://gnosis-safe.io) (en anglais), mais vous pouvez suivre une approche similaire pour tout autre portefeuille MultiSig qui prend en charge l'interaction des contrats.
{% endhint %}

## Conditions préalables

### Attribuez les permissions souhaitées dans le DAO du client au MultiSig.

{% hint style="info" %}
Les DAOs Aragon Client (du client Aragon) ont accès à un système de contrôle, où chaque action est protégée par un ensemble d'enregistrements de permission. Seule une personne ayant des permissions spécifiques peut agir. C'est pourquoi nous devons attribuer au porte-monnaie MultiSig une série de permissions qui correspondent aux actions souhaitées. Vous pouvez en savoir plus à ce sujet [ici](aragon-client/explore-template-dao/system-setting/permissions-setting.md).
{% endhint %}

1\. Suivez les étapes ci-dessous pour attribuer une permission à un MultiSig.

2\. Ouvrez votre portail DAO et sélectionnez l'onglet _**permissions**_ sur la gauche. Vous pouvez y examiner les autorisations dont vous disposez dans votre DAO.&#x20;

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6112718fb55c2b04bf6dce7e/file-DCOHNWElgt.png)

3\. Pour ajouter une nouvelle autorisation, cliquez sur le bouton _**New Permission**_ (Nouvelle autorisation).&#x20;

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611272116ffe270af2a97627/file-D7HYuaQgTh.png)

4\. Sélectionnez l'application pour laquelle vous voulez créer une permission dans le menu déroulant App.&#x20;

5\. Sélectionnez l'entité à laquelle la nouvelle permission sera attribuée dans le champ \_**Assign To Entity** \_. Pour ajouter l'adresse MultiSig, sélectionnez _**Custom Address**_  et entrez l'adresse dans le champ ci-dessous.&#x20;

6\. Sélectionnez l'action à laquelle vous voulez accorder la permission. Dans notre cas, nous attribuons à un MultiSig la permission de créer de nouveaux votes dans notre DAO.&#x20;

7\. Cliquez sur _**Add Permission**_ (Ajouter une permission). Cela peut créer un vote en fonction de la structure de votre DAO et de l'identité du gestionnaire des autorisations de cette action.&#x20;

8\. Révoquez les permissions indésirables. Pour ce faire, développez n'importe quelle autorisation et cliquez sur l'icône de la poubelle.

{% hint style="danger" %}
Soyez prudent, car des permissions incorrectes pourraient rendre votre DAO vulnérable ou inaccessible.
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611275a7b37d837a3d0e2535/file-AecSpNvGSO.png)

Résultat :

![Multisig Permissions](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d0ef364a230081ba1ce2f/file-aDCnpa7wjo.png)

{% hint style="info" %}
Ici, nous avons attribué à MutliSig des permissions pour gérer les paiements et modifier les paramètres de support du vote au sein du DAO. Cependant, comme nous avons conservé le vote en tant que gestionnaire de permissions, les membres de la communauté pourront voter pour supprimer ces permissions, révoquant ainsi le contrôle de MultiSig sur le DAO.
{% endhint %}

### Exécution des actions

1\. Allez sur le site de [Gnosis Safe](https://gnosis-safe.io) (en anglais) et connectez-vous à leur DApp.&#x20;

2\. Ouvrez votre coffre-fort.&#x20;

3\. Appuyez sur le bouton _**New Transaction**_ (Nouvelle transaction) et sélectionnez _**Contract Interaction**_ (Interaction du contrat).

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d0efb766e8844fc34e2c5/file-ery56Brop6.png)

4\. Indiquez l'adresse de l'application Aragon avec laquelle vous souhaitez interagir.&#x20;

Vous pouvez la trouver sur la page _**Organizations**_ de votre portail DAO. Regardez la section \_**Installed Aragon Apps** \_ (_Applications Aragon installées)_.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d1014766e8844fc34e2cd/file-8cuqErvYC1.png)

5\. Cela remplira automatiquement le champ ABI. Supprimez le contenu qui y figurait.&#x20;

6\. Trouvez le contrat de base de l'application Aragon sélectionnée avec laquelle vous voulez interagir.&#x20;

* Ouvrez l'adresse que vous avez utilisée à l'étape 4 sur [etherscan](https://etherscan.io) (en anglais).&#x20;
* Allez à _**Contract**_ (Contrat)&#x20;
* Sélectionnez _**Read contrac**_ (Lire le contrat)
* Développez _**Implementation**_ (Implementation)
* Ouvrez l'adresse qui apparaît sous _**Implementation**_ sur [etherscan](https://etherscan.io) (en anglais)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d115d766e8844fc34e2ce/file-g3POvBnP7e.png)

7\. Copiez l'ABI de l'adresse ouverte dans le champ de l'étape 5.

* Aller au _**Contract**_ (contrat)
* Sélectionner le _**Code**_
* Trouver _**Contract ABI**_ (l'ABI du contrat)
* Copier l'ABI dans le champ de saisie de l'ABI de Gnosis Safe.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d12f1766e8844fc34e2d7/file-nCgkCpoDAD.png)

8\. Sélectionnez la méthode que vous souhaitez utiliser et renseignez les paramètres.

Ici, nous allons créer un nouveau paiement immédiat à partir de l'application Finance. Il transférera **0,1 ETH** (représenté par une adresse de jeton 0x0..0) à l'adresse 0x424....

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611277e1766e8844fc34f0ab/file-xlkaRMNQ6n.png)

9\. Appuyez sur _**Review**_ et _**Submit**_. Une fois qu'un nombre suffisant de personnes aura signé la transaction, vous pourrez la consulter sur Etherscan. Une fois confirmée, elle prendra effet sur le DAO.&#x20;

## Problèmes possibles

{% hint style="warning" %}
Assurez-vous que vous avez les autorisations nécessaires pour invoquer cette méthode à partir de l'adresse Gnosis Safe.
{% endhint %}

{% hint style="warning" %}
Si l'estimation des gaz a échoué et que vous recevez des avertissements, il y a probablement eu une erreur dans les autorisations, les paramètres de la méthode ou l'ABI et l'adresse du contrat. Veuillez recommencer la configuration.
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611278276ffe270af2a97644/file-rxfkptmQt8.png)

{% hint style="warning" %}
Si vous saisissez des nombres fractionnaires, ajoutez 18 zéros à la valeur initiale. Par exemple, si vous voulez invoquer la méthode **immediateTransfer** qui transférera 10,5 jetons, vous devrez saisir 10,5\*10^18 = 10500000000000000000 dans le champ du montant.
{% endhint %}

{% hint style="warning" %}
Si l'ABI ne s'affiche pas sur un réseau (Rinkeby par exemple), obtenez l'ABI similaire d'une autre DAO sur un réseau différent (Ethereum Mainnet par exemple).
{% endhint %}

> <mark style="color:purple;">**Vous avez une question ? Laissez vos commentaires ici sur notre forum Discourse (en anglais).**</mark>** 👇**

{% embed url="https://support.aragon.org/t/web3-multisig-wallet/17/2" %}
