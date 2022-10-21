# Changez votre quorum utilisant la console Aragon

{% hint style="info" %}
Ce guide vous montrera comment modifier le quorum minimum (participation) nécessaire pour que les votes dans votre DAO passent en utilisant la console Aragon.
{% endhint %}

Ouvrez votre DAO, ajoutant `/console` à la fin de l'url de votre DAO. L'URL devrait alors ressembler à: `https://client.aragon.org/#/<your-dao-name>/console`

{% hint style="warning" %}
Replacez`<your-dao-name>`avec le nom de votre DAO dans l'URL ci-dessus
{% endhint %}

Vous devriez voir quelque chose comme ci-dessous:

<figure><img src="../../../../.gitbook/assets/immagine1.png" alt=""><figcaption></figcaption></figure>

Maintenant sélectionnez `Exec` qui est une commande utilisée pour effectuer des transactions DAOs.

Vous devriez maintenant voir l'écran ci-dessous. Sélectionnez `Voting`, puisque vous allez créer un changement dans l'application de vote :

<figure><img src="../../../../.gitbook/assets/immagine2.png" alt=""><figcaption></figcaption></figure>

Dans le code source de l'application de vote [Github](https://github.com/aragon/aragon-apps/blob/631048d54b9cc71058abb8bd7c17f6738755d950/apps/voting/contracts/Voting.sol) vous pouvez trouver une fonction permettant de modifier le pourcentage minimum de quorum accepté, exactement ce dont nous avons besoin:

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

Nous allons maintenant appeler cette fonction depuis la console Aragon. Nous devrons ajouter`changeMinAcceptQuorumPct(uint64 _minAcceptQuorumPct)`à la commande dans la console, mais d'abord nous allons remplacer `uint64 _minAcceptQuorumPct` avec le pourcentage minimum de quorum que vous souhaitez.

Ceci est exprimé en pourcentage de `10^18` , donc par exemple `100% = 10^18` et `1% = 10^16`. Disons que vous vouliez un nouveau Quorum minimum de 25%, alors vous devez ajouter 16 zéros à 25, ce qui donne `250000000000000000`

{% hint style="danger" %}
**Avertissement**

Le **pourcentage de quorum minimum ne peut jamais être supérieur au pourcentage de soutien requis** pour les votes au sein de votre DAO ! Assurez-vous donc que le pourcentage de soutien requis de votre DAO est de 55 % ou plus. Sinon, utilisez un pourcentage inférieur au pourcentage de soutien requis pour ce tutoriel ( autrement vous rencontrerez un problème plus tard).
{% endhint %}

Maintenant ajoutez `changeMinAcceptQuorumPct(250000000000000000)` à ma commande dans la console:

<figure><img src="../../../../.gitbook/assets/immagine 3.png" alt=""><figcaption></figcaption></figure>

Lorsque vous appuyez sur la touche "Entrée", une transaction devrait s'afficher dans votre fournisseur Web3 (Metamask pour la plupart des utilisateurs). Vérifiez si le pourcentage minimum de quorum correspond à ce que vous aviez en tête:

<figure><img src="../../../../.gitbook/assets/immagine4.png" alt=""><figcaption></figcaption></figure>

Cliquez sur "Créer une transaction" et signez-la avec votre fournisseur Web3.

Vous y êtes presque ! Mais allez d'abord dans l'application de vote puisque ce changement a automatiquement généré un vote. Maintenant, vous (et un nombre suffisant de membres de votre DAO) devez approuver le vote pour qu'il soit adopté :

<figure><img src="../../../../.gitbook/assets/immagine5.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
**Avertissement**

Le changement de volonté ne peut être promulgué que lorsque le temps de vote restant est écoulé. Dans le cas de cet exemple, le `temps restant est de 23H:59M:12S` :point\_up:
{% endhint %}

Lorsque le temps de vote est écoulé, cliquez sur "Valider ce vote" et signez la transaction avec votre fournisseur Web3:

<figure><img src="../../../../.gitbook/assets/immagine6.png" alt=""><figcaption></figcaption></figure>



Une fois que cela est fait, le pourcentage minimum de quorum devrait avoir été ajusté à 25%. Vous pouvez le vérifier en créant un nouveau vote. Lorsque vous ouvrez le vote, `L'autorisation minimale` devrait avoir été ajusté à `>25% nécessaire`.

{% hint style="success" %}
Si vous êtes arrivé jusqu'ici, bravo! :clap:
{% endhint %}

> <mark style="color:purple;">**Vous avez une question? Laissez vos commentaires ici sur notre forum Discourse**</mark>👇

{% embed url="https://forum.aragon.org/" %}
