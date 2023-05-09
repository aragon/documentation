# Configuración de los permisos

{% hint style="info" %}
En esta sección, exploramos en profundidad la configuración de los permisos. Al final de esta página encontrará un vídeo dedicado a ello (disponible actualmente solo en inglés).
{% endhint %}

## ¿Qué es la Permissions App (App de Permisos)?

La _**Permissions App** (App de_ Permisos)\*\* \*\* se utiliza para ver todos los permisos actuales que se han establecido en una organización y añadir o eliminar permisos según sea necesario.&#x20;

Los permisos establecidos por la aplicación Permisos definen qué entidades tienen qué permisos para realizar diversas acciones en una organización.&#x20;

Por ejemplo, cualquier cuenta puede tener permiso para crear un voto, pero solo los titulares de tokens en una organización pueden tener permiso para emitir un voto.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a697f2c7d3a7e9ae19121/file-gDcISkpUXb.png)

## Buscar por aplicación

La Permissions App muestra una lista de todas las **aplicaciones instaladas** en la organización y **la dirección o símbolo de token** de esa aplicación. Puede cambiar los permisos de la aplicación y los permisos del sistema.

![Permissions App](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6a562c7d3a7e9ae1912e/file-0y5pgj1j2k.png)

![System permissions (Permisos del sistema)](../../../../.gitbook/assets/file-mnVytX0QZA.png)

### Cada aplicación tiene:

* una lista de **acciones que se pueden realizar** en la aplicación,&#x20;
* una lista de **acciones que otras entidades han recibido permiso para realizar** en la app,&#x20;
* una lista de **permisos que la aplicación tiene concedidos**.

{% hint style="info" %}
La imagen siguiente muestra la lista de acciones que puede realizar la _Finance App (App de_ finanzas) (columna _Action -_ Acción), las otras entidades que tienen los permisos para realizar estas acciones (columna _Assigned to entity -_ Asignado a la entidad) y quién tiene la autoridad para asignar el permiso a esta entidad (columna _Managed by -_ Gestionado por).
{% endhint %}

![Finance permissions example](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6a7104286364bc8f8145/file-NKD9Oqrl0V.png)

### Ejemplo

Si necesitamos realizar una acción de \_**Create new payments** \_ (_Crear nuevos pagos)_ en la App Finance (App de Finanzas), esta acción pasará por una votación en la App Voting (App de Votación). La razón es que la acción de crear nuevos pagos en la Finance App está asignada a la entidad de votación.

### Permisos disponibles

La sección de permisos disponibles muestra:&#x20;

* **qué acciones** se pueden realizar en la aplicación,&#x20;
* **qué entidad** tiene permiso para **realizar** cada acción,&#x20;
* **qué entidad gestiona** cada acción. Esta entidad se llama “manager” ("administrador").

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b052c7d3a7e9ae19132/file-68mYNPchqp.png)

Un **manager (administrador)** tiene la capacidad de **elegir qué entidades tienen permiso para realizar una acción** (_Assign Permission -_ Asignar permiso) y la capacidad de **cambiar el administrador de esa acción** (_Manage Role -_ Gestionar rol). Estas acciones pueden realizarse mediante el menú desplegable situado bajo los tres puntos.

![](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.25.57 (1).png>)

### Asignar permisos

Haga clic en el menú desplegable de los _tres puntos_ y seleccione _Assign Permission (_Asignar permiso). Seleccione una App en el menú _On App_, una entidad en el menú _Assign to Entity (_Asignar a Entidad) y una Action (Acción).

![Asignar un permiso](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.26.48.png>)

### Gestionar posición

Haga clic en el menú desplegable de los \*\* _tres puntos_ y **\_ seleccione\_**Manage Rol (_Gestionar rol/posición)\*\*._ Seleccione una actualización en el menú _**Update** (A_ctualizar)\*\* \*\*.

![Gestionar Permisos](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.37.21.png>)

{% hint style="warning" %}
Si un administrador se da de baja como administrador de permisos sin reasignar el rol de administrador a otra entidad, la administracion de esa acción se asigna por defecto a la entidad que gestiona la acción _**Create permissions**_ (Crear permisos) \*\* \*\* en la app ACL.&#x20;

En el ejemplo a continuación, la gestión de la acción se asignará a la Voting App.
{% endhint %}

![](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.12.59.png>)

{% hint style="danger" %}
Si el administrador de la acción se establece como 0x00000000000000000000000000000001 entonces no se podrá establecer un nuevo administrador y los permisos concedidos para esa acción quedarán bloqueados para siempre.
{% endhint %}

### Inicializar el permiso

Si una acción aún no tiene un administrador todavia, debe ser inicializada. Para inicializar una acción, introduzca la dirección (_Grant permission to -_ Conceder permiso a) de la entidad que desea gestionar la acción, seleccione a qué entidad desea conceder permiso para realizar la acción y, a continuación, haga clic en el botón _Initialize permission_ (Inicializar permiso) para inicializar el permiso, si tiene permiso para hacerlo.

![](../../../../.gitbook/assets/inizialize.png)

### Buscar por entidad

De vuelta en la página principal de Permisos, usted tiene la posibilidad de obtener una vista rápida de todos los permisos establecidos en una organización en la sección _Browse by entity_ (Examinar por entidad).&#x20;

Aquí puede ver rápidamente a qué entidades se les ha concedido permiso para realizar qué acciones en la organización.&#x20;

Al hacer clic en \*\* **\_**View details (_Ver detalles)\*\*\__ se accede a la página de permisos de esa entidad.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b6104286364bc8f8153/file-W609vjv1Pi.png)

### Añadir permiso

Para dar permiso a una entidad para realizar una acción en una aplicación, haga clic en el botón _**Add permission**_ (Añadir permiso), seleccione la aplicación en la que desea que la entidad realice la acción, seleccione la entidad a la que desea conceder el permiso y, a continuación, seleccione la acción a la que desea conceder permiso a la entidad.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b732c7d3a7e9ae1913a/file-xsxDomUDSy.png)

Cada aplicación tiene diferentes acciones que una entidad puede tener permiso para realizar.&#x20;

Conceder permiso a una entidad para realizar estas acciones en estas apps les permitirá:

#### **ACL (Access Control List) (Lista de Acceso de Control)**

* Crear permisos: crea permisos que aún no se han inicializado en ninguna aplicación que utilice esta instancia de ACL`*`.

> `*`_Estas acciones son muy sensibles y darán a la entidad con permiso para realizar estas acciones un control casi total de su organización._

#### **EVM (Ethereum Virtual Machine) Script Registry (**Registro de secuencias de comandos de la **Máquina Virtual de Ethereum)**&#x20;

* **Añadir ejecutores**: añadir un ejecutor a la organización`*`
* **Activar y desactivar ejecutores**: activar y desactivar ejecutores en una organización`*`.

> `*` Estas acciones son acciones muy sensibles que darán a la entidad con permiso para realizar estas acciones un control casi total de su organización.

{% hint style="warning" %}
Un ejecutor es un intérprete para ejecutar scripts en una organización. Todas las aplicaciones de una organización utilizan los ejecutores de la organización para ejecutar los scripts que forman parte de las transacciones enviadas a la aplicación. Cada script tiene un identificador que determina qué ejecutor se utiliza para ejecutar el script.&#x20;

Por ejemplo, cada vez que se envía una transacción de votación a la Voting App, la aplicación ejecuta un script y luego utiliza un ejecutor para ejecutar el script en la transacción. Puede encontrar más documentación sobre los ejecutores en el [Portal del Desarrollador de Aragon](https://hack.aragon.org/) (Disponible actualmente solo en inglés).
{% endhint %}

#### Kernel

* Gestionar aplicaciones: instalar aplicaciones, actualizar aplicaciones y cambiar las aplicaciones por defecto en una organización. La ACL y el Registro de Script de EVM son aplicaciones por defecto en la organización. Quien tenga permiso para realizar esta acción también puede cambiar el contrato Vault por defecto de la organización (que es la bóveda a la que se enviarán los tokens si estos se envían a la dirección de una app que no está destinada a aceptar depósitos de tokens).`*`

> `*` _Estas acciones son muy sensibles y darán a la entidad con permiso para realizarlas un control casi total de su organización._

**Tokens**

* Acumular tokens: crear nuevos tokens y transferirlos a una dirección especificada&#x20;
* Emitir tokens: crear nuevos tokens y transferirlos a la Tokens App de la organización, para su posterior asignación a una entidad determinada&#x20;
* Asignar tokens: transferir tokens de la Tokens App a una entidad determinada&#x20;
* Revocar la titularidad: revocar la titularidad de tokens de una entidad específica&#x20;
* Quemar tokens: eliminar los tokens en posesión de un titular de tokens, reduciendo el suministro total de tokens

**Votación**

* Crear nuevos votos: crear un nuevo voto&#x20;
* Modificar el apoyo: modificar el parámetro Apoyo&#x20;
* Modificar el quórum: modificar el parámetro % mínimo de aprobación

{% hint style="info" %}
El **% mínimo de aprobación** es el porcentaje de la oferta total de fichas que debe superar el apoyo a una propuesta para que esta se considere válida.&#x20;

**Ejemplo 1**

Si el % mínimo de aprobación se establece en el 20%, entonces más del 20% del suministro de tokens en circulación debe votar para aprobar una propuesta para que la votación se considere válida. Si una votación no alcanza el quórum, entonces fracasará, aunque hayan votado más tokens para aprobar la propuesta que en contra.&#x20;

**Ejemplo 2**

Si el % mínimo de aprobación se fija en el 20% y el 10% de la reserva de tokens vota en contra de la propuesta, pero solo el 15% vota a favor, la propuesta fracasará porque no ha alcanzado el umbral del % mínimo de aprobación.
{% endhint %}

{% hint style="info" %}
**Support (Apoyo)** es el porcentaje de votos de una propuesta que el apoyo total debe ser mayor para que la propuesta sea aprobada. Por ejemplo, si el "Apoyo" se establece en el 51%, entonces más del 51% de los votos de una propuesta deben votar "Sí" para que la propuesta sea aprobada.
{% endhint %}

**Finanzas**

* Crear nuevos pagos: crear una transferencia desde la Finance App a otra entidad
* Ejecutar pagos: desencadenar un pago recurrente que se debe a una entidad&#x20;
* Cambiar la duración del periodo: modificar la duración en segundos entre periodos contables
* Cambiar los presupuestos: modificar la cantidad de tokens que se pueden gastar en un periodo contable determinado
* Gestionar los pagos: activar y desactivar los pagos recurrentes

**Bóveda**

* Transferir los tokens de Vault (Bóveda): transferir los tokens en posesión de la Vault App

{% embed url="https://youtu.be/kMF7Y_KPm-4?t=666" %}
