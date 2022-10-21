# Configurar un monedero MultiSig



{% hint style="info" %}
En esta sección, veremos cómo las DAOs de Cliente de Aragon pueden ser gestionadas por un monedero MultiSig.
{% endhint %}

{% hint style="info" %}
Aquí vamos a utilizar [Gnosis Safe MultiSig](https://gnosis-safe.io) (disponible actualmente solo en inglés), sin embargo, podría seguir un enfoque similar para cualquier otro monedero MultiSig que soporte la interacción de contratos.
{% endhint %}

## Requisitos previos

### Asigne los permisos deseados en la DAO del cliente al MultiSig

{% hint style="info" %}
Las DAOs de Cliente de Aragon tienen acceso a un sistema de control, donde cada acción está protegida por un conjunto de registros de permisos. Solo alguien con permisos específicos puede actuar. Por eso necesitamos asignar al monedero MultiSig un rango de permisos que se correspondan con las acciones deseadas. Puede leer más sobre esto [aquí](aragon-client/explore-template-dao/system-setting/permissions-setting.md).
{% endhint %}

1\. Siga los siguientes pasos para asignar el permiso a un MultiSig.

2\. Abra el portal de su DAO y seleccione la pestaña de **Permissions (**_**permisos)**_ a la izquierda. Aquí puede examinar los permisos que tiene dentro de su DAO.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6112718fb55c2b04bf6dce7e/file-DCOHNWElgt.png)

3\. Para añadir un nuevo permiso, pulse el botón _**New Permission (Nuevo permiso)**_**.**

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611272116ffe270af2a97627/file-D7HYuaQgTh.png)

4\. Seleccione la App para la que desea crear el permiso en el menú desplegable de la aplicación.

5\. Seleccione a qué entidad se le asignará el nuevo permiso en el campo \_**Assign To Entity** \_ (_Asignar a entidad)_. Para añadir la dirección MultiSig seleccione _**Custom Address** (Dirección Personalizada)_ e introduzca la dirección en el campo inferior.&#x20;

6\. Selecciona la acción a la que queremos conceder el permiso. En nuestro caso, estamos asignando permiso a un MultiSig para crear nuevos votos dentro de nuestra DAO.

7\. Pulse _**Add Permission** (Añadir permiso)_. Esto podría crear una votación dependiendo de la estructura de su DAO y de quién sea el administrador de permisos de esta acción.

8\. Revoque los permisos no deseados. Para ello, expanda cualquier permiso y pulse sobre el icono de la papelera.

{% hint style="danger" %}
Por favor tenga cuidado, ya que los permisos incorrectos pueden hacer que su DAO sea vulnerable o inaccesible.
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611275a7b37d837a3d0e2535/file-AecSpNvGSO.png)

Resultados:

![Multisig Permissions](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d0ef364a230081ba1ce2f/file-aDCnpa7wjo.png)

{% hint style="info" %}
Aquí hemos asignado a MutliSig permisos para gestionar los pagos y cambiar los parámetros de apoyo a la votación dentro del DAO. Sin embargo, como hemos mantenido la votación como gestor de permisos, los miembros de la comunidad podrán votar para eliminar estos permisos, revocando efectivamente este control de MultiSigs sobre la DAO.
{% endhint %}

### Ejecución de acciones

1\. Ve al sitio web de [Gnosis Safe](https://gnosis-safe.io) (disponible actualmente solo en inglés) y conéctate a su DApp.&#x20;

2\. Abra su bóveda.

3\. Pulse el botón _**New Transaction** (Nueva transacción)_ y seleccione _**Contract Interaction** (Interacción con el contrato)_.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d0efb766e8844fc34e2c5/file-ery56Brop6.png)

4\. Indique la dirección de la App de Aragon con la que desea interactuar.

Puede encontrarla en la página de _**Organizations** (Organizaciones)_ de su portal DAO. Mire la sección \_**Installed Aragon Apps** \_ (_Aplicaciones de Aragón instaladas)_ allí.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d1014766e8844fc34e2cd/file-8cuqErvYC1.png)

5\. Esto rellenará automáticamente el campo ABI. Elimine el contenido que apareció allí.

6\. Busque el contrato base de la aplicación de Aragon seleccionada con la que desea interactuar.

* Abra la dirección que ha utilizado en el paso 4 en [etherscan](https://etherscan.io) (disponible actualmente solo en inglés)
* Ir a _**Contract** (Contrato)_&#x20;
* Seleccione _**Read contract** (Leer contrato)_
* Desplegar _**Implementation** (Implementación)_&#x20;
* Abra la dirección que aparece en _**Implementation** (_Implementación) en [etherscan](https://etherscan.io) (disponible actualmente solo en inglés)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d115d766e8844fc34e2ce/file-g3POvBnP7e.png)

7\. Copie el ABI de la dirección abierta en el campo del paso 5.

* Ir a _**Contract** (Contrato)_&#x20;
* Seleccione el _**Code** (código)_&#x20;
* Localizar el _**Contract ABI** (ABI del contrato)_
* Copiar el ABI en el campo de entrada de Gnosis Safe ABI

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d12f1766e8844fc34e2d7/file-nCgkCpoDAD.png)

8\. Seleccione el método que desea utilizar y rellene los parámetros.

Aquí crearemos un nuevo pago inmediato desde la app de Finanzas. Transferirá **0,1 ETH** (representado por una dirección de token 0x0..0) a la dirección 0x424..

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611277e1766e8844fc34f0ab/file-xlkaRMNQ6n.png)

9\. Pulse _**Review** (Revisar)_ y _**Submit** (Enviar)_. Después de que suficientes personas firmen la transacción, podrá verla en Etherscan y una vez que haya sido confirmada debería tener efecto en el DAO.

## Posibles problemas

{% hint style="warning" %}
Asegúrese de tener los permisos para invocar este método desde la dirección de Gnosis Safe.
{% endhint %}

{% hint style="warning" %}
Si la estimación del gas ha fallado y recibe advertencias, es probable que haya habido un error en los permisos, los parámetros del método o la dirección ABI y del contrato. Por favor, repase la configuración de nuevo.
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611278276ffe270af2a97644/file-rxfkptmQt8.png)

{% hint style="warning" %}
Si está rellenando números fraccionarios, añada 18 ceros al valor original. Por ejemplo, si quiere invocar el método _**immediateTransfer**_ que transferirá 10,5 tokens, tendrá que introducir 10,5\*10^18 = 10500000000000000000 en el campo de cantidad.
{% endhint %}

{% hint style="warning" %}
Si el ABI no se muestra en una red (Rinkeby, por ejemplo), obtenga el ABI similar de otro DAO en una red diferente (Ethereum Mainnet, por ejemplo).
{% endhint %}

> <mark style="color:purple;">**¿Tiene alguna pregunta? Deje sus comentarios aquí en nuestro foro Discourse (disponible actualmente solo en inglés)**</mark>** 👇**

{% embed url="https://support.aragon.org/t/web3-multisig-wallet/17/2" %}
