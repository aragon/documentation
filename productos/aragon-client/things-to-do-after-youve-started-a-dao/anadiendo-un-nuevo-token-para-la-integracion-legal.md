# Añadiendo un nuevo token para la integración legal

{% hint style="info" %}
En esta sección, **mostramos cómo Aragon podría interactuar con una entidad legal como una Delaware C-Corp**. En nuestro ejemplo, el DAO de Aragon apalanca **Gnosis Safe y EVM-CRISPR** también, para mostrar cómo un DAO existente podría tener acceso a las entidades legales.
{% endhint %}

## Introducción

Los envoltorios legales son un tema desafiante, y en aras de la claridad el autor aquí no es un abogado ni da consejos legales... el objetivo en este trabajo es mostrar un ejemplo de cómo Aragon podría interactuar con una LLC, sin embargo, este ejemplo no pretende servir como un proceso necesariamente útil, y más bien como un punto de partida para la crítica....

## Inicio rápido

Cree su DAO empezando por [aquí](https://client.aragon.org/) (disponible actualmente solo en inglés). Para este ejemplo, he creado un [DAO de reputacion de Aragon.](../how-to-create-a-dao-using-aragon-client/page-1.md)\


![DAO básica con una DAO de reputación - se utiliza porque estos tokens deben ser intransferibles](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.35.12 PM.png>)

## Acuña su Token

A continuación, diríjase a [EVM CRISPR](https://evm-crispr.blossom.software/#/terminal) (disponible actualmente solo en inglés), donde puedes introducir un código para acuñar un nuevo token.

* Conecte su cartera&#x20;
* Limpie la consola&#x20;
* Copie y pegue estos comandos

```
connect your-dao-here token-manager voting 
new token "Test Token" TEST token-manager:new
install token-manager:new token:TEST true 0
grant voting token-manager:new MINT_ROLE voting
grant voting token-manager:new BURN_ROLE voting
exec token-manager:new mint @me 100e18
```

* Haga clic en el comando forward (avance) y firme la transacción en su cartera&#x20;
* Una vez confirmada la transacción, haz clic en "_Go Vote_" ("ir a votar") y vota en su DAO

![EVM CRISPR](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.10.14 PM.png>)

![Votar en su transacción EVM CRISPR](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.32.09 PM.png>)

Ahora que ha creado sus nuevos tokens puede verlos en su lista de tokens.\


![Este es nuestro DAO](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.11.44 PM.png>)

## Envoltura legal para su DAO Aragon

Ahora pasamos a [Gnosis](https://gnosis-safe.io) (disponible actualmente solo en inglés), donde vamos a unir los puntos.

* Cree una Gnosis safe vault (Bóveda de Gnosis) (para más ayuda vaya [aquí](https://help.gnosis-safe.io/en/articles/3876461-create-a-safe)) y deposite algunos fondos en su Bóveda para firmar las transacciones.&#x20;
* Cargue la aplicación Otoco&#x20;
* Nombre su empresa y elige entre las DAOs de Delaware, UNA y Wyoming.&#x20;
* _Approve Payment_ (Apruebe el pago) y _Activate the Company_ (active la empresa)

Los principales pasos se muestran en las siguientes imágenes.

![Crear una bóveda en gnosis](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.04.21 PM.png>) ![Cargar la aplicación Otoco](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.04.31 PM.png>) ![Ponerle nombre a su empresa y elegir entre las DAO de Delaware, UNA y Wyoming](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.05.46 PM (1).png>) ![¡Elegir su sabor y menta!
](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.05.58 PM (1).png>)

Si ve un mensaje como este "your entity smart contract is not a wallet" ("tu contrato inteligente de entidad no es un monedero"), vaya a la página "_Asset wallet_" ("Monedero de activos") y añada un propietario (una _Wallet address -_ dirección de monedero o una _Gnosis Safe Address -_ dirección de Gnosis Safe).

![](<../../../.gitbook/assets/Schermata 2022-06-07 alle 14.50.29.png>)

A continuación, vaya a la página de _Tokens_ y copie y pegue la dirección de su token (puede encontrarla en la [página de organización](../explore-template-dao/system-setting/organization-setting.md) de su DAO).

![Transfiera los tokens de su DAO a su Otoco LLC](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.11.31 PM.png>)

Ahora tiene una LLC de Delaware con tokens acuñadas en Aragon.

![](<../../../.gitbook/assets/Screen Shot 2022-06-01 at 8.15.49 PM.png>)





> <mark style="color:purple;">**¿Tiene alguna pregunta? Deje sus comentarios aquí en nuestro foro Discourse (disponible actualmente en inglés)**</mark>**  👇**

{% embed url="https://support.aragon.org/t/aragon-client-legal-wrappers/173" %}
