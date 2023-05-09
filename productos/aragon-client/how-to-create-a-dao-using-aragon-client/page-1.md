# Utilizar la plantilla de reputación

{% hint style="info" %}
En esta sección, usted aprenderá a crear una DAO de reputación utilizando la plantilla de reputación en el Cliente Aragon.
{% endhint %}

{% hint style="danger" %}
Antes de empezar, asegúrese de haber leído [Como crear una DAO](./).
{% endhint %}

Una organización de reputación es una organización que utiliza **tokens intransferibles** para representar la reputación. Las decisiones se toman mediante una **votación ponderada por la reputación.**

## Creación de una Reputation DAO (DAO de reputación)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.02.19.png>)

Haga clic en _**View details** (Ver detalles)_, revise las aplicaciones disponibles, marque las casillas para instalar cualquier aplicación opcional que desee instalar. Cuando termine, haga clic en _**Use this template** (Usar esta plantilla)._

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.22.29.png>)

## Reclamar un nombre

Seleccione el nombre de su DAO y rellene la pestaña _**Organization Name**_\*\* \*\* (_Nombre de la organización)._ Aragon utiliza el [Servicio de nombres de Ethereum](https://ens.domains) (ENS) (en inglés) para asignar nombres a las organizaciones

{% hint style="warning" %}
Este nombre será útil para acceder a su DAO. No lo olvide.
{% endhint %}

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.23.36.png>)

## Configurar los parámetros de la Voting App (Aplicación de Votos)

{% hint style="info" %}
Actualmente, los parámetros de la App Voting no pueden cambiarse desde la parte frontal del Cliente Aragon. Para cambiar los parámetros de la Voting App después de que su organización haya sido creada, primero debe inicializar los permisos para cambiar estos parámetros, luego puede cambiar los parámetros usando el [aragonCLI](https://hack.aragon.org/developers/tools/aragoncli) (diponible actualmente solo en inglés).
{% endhint %}

### Configurar los ajustes de la votación

#### El porcentaje de apoyo

Es el porcentaje relativo de tokens que se requieren para votar _**Yes**_ (_Sí)_ para que una propuesta sea aprobada. Por ejemplo, si el _**Support** (Apoyo)_ se establece en el 50%, entonces más del 50% de los tokens utilizados para votar una propuesta deben votar _**Yes** (Sí)_ para que se apruebe.

#### El porcentaje mínimo de aprobación

Es el porcentaje del suministro total de tokens que se requiere para votar _**Yes** (Sí)_ a una propuesta antes de que pueda ser aprobada. Por ejemplo, si la _**Minimum Approval**_ (_Aprobación Mínima)_ se establece en el 20%, entonces más del 20% del suministro de tokens en circulación debe votar _**Yes** (Sí)_ a una propuesta para que sea aprobada.

#### La duración del voto

Es el tiempo que la votación estará abierta a la participación. Por ejemplo, si la duración de la votación se establece en 24 horas, los poseedores de tokens tendrán 24 horas para participar en la votación.

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.08.36.png>)

## Configurar los parámetros de la Token App&#x20;

Elija un nombre de token, un símbolo, los titulares/propietarios de los tokens y la cantidad (balance) de tokens para cada titular. Puede añadir el titular del token utilizando el botón _**Add more** (Añadir más)_.

{% hint style="warning" %}
El nombre y el símbolo de la ficha no se pueden cambiar actualmente. No añada más que unos pocos titulares de fichas a su organización en esta pantalla o la transacción para crear su organización puede fallar. Puede añadir más titulares de fichas una vez creada la organización.
{% endhint %}

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.25.03.png>)

## Revisar la información de la organización

Abra cada panel para asegurarse de que la información introducida para lanzar su organización es correcta. Si algo es incorrecto, puede hacer clic en el botón de _**back** (retroceso)_ para volver a una pantalla anterior y hacer la corrección necesaria.

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.25.54.png>)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.26.03.png>)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.26.14.png>)

## Lance su organización

Ahora necesitará firmar una transacción para crear su organización. Abra su proveedor de Ethereum si la ventana no se abre automáticamente. Haz clic en el botón \_**confirm** **\_** (confirmar) de su proveedor de Ethereum para firmar y emitir la transacción.

Espere a que se complete la transacción.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624d704286364bc8f650d/file-arEtXF8S0j.png)

No cierre o actualice la página hasta que el proceso se haya completado y el DAO se haya desplegado.

## Haga clic en "Get started" ("Empezar").

{% hint style="success" %}
Su nueva organización de la reputación está lista para funcionar.
{% endhint %}

Ahora puede [explorar su nueva organización de reputación](../explore-template-dao/).

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.17.04.png>)

{% hint style="info" %}
Si su DAO no se abre automáticamente, vaya [aquí](../../../faqs-preguntas-frecuentes/products/aragon-client/where-is-my-dao.md) y encuentre cómo acceder a ella.
{% endhint %}
