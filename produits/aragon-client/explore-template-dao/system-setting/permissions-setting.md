# Réglage des autorisations

{% hint style="info" %}
Dans cette section, nous explorons en profondeur le paramètre "Permissions". Vous trouverez une vidéo dédiée à la fin de cette page (en anglais).
{% endhint %}

## Qu'est-ce que l'application Permissions ?

L'**application Permissions** est utilisée pour afficher toutes les permissions actuelles qui ont été définies dans une organisation et ajouter ou supprimer des permissions si nécessaire.&#x20;

Les autorisations définies par l'application Permissions définissent quelles entités ont quelles autorisations pour effectuer diverses actions dans une organisation.&#x20;

Par exemple, n'importe quel compte peut être autorisé à créer un vote, mais seuls les détenteurs de jetons d'une organisation peuvent être autorisés à voter.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a697f2c7d3a7e9ae19121/file-gDcISkpUXb.png)

## Naviguer par application

L'application Permissions affiche une liste de toutes les **applications installées** dans l'organisation et **l'adresse ou le symbole de jeton** de ces applications. Vous pouvez modifier les _App permissions_ (autorisations de l'application) et les _System permissions_ (autorisations du système).

![Autorisations de l'application](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6a562c7d3a7e9ae1912e/file-0y5pgj1j2k.png)

![Permissions du système](../../../../.gitbook/assets/file-mnVytX0QZA.png)

### Chaque application a :

* une liste **d'actions qui peuvent être effectuées** sur l'application,&#x20;
* une liste **d'actions que d'autres entités ont été autorisées à effectuer** sur l'application,&#x20;
* une liste **des autorisations accordées** à l'application.

{% hint style="info" %}
L'image ci-dessous montre la liste des actions qui peuvent être exécutées par l'application Finance (colonne _Action_), les autres entités qui ont les permissions d'exécuter ces actions (colonne _Assigned to entity -_ Affecté à l'entité) et qui a l'autorité d'affecter la permission à cette entité (colonne _Managed by -_ Géré par).
{% endhint %}

![Exemple de permissions pour les finances](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6a7104286364bc8f8145/file-NKD9Oqrl0V.png)

### Exemple

Si nous devons effectuer une action \_**Create new payments** \_ (_Créer de nouveaux paiements)_ dans l'application Finance, cette action passera par un vote dans l'application Vote. La raison en est que l'action Créer de nouveaux paiements dans l'application Finance est affectée à l'entité Vote.

### Permissions disponibles

La section Autorisations disponibles indique&#x20;

* **quelles actions** peuvent être effectuées sur l'application,&#x20;
* **quelle entité** a la permission **d'effectuer** chaque action,&#x20;
* **quelle entité gère** chaque action. Cette entité est appelée "gestionnaire".

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b052c7d3a7e9ae19132/file-68mYNPchqp.png)

Un **manager** (gestionnaire) a **la possibilité de choisir les entités qui ont la permission d'exécuter une action** (_Assign Permission -_ Attribuer une permission) et la **possibilité de changer le gestionnaire de cette action** (_Manage Role -_ Gérer le rôle). Ces actions peuvent être effectuées à l'aide du menu déroulant situé sous les trois points.

![](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.25.57 (1).png>)

### Attribuer des autorisations

Cliquez sur le menu déroulant sur les _trois points_ et sélectionnez _Assign Permission_ (Attribuer une autorisation). Sélectionnez une application dans le menu _On App_, une entité dans le menu _Assign to Entity_ et une action.

![Attribuer une autorisation](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.26.48.png>)

### Gérer le rôle

Cliquez sur le menu déroulant sur les \*\*\* (_trois points_ et sélectionnez _Gestion des rôles._ Sélectionnez une mise à jour sous le menu _**Update**_ (Mise à jour).

![Gérer les permissions](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.37.21.png>)

{% hint style="warning" %}
Si un gestionnaire se retire de la gestion des autorisations sans réassigner le rôle de gestionnaire à une autre entité, la gestion de cette action est confiée par défaut à l'entité qui gère l'action _**Create permissions**_ (Créer des autorisations) dans l'application ACL.&#x20;

Dans l'exemple ci-dessous, la gestion de l'action sera attribuée à l'application Voting.
{% endhint %}

![](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.12.59.png>)

{% hint style="danger" %}
Si le gestionnaire de l'action est défini comme 0x000000000000000000000000000000000001, aucun nouveau gestionnaire ne peut être défini et les autorisations accordées pour cette action seront verrouillées pour toujours.
{% endhint %}

### Initialiser la permission

Si une action n'a pas encore été attribuée à un gestionnaire, elle doit être initialisée. Pour initialiser une action, saisissez l'adresse (_Grant permission to -_ Accorder la permission à) de l'entité qui doit gérer l'action, sélectionnez l'entité à laquelle vous voulez accorder la permission d'exécuter l'action, puis cliquez sur le bouton _Initialize permission_ (Initialiser la permission) pour initialiser la permission, si vous avez la permission de le faire.

![](../../../../.gitbook/assets/inizialize.png)

### Parcourir par entité

De retour sur la page principale des autorisations, vous avez la possibilité d'obtenir une vue d'ensemble de toutes les autorisations définies dans une organisation dans la section _Browse by entity_ (Parcourir par entité).&#x20;

Ici, vous pouvez voir rapidement quelles entités ont reçu l'autorisation d'effectuer quelles actions dans l'organisation.&#x20;

En cliquant sur \*\* **\_**View details\*\*\_ (_Voir les détails)_, vous accédez à la page des autorisations pour cette entité.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b6104286364bc8f8153/file-W609vjv1Pi.png)

### Ajouter une permissio**n**

Pour autoriser une entité à effectuer une action sur une application, cliquez sur le bouton _**Add permission**_ (Ajouter une autorisation), sélectionnez l'application sur laquelle vous souhaitez que l'entité effectue l'action, sélectionnez l'entité à laquelle vous souhaitez accorder l'autorisation, puis sélectionnez l'action que vous souhaitez autoriser l'entité à effectuer.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b732c7d3a7e9ae1913a/file-xsxDomUDSy.png)

Chaque application comporte différentes actions qu'une entité peut être autorisée à exécuter.

Accorder la permission à une entité d'effectuer ces actions sur ces apps lui permettra de :

#### **ACL (Access Control List)**

* Créer des permissions : créer des permissions qui n'ont pas encore été initialisées dans toute application qui utilise cette instance ACL.`*`

> `*`Ces actions sont très sensibles et donneront à l'entité qui a la permission d'effectuer ces actions un contrôle presque total de votre organisation._._

#### **EVM (Ethereum Virtual Machine) Script Registry**

* **Ajouter des exécuteurs** : ajouter un exécuteur à l'organisation`*`
* **Activer et désactiver les exécutants** : activer et désactiver les exécutants dans une organisation.`*`

> `*` Il s'agit d'actions très sensibles qui donneront à l'entité ayant la permission d'effectuer ces actions un contrôle presque total de votre organisation.

{% hint style="warning" %}
Un exécuteur est un interprète permettant d'exécuter des scripts dans une organisation. Toutes les applications d'une organisation utilisent les exécuteurs de l'organisation pour exécuter les scripts qui font partie des transactions envoyées à l'application. Chaque script possède un identifiant qui détermine quel exécuteur est utilisé pour exécuter le script.

Par exemple, chaque fois qu'une transaction de vote est envoyée à l'application Voting, l'application exécute un script, puis utilise un exécuteur pour exécuter le script dans la transaction. Vous pouvez trouver plus de documentation sur les exécuteurs dans le [portail des développeurs d'Aragon](https://hack.aragon.org/).&#x20;
{% endhint %}

#### Kernel

* Gérer les applications : installer des applications, mettre à niveau des applications et modifier les applications par défaut dans une organisation. L'ACL et le registre de scripts EVM sont les applications par défaut de l'organisation. Les personnes autorisées à effectuer cette action peuvent également modifier le contrat de coffre-fort par défaut de l'organisation (qui est le coffre-fort vers lequel les jetons seront envoyés si les jetons sont envoyés à l'adresse d'une application qui n'est pas censée accepter les dépôts de jetons). `*`

> `*`Il s'agit d'actions très sensibles qui donneront à l'entité ayant la permission d'effectuer ces actions un contrôle presque total de votre organisation.

#### **Tokens**

* Monnaie : créer de nouveaux jetons et les transférer à une adresse spécifique.&#x20;
* Émettre des jetons : créer de nouveaux jetons et les transférer vers l'application Tokens de l'organisation, pour les attribuer ultérieurement à une entité donnée.&#x20;
* Attribuer des jetons : transférer des jetons détenus par l'application Tokens à une entité donnée.&#x20;
* Révoquer l'acquisition de jetons : révoquer l'acquisition de jetons d'une entité donnée.&#x20;
* Brûler des jetons : supprimer les jetons détenus par un détenteur de jetons, réduisant ainsi le nombre total de jetons disponibles.

#### **Voting (Vote)**

* Créer de nouveaux votes : créer un nouveau vote&#x20;
* Modifier le soutien : modifier le paramètre Support (Soutien)&#x20;
* Modifier le quorum : modifier le paramètre Minimum Approval %

{% hint style="info" %}
Le **Minimum Approval %** (% d'approbation minimum) est le pourcentage de l'offre totale de jetons que le soutien à une proposition doit dépasser pour que la proposition soit considérée comme valide.

**Exemple 1**

Si le pourcentage minimum d'approbation est fixé à 20 %, plus de 20 % des jetons en circulation doivent voter pour approuver une proposition pour que le vote soit considéré comme valide. Si le quorum n'est pas atteint, le vote échouera, même si plus de jetons ont voté pour approuver la proposition que contre.

**Exemple 2**

Si le pourcentage minimum d'approbation est fixé à 20 % et que 10 % de l'offre de jetons en circulation votent contre la proposition mais que seulement 15 % votent pour, la proposition sera rejetée car elle n'a pas atteint le seuil minimum d'approbation.
{% endhint %}

{% hint style="info" %}
Le **Support** (soutien) est le pourcentage de votes sur une proposition que le soutien total doit dépasser pour que la proposition soit approuvée. Par exemple, si le "Soutien" est fixé à 51%, plus de 51% des votes sur une proposition doivent voter "Oui" pour que la proposition soit adoptée.
{% endhint %}

#### Finance

* Créer de nouveaux paiements : créer un transfert depuis l'application Finance vers une autre entité.&#x20;
* Exécuter des paiements : déclencher un paiement récurrent dû à une entité.&#x20;
* Modifier la durée de la période : modifier la durée en secondes entre les périodes comptables.
* Modifier les budgets : modifier le nombre de jetons pouvant être dépensés au cours d'une période comptable donnée.&#x20;
* Gérer les paiements : activer et désactiver les paiements récurrents.

#### **Vault**

* Transférer les jetons de Vault : transférer les jetons détenus par l'application Vault

{% embed url="https://youtu.be/kMF7Y_KPm-4?t=666" %}
