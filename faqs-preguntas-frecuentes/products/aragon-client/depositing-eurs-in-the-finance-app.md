# Depositar EURS en la Finance App (App de Finanzas)

El [contrato de tokens EURS](https://etherscan.io/address/db25f211ab05b1c97d595516f45794528a807ad8#contracts) tiene un mecanismo de tarifas que podría no estar jugando bien con la forma en que la parte frontal (frontend) de Aragon calcula las aprobaciones de tokens.&#x20;

El `Finance.deposit()`de la Finance App hace un `transferFrom()` (transferencia desde) bajo el capó. El token EURS, en `transferFrom(),` transfiere:

1. El monto solicitado por el titular a la Finance App.
2. Una "tarifa" fijada por el titular al "recaudador de tarifas".

Tanto el monto solicitado como la tarifa establecida requieren la aprobación del titular para la Finance App (ya que Finanzas es el contrato que realiza la`transferFrom()`"llamada"), pero ahora mismo la Finance App únicamente solicita la aprobación para la primera transferencia. Así que cuando un usuario intenta depositar EURS utilizando la Finance App, el monto de la tarifa no ha sido aprobado y la segunda transferencia para la tarifa falla, revirtiendo toda la transacción.

Hay que señalar que este mecanismo de "tarifa" implementado por EURS no forma parte del estándar ERC20. El token EURS afirma ser "compatible con ERC20", pero ajustar el `transferFrom()`como lo ha hecho para este mecanismo hace que EURS sea incompatible con el estándar ERC20. Bajo el estándar ERC20 hay una relación de aprobación a transferencia de 1:1, pero la transferencia de tarifa extra implementada por EURS cambia esta suposición y probablemente romperá muchos contratos de manejo de tokens existentes.

No hay forma de evitar, rodear o solucionar esto ahora mismo usando solo el cliente frontend (frontal) de Aragon porque el contrato de Finanzas también asume una proporción de aprobación a transferencia de 1:1. Los usuarios pueden enviar EURS directamente a la dirección de la Vault App (App de Bóveda) de su organización y, a continuación, realizar un retiro utilizando la [aragonCLI](https://hack.aragon.org/docs/cli-intro.html) (disponible actualmente solo en inglés).
