# Configuration d'un porte-monnaie Metamask

{% hint style="info" %}
Dans cette section, vous apprendrez à mettre en place un porte-monnaie Metamask et à le configurer sur différentes blockchains.
{% endhint %}

{% hint style="success" %}
**Nous vous recommandons d'utiliser** [**Metamask**](https://metamask.io) **(en anglais) comme votre porte-monnaie Web3.**&#x20;

Metamask est un plugin de navigateur qui vous permet d'effectuer des transactions Ethereum (et autres blockchains) à travers des sites web ordinaires.&#x20;
{% endhint %}

{% hint style="warning" %}
Ce guide se concentre sur une extension Chrome. Toutefois, le processus est similaire pour tous les navigateurs.
{% endhint %}

## Pour commencer <a href="#getting-started" id="getting-started"></a>

Pour créer et utiliser un **Aragon Client** (DAO client Aragon), vous devez vous connecter à un réseau de test ou à un réseau principal. Vous pouvez choisir parmi différentes blockchains :

* [Ethereum Mainnet](getting-started-with-ethereum.md)
* [Goerli Testnet](https://app.gitbook.com/s/5JocmZjUHc2kDC6Rngio/products/set-up-metamask/getting-started-with-rinkeby-testnet)
* [Polygon](getting-started-with-polygon.md)
* Andromeda
* [Mumbai Testnet](getting-started-with-mumbai-testnet.md)
* [Harmony](getting-started-with-harmony.md)
* [Harmony Testnet](getting-started-with-harmony-testnet.md)
* [Stardust testnet](getting-started-with-metis-andromeda.md)
* [BSC Testnet](getting-started-with-bsc-testnet.md)

Vous pouvez également créer et interagir avec un DAO directement en utilisant la ligne de commande (dans ce cas, quelques compétences en développement sont nécessaires), également dans ce cas, vous devez vous connecter à un réseau de test ou un réseau principal (les réseaux disponibles sont les mêmes dans la liste supérieure).

Pour créer ou utiliser une **Aragon Govern** (DAO d'Aragon Govern), vous devez vous connecter à un réseau principal:

* [Ethereum Mainnet](getting-started-with-ethereum.md)

Commençons par configurer et comprendre les principaux intérêts du porte-monnaie metamask, puis vous pourrez passer au choix de votre réseau préféré.

## Pour commencer <a href="#getting-started" id="getting-started"></a>

* Visitez la [page d'accueil de Metamask ](https://metamask.io)(en anglais) et téléchargez l'extension de navigateur. Une fois qu'elle est téléchargée, vous devriez être automatiquement dirigé vers une page de bienvenue.

<figure><img src="../../.gitbook/assets/m-0.png" alt=""><figcaption><p>Page d'accueil de MetamaskSuivez attentivement les instructions.</p></figcaption></figure>

* Configurez votre compte Metamask en fonction de vos beoins.

{% hint style="info" %}
Si vous avez besoin de plus d'informations concernant la création de votre propre profil Metamask, vous pouvez vous rendre [ici](https://docs.polygon.technology/docs/develop/metamask/hello/) (en anglais).
{% endhint %}

* Une fois l'installation de Metamask terminée, vous devriez être redirigé vers votre portefeuille Ethereum nouvellement créé.

![Metamask account](<../../.gitbook/assets/mm account (1).png>)

{% hint style="success" %}
Si vous êtes arrivé jusqu'ici, félicitations. 🎉.
{% endhint %}

## Adresse du compte <a href="#account-address" id="account-address"></a>

Si vous cliquez sur le bouton "**trois points**" situé sous le nom de votre compte - dans notre cas, _Account 1 (Compte 1)_ - une fenêtre pop-up apparaîtra avec l'adresse de votre compte. Elle devrait ressembler à l'exemple ci-dessous :

> **0x931D387731bBbC988B312206c74F77D004D6B84b**

{% hint style="success" %}
Il s'agit de votre adresse publique (ou clé publique). Vous pouvez la partager avec d'autres personnes pour recevoir des ETH ou d'autres jetons.
{% endhint %}

## Réseaux sélectionnés <a href="#selected-networks" id="selected-networks"></a>

En haut à droite, vous devriez voir un menu déroulant avec le _**Main Ethereum Network**_ (réseau Ethereum principal) sélectionné. Avec cette option, vous êtes en mesure d'interagir directement avec la blockchain principale d'Ethereum.&#x20;

**Si vous cliquez dessus, une sélection d'autres réseaux s'affichera.**

<figure><img src="../../.gitbook/assets/1_Setting Up MM_Networks List.png" alt=""><figcaption><p>Menu déroulant pour sélectionner le réseau.</p></figcaption></figure>

## Pourquoi choisir d'autres réseaux ?

Avant de lancer un projet (ou une Dapp) sur le réseau principal d'Ethereum, il est bon de déployer une version sur un réseau de test d'Ethereum ou sur d'autres réseaux principaux (comme Polygon ou Harmony) pour économiser sur les frais de transaction.

### Les avantages de l'utilisation d'un réseau de test

La principale raison d'utiliser un réseau de test ETH est qu'il peut être obtenu sans avoir à payer de l'argent réel. Cela donne aux développeurs et à la communauté une chance de régler les problèmes avant que de l'argent réel ne soit impliqué.&#x20;

**Il existe quatre réseaux de test :**

* Sepolia
* Goerli

{% hint style="warning" %}
**À ce stade, ne vous inquiétez pas des différences entre ces réseaux.** Tout ce que vous devez savoir, c'est qu'ils simulent Ethereum et pe
{% endhint %}

### Utilisation de réseaux privés

Enfin, vous pouvez également interagir avec les réseaux Ethereum privés en sélectionnant **Localhost 8545**. Privé dans ce cas ne signifie pas plus sécurisé. Cela signifie simplement que les nœuds ne sont pas connectés aux nœuds du réseau principal ou du réseau de test. **Parfait pour l'expérimentation et les tests rapides.**

{% hint style="warning" %}
N'oubliez pas que si vous souhaitez utiliser différents réseaux, vous devez configurer votre porte-monnaie et le charger avec suffisamment de fonds pour payer les frais de transaction. Nous vous expliquerons comment procéder dans les prochaines sections.
{% endhint %}

> <mark style="color:purple;">**Vous avez une question ? Laissez vos commentaires ici sur notre forum Discourse (en anglais)**</mark>** 👇**

{% embed url="https://support.aragon.org/t/web-3-metamask-wallet/15/2" %}
