# Finance App (App de finanzas)

La **Finance App** se utiliza para gestionar los recursos financieros de una organización.

## Objetivo de la aplicación de finanzas

* Comprobar **the balance** (el balance) de cada activo que posee la organización.&#x20;
* Consultar el **historial** de transferencias anteriores.&#x20;
* Crear **new transfers** (nuevas transferencias) desde la app de Finanzas.



![](<../../../../.gitbook/assets/Schermata 2022-02-09 alle 09.52.02.png>)

## **Token Balance (**Balance de tokens)

La sección de _Token Balance (_Balance de tokens) muestra el saldo de cada token que posee la organización.&#x20;

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62772c7d3a7e9ae190b0/file-eLUV9SRU2y.png)

## **Transfers (**Transferencias)

La sección muestra un historial de las transferencias pasadas que se han realizado mediante la Finance App, incluyendo información sobre la fecha de la transferencia, la dirección a la que se realizó o desde la que se realizó la transferencia, una referencia con contexto adicional sobre la transferencia y el monto de la misma.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62832c7d3a7e9ae190b1/file-5lFKotQ4xB.png)

### El historial de transferencias puede filtrarse por date (fecha), token symbol (símbolo de token) o transfer type (tipo de transferencia)

Vea los ejemplos siguientes.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a629604286364bc8f80c5/file-TXwf7noy6I.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62a52c7d3a7e9ae190b8/file-HWRr2HXIlA.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62b62c7d3a7e9ae190b9/file-vWgrnBRGM4.png)

**Para cada transferencia, puede hacer clic en el menú desplegable para obtener un enlace para ver la transacción en la blockchain (cadena de bloques) y así poder ver aún más detalles sobre la transferencia:**

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62c904286364bc8f80cc/file-Puf5b59tKe.png)

#### Si necesita exportar su historial de transferencias para contabilizarlo en otra aplicación, hay un botón de export (exportar) que puede utilizar para exportar un archivo CSV:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62e604286364bc8f80ce/file-wgYMOA7KJK.png)

## **New Transfer (**Nueva transferencia)

### **Depositar Fondos**

Para enviar fondos a su organización, puede crear un depósito utilizando la Finance App&#x20;

* Pulse el botón _**New Transfer**_ (Nueva transferencia).&#x20;
* Abra la pestaña \_**Deposit** \_ (\_Depósito \_.)&#x20;
* Seleccione el token que desea depositar.&#x20;
* Introduzca el monto.&#x20;
* Introduzca una nota de referencia (opcional).&#x20;
* A continuación, haga clic en el botón _**Submit** deposit_ (Enviar depósito).

{% hint style="info" %}
En el caso de los tokens que no son ETH, pueden ser necesarias dos transacciones para realizar un depósito.&#x20;

La primera transacción autoriza a la Finance App a extraer el importe del depósito del saldo de su cuenta, y la segunda transacción es la del depósito propiamente dicho.&#x20;

Se trata de una función de seguridad para evitar que la Finance App extraiga más fondos de su cuenta de los que usted ha autorizado explícitamente.
{% endhint %}

### Retirar fondos

Para crear una nueva transferencia de su organización a otra dirección, puede crear un retiro utilizando la Finance App

* Haga clic en el botón _**New Transfer**_ (Nueva transferencia).&#x20;
* Abra la pestaña _**Withdrawal**_\*\* \*\* (Retiro).&#x20;
* Introduzca la dirección a la que desea realizar la transferencia. Introduzca el token que desea enviar.&#x20;
* Introduzca la cantidad de tokens que desea enviar.&#x20;
* Añada (opcionalmente) una nota de referencia para dar más contexto a la transferencia.

Una vez que haya rellenado toda esta información, puede hacer clic en el botón _**Submit transfer**_ (Enviar transferencia) para completar la acción, si tiene permiso para hacerlo.

![Retirada de fondos - App de Finanzas](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a63252c7d3a7e9ae190c4/file-L9njobkDLU.png)

### Firmar la transacción para crear el voto de la Nueva Transferencia

Como se mencionó anteriormente, todas las acciones en la organización de la empresa requieren el voto de los titulares de tokens. Haga clic en _**Create transaction**_ (Crear transacción) y luego abra su proveedor de Ethereum para firmar y enviar la transacción que crea el voto de la Nueva Transferencia.

![](https://lh3.googleusercontent.com/UXQwChFz66jOLkHe2GvPoJ\_dTc0dWafDE1aUsgS6GVP47AlL\_RNwSvBTLzZqQDq4M8rxpts6acwsYr2MIO4dRBwjJ6S56h8G1-w9f5c\_FJAK8usZabmT5WbQvR5bqCCXPr-fiGiX)

### Votación de la transferencia

La transferencia debe ser aprobada por los poseedores de tokens. Vote _**Yes**_ (afirmativamente) para aprobar la transferencia y haga que los demás poseedores de fichas de la organización voten también.

![](https://lh3.googleusercontent.com/BYjI\_u7oOJgw6s6\_0IVRxQy\_AAkEHiuc8aQes9a71HZNEknuNwO8FttrpeszbMIXY2j6AV7FfytR-eUi4Y\_eoILA\_WGjHiCz1cYasmUfj\_A0uhmod3bkh1ezWT6IhfP0GmyFmVG7)

### La operación de voto se firma y se envía para aprobar la transferencia

Tras la confirmación, la transferencia se ejecutará.

![](https://lh4.googleusercontent.com/C86GPoGAqAHhOiN-534hCWcWFeLBfwv3gsnEZ\_aXKwbYeaj67c8nNnvb3\_AK5fEAwPm03a-btdc-mLNkdy\_u-ezuZQG-g7iAvtjfHFoBmZxpYLoukXi7FT88VWifr79\_L21sGjxC)
