# Changez votre Quorum utilisant EVMcrispr

{% hint style="info" %}
Ce guide vous montrera comment modifier le quorum minimum (participation) nécessaire pour que les votes dans votre DAO passent en utilisant [**EVMcrispr**](https://evm-crispr.blossom.software/#/).

EVMcrispr est un outil puissant qui combine un langage spécifique au domaine et une bibliothèque Javascript pour interagir avec les DAOs Aragon.
{% endhint %}

Première chose, ouvrez EVMcrispr [ici](https://evm-crispr.blossom.software/#/) et clickez sur 'Open Terminal'. Désormais, cet écran devrait apparaître:

<figure><img src="../../../../.gitbook/assets/crisper1.png" alt=""><figcaption></figcaption></figure>

Ensuite, supprimez tout le texte dans le terminal :

<figure><img src="../../../../.gitbook/assets/crisper2.png" alt=""><figcaption></figcaption></figure>

Pour modifier le pourcentage minimum de quorum de votre DAO, vous devez vous connecter à votre DAO avec connect `<dao-name-or-address`.  Ensuite ajoutez `token-manager voting` car l'appliacation `token-manager` possède le `CREATE_VOTES_ROLE`nécessaire pour transmettre les actions de vote à l'application avec laquelle nous allons interagir. Voici ce que nous avons jusqu'à présent:

```
connect <dao-name-or-address> token-manager voting
```

Nous allons maintenant écrire la deuxième ligne de commande pour le terminal EVMcrispr. La première à ajouter est exec qui est une commande utilisée pour effectuer des transactions DAOs. Ensuite nous ajoutons voter l'application avec laquelle nous allons interagir. Voici ce que nous avons jusqu'à présent:

```
connect <dao-name-or-address> token-manager voting
exec voting
```

Nous ne sommes cependant pas prêts. Lorsque nous regardons dans le code source de l'application de vote sur [Github](https://github.com/aragon/aragon-apps/blob/631048d54b9cc71058abb8bd7c17f6738755d950/apps/voting/contracts/Voting.sol) nous pouvons trouver une fonction pour changer le pourcentage minimum de quorum accepté, c'est exactement ce dont nous avons besoin:

```solidity
function changeMinAcceptQuorumPct(uint64 _minAcceptQuorumPct)
    external
    authP(MODIFY_QUORUM_ROLE, arr(uint256(_minAcceptQuorumPct), uint256(minAcceptQuorumPct)))
{
    require(_minAcceptQuorumPct <= supportRequiredPct, ERROR_CHANGE_QUORUM_PCTS);
    minAcceptQuorumPct = _minAcceptQuorumPct;

    emit ChangeMinQuorum(_minAcceptQuorumPct);
}
```

Nous allons maintenant ajouter cette fonction aux commandes pour que le terminal l'appelle. Nous devrons ajouter`changeMinAcceptQuorumPct(uint64 _minAcceptQuorumPct)`, mais premièrement nous allons remplacer `uint64 _minAcceptQuorumPct` avec le pourcentage minimum du Quorum que vous souhaitez.

Ceci est exprimé en pourcentage de `10^18` , donc par exemple `100% = 10^18` and `1% = 10^16`. Si vous voulez un nouveau quorum minimum de 25%, vous devez ajouter 16 zéros à 25, ce qui donne `250000000000000000`

{% hint style="danger" %}
Le pourcentage de Quorum minimum ne peut jamais être supérieur au pourcentage de soutien requis pour les votes au sein de votre DAO ! Assurez-vous donc que le pourcentage de soutien requis de votre DAO est de 55% ou plus. Sinon, utilisez un pourcentage inférieur au pourcentage de soutien requis pour ce tutoriel ( autrement vous rencontrerez un problème plus tard).
{% endhint %}

Maintenant ajoutez `changeMinAcceptQuorumPct 250000000000000000` aux commandes pour le terminal:

```
connect <dao-name-or-address> token-manager voting
exec voting changeMinAcceptQuorumPct 250000000000000000
```

Les commandes sont prêtes ! Copiez/collez-les dans le terminal et cliquez sur le bouton 'Forward from ...':

<figure><img src="../../../../.gitbook/assets/crisper3.png" alt=""><figcaption></figcaption></figure>

Signez la transaction à partir de votre fournisseur Web3 et elle devrait maintenant s'exécuter avec succès.

{% hint style="danger" %}
**Warning**

Utilisez votre adresse DAO en cas de votre nom DAO en cas de cette erreur :

`Error: ENS <dao-name>.aragonid.eth not found in rinkeby, please introduce the address of the DAO instead.`
{% endhint %}

Nous sommes presque prêts mais il faut d'abord ouvrir votre DAO dans le navigateur web. L'url doit être :

`https://client.aragon.org/#/<dao-name-or-address>`

Allez ensuite dans l'application de vote puisque ce changement a automatiquement généré un vote. Maintenant, vous (et un nombre suffisant de membres de votre DAO) devez approuver le vote pour qu'il soit adopté :

<figure><img src="../../../../.gitbook/assets/crisper4.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
**Avertissement**

Le changement de volonté ne peut être promulgué que lorsque le temps de vote restant est écoulé. Dans le cas de cet exemple, le `temps restant est 23H:59M:12S` :point\_up:
{% endhint %}

Lorsque le temps de vote est écoulé, cliquez sur "Valider ce vote" et signez la transaction avec votre fournisseur Web3 :

<figure><img src="../../../../.gitbook/assets/crisper5.png" alt=""><figcaption></figcaption></figure>



Une fois que cela est fait, le pourcentage minimum de quorum devrait avoir été ajusté à 25%. Vous pouvez le vérifier en créant un nouveau vote. Lorsque vous ouvrez le vote, le seuil minimal d'approbation devrait avoir été ajusté à `>25% nécessaire`.

{% hint style="success" %}
Si vous êtes arrivé jusqu'ici, bravo! :clap:
{% endhint %}



> <mark style="color:purple;">**Vous avez une question? Laissez vos commentaires ici sur notre forum Discourse**</mark>**  👇**

{% embed url="https://forum.aragon.org/" %}
