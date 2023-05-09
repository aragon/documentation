# Agent App (App de Agente)

## ¿Qué es la Agent App?

La **Agent App** permite a las organizaciones de Aragon **interactuar** directamente con cualquier **otro contrato inteligente** en Ethereum. Antes de Agent, una organización tenía que nombrar a una parte de confianza para interactuar con un contrato inteligente de Ethereum en su nombre.

{% hint style="info" %}
Por ejemplo, una organización enviaría algunos $DAI a uno de sus empleados, a quien se le confiaría el préstamo de los $DAI en Compound, ganaría intereses y luego enviaría los intereses más el monto principal de vuelta a la organización.
{% endhint %}

Ahora, con Agent, una organización puede prestar sus $DAI en Compound directamente, sin tener que confiar en ningún intermediario.

## ¿Cómo empezar a utilizar la Agent App?

La forma más fácil de empezar a utilizar la Agent App es **marcar la casilla** para instalarla opcionalmente cuando se crea la organización por primera vez:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bc80204286364bc8f9029/file-zLiYZ6kXSy.png)

{% hint style="info" %}
Tenga en cuenta que la instalación del Agente a través de una de las plantillas sustituirá la aplicación Vault que normalmente se incluye en las plantillas que no utilizan la aplicación Agente.
{% endhint %}

{% hint style="warning" %}
Si no instaló opcionalmente la aplicación Agente cuando creó su organización por primera vez, todavía puede instalarla después de que la organización haya sido creada. Para ello, deberá seguir [las instrucciones de instalación e inicialización de la Agent App mediante aragonCLI](https://github.com/aragon/aragon-apps). Tenga en cuenta que esta opción está orientada a los expertos.
{% endhint %}

## Interfaz de Agent

Actualmente, la **Agent App** tiene una **interfaz frontal de solo visualización** que puede utilizar para ver qué tokens tiene actualmente la Agent App (incluidos los tokens ERC-20, ERC-677 y ERC-777), así como para ver el historial de transacciones realizadas con la Agent App. El historial de transacciones puede filtrarse por tipo de transacción, token o fecha, y puede exportarse como archivo CSV.

![Página de la aplicación del agente](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5e8ce5d32c7d3a7e9aea8d19/file-r5322DPQHX.png)

La dirección del contrato inteligente de Agent está disponible en el menú _**System**_ (Sistema) de la página _**Organization**_ (Organización).

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bcdad2c7d3a7e9ae1a16d/file-pJP6dzQfhR.png)
