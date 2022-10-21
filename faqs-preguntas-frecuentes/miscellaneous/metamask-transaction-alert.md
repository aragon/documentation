# Alerta de transacciones en el monedero de Metamask

Cuando el Aragon Cliente (Cliente Aragon) le pide que firme y envíe múltiples transacciones a la blockchain (cadena de bloques) de Ethereum, su proveedor de Ethereum (por ejemplo, Metamask) puede advertirle de que las transacciones posteriores fallarán:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5e31cc5804286364bc949451/file-vZiPEIBtx3.png)

Esto se debe a que el blockchain de Ethereum aún no se ha actualizado desde sus transacciones iniciales, lo que hace imposible que el proveedor de Ethereum determine si las transacciones posteriores tendrán éxito o no.&#x20;

Debería poder ignorar estas advertencias, ya que el cliente de Aragon ya habrá precalculado el estado necesario para asegurar que sus transacciones tengan éxito.
