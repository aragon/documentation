# Alerte sur les transactions du porte-monnaie Metamask

Lorsque le client Aragon vous demande de signer et d'envoyer plusieurs transactions sur la blockchain Ethereum, votre fournisseur Ethereum (par exemple Metamask) peut vous avertir que les transactions suivantes échoueront:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5e31cc5804286364bc949451/file-vZiPEIBtx3.png)

Ceci est dû au fait que la blockchain Ethereum n'a pas encore été mise à jour à partir de vos transactions initiales, ce qui rend impossible pour le fournisseur Ethereum de déterminer si les transactions suivantes vont réussir ou échouer.

Vous devriez être en mesure d'ignorer ces avertissements, car le client Aragon aura déjà pré-calculé l'état requis pour garantir la réussite de vos transactions.
