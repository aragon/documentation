# Metamask wallet transaction alert

When the Aragon Client asks you to sign and send multiple transactions to the Ethereum blockchain, your Ethereum provider (e.g. Metamask) may warn you that the subsequent transactions will fail:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5e31cc5804286364bc949451/file-vZiPEIBtx3.png)

This is due to the Ethereum blockchain not yet having been updated from your initial transactions, which makes it impossible for the Ethereum provider to determine whether the subsequent transactions will succeed or fail.

You should be able to safely ignore these warnings, as the Aragon client will have already pre-computed the state required to ensure your transactions will succeed.
