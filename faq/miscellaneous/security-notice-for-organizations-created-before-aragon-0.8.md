# Avis de sécurité pour les organisations créées avant Aragon 0.8

Les [changements](https://github.com/aragon/aragonOS/issues/549) (en anglais) dans les règles de consensus du réseau Ethereum, qui ont été activés avec le hard fork d'Istanbul, ont cassé une fonctionnalité clé dans la façon dont les versions pré-0.8 des smart contracts Aragon traitent les dépôts ETH provenant d'autres smart contracts.

Le résultat est qu'après le hard fork d'Istanbul (survenu le 7 décembre 2019), les dépôts ETH envoyés depuis un smart contract vers des smart contracts Aragon pré-0.8 échoueront, et la transaction se retournera. Dans certains cas, cela pourrait entraîner une perte permanente de fonds. En outre, certaines fonctionnalités seront interrompues, ce qui entraînera une mauvaise expérience pour les utilisateurs des organisations Aragon.Les organisations créées après la sortie d'Aragon 0.8 auront automatiquement une correction pour ce problème, et aucune autre action n'est nécessaire.

<mark style="color:red;">**Il est conseillé aux organisations créées avant la sortie d'Aragon 0.8 (11 septembre 2019) de migrer leurs actifs et leurs membres vers une nouvelle organisation Aragon**</mark> créée à l'aide des versions post-0.8 des contrats Aragon.

Vous pouvez créer votre nouvelle organisation à l'adresse [app.aragon.org](https://app.aragon.org) (en anglais), configurer les autorisations de la nouvelle organisation pour qu'elles reflètent celles de l'ancienne, puis transférer les membres, les fonds et les autres actifs vers la nouvelle organisation, et reprendre là où vous en étiez.

Pour plus de détails,, lisez [cet article](https://blog.aragon.org/istanbul-hard-fork-impact/) (en anglais) sur le blog du projet Aragon.
