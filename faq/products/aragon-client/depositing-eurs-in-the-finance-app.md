# Dépôt d'EURS dans l'application Finance

Le [contrat de jeton EURS](https://etherscan.io/address/db25f211ab05b1c97d595516f45794528a807ad8#contracts) (en anglais) a un mécanisme de frais qui pourrait ne pas être compatible avec la façon dont le front-end d'Aragon calcule les approbations de jeton.

L'application `Finance.deposit()` de l'application Finance effectue un `transferFrom()`sous le capot. Le jeton EURS, lors d `transferFrom()`, transfère:

1. Le montant demandé du détenteur à l'application Finance.
2. Un montant fixe de "frais" du détenteur au "collecteur de frais".

Le montant demandé et le montant des frais fixés nécessitent tous deux l'approbation du détenteur pour l'application Finance (puisque Finance est le contrat qui effectue l'appel transferFrom()), mais pour l'instant l'application Finance ne demande l'approbation que pour le premier transfert. Ainsi, lorsqu'un utilisateur tente de déposer des EURS à l'aide de l'application Finance, le montant des frais n'a pas été approuvé et le second transfert échoue, ce qui annule l'ensemble de la transaction.

Il convient de noter que ce mécanisme de "frais" mis en œuvre par EURS ne fait pas partie de la norme ERC20. Le jeton EURS prétend être "conforme à la norme ERC20", mais l'ajustement du transferFrom() comme il l'a fait pour ce mécanisme rend EURS incompatible avec la norme ERC20. Dans le cadre de la norme ERC20, il existe un ratio approbation/transfert de 1:1, mais le transfert de frais supplémentaires mis en œuvre par EURS modifie cette hypothèse et brisera probablement beaucoup de contrats de manipulation de jetons existants.

Il n'y a aucun moyen de contourner ce problème pour le moment en utilisant uniquement le client frontal d'Aragon, car le contrat Finance suppose également un ratio d'approbation de transfert de 1:1. Les utilisateurs peuvent envoyer des EURS directement à l'adresse de l'application Vault de leur organisation, puis effectuer un retrait en utilisant [l'aragonCLI](https://hack.aragon.org/docs/cli-intro.html) (en anglais).
