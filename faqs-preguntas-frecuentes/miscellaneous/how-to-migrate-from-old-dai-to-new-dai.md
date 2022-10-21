# Cómo migrar del "antiguo" DAI al "nuevo" DAI

El token DAI, gestionado por [MakerDAO](https://makerdao.com) (disponible en inglés), fue migrado para utilizar otra dirección de token a las 16:00 UTC del 18/11/2019.&#x20;

Puedes leer más sobre los detalles específicos de la migración en el [blog de MakerDAO](https://blog.makerdao.com/multi-collateral-dai-is-live/) (disponible actualmente solo en inglés).

* El antiguo token DAI en 0x89d24a6b4ccb1b6faa2625fe562bdd9a23260359 ahora se convierte en **SAI**.&#x20;
* El nuevo contrato de tokens **DAI multicolateral** es 0x6b175474e89094c44da98b954eedeac495271d0f&#x20;

Una herramienta de migración entre SAI y DAI está disponible en [migrate.makerdao.com](https://migrate.makerdao.com) (disponible actualmente solo en inglés).&#x20;

Para cualquier organización que tenga el token "antiguo" de DAI (también conocido como SAI), el Aragon Client (Cliente Aragon) ha comenzado a mostrar el nombre correcto después de un lanzamiento alrededor de 2019-11-25.

Para las organizaciones que poseen SAI, hay dos vías recomendadas para pasar a la DAI multicolateral:&#x20;

* Transferir el SAI a una cuenta externa o a un contrato multisig que usted controle. A partir de ahí, utilice la interfaz de migración en [migrate.makerdao.com](https://migrate.makerdao.com) para cambiar el SAI por el DAI, y deposite el nuevo DAI de nuevo en su organización.
* Instale la [Agent App (App de Agente)](../../productos/aragon-client/explore-template-dao/what-are-apps/agent-app/), si su organización aún no ha instalado una. Transfiera la SAI a la aplicación Agente, configure los permisos necesarios para permitir las interacciones con la Agent App y utilice [migrate.makerdao.com](https://migrate.makerdao.com) (disponible actualmente solo en inglés) a través de [Frame](https://frame.sh) (disponible actualmente en inglés).

Para las organizaciones que tengan antiguos SAI de Collateralized Debt Position (CDP) (Posición de Deuda Colateralizada), las rutas de migración recomendadas son similares si la organización solo mantenía SAI: transfiera la propiedad del CDP de SAI de la organización a una cuenta externa, multisig, o a la Agent App (App de Agente) instalada con la que pueda interactuar, y utilice la interfaz [migrate.makerdao.com](https://migrate.makerdao.com). En este caso, asegúrese de que la cuenta con la propiedad del CDP de DAI también tiene suficientes $MKR para pagar las tarifas de estabilidad adeudadas.&#x20;

Las organizaciones que quieran crear nuevas DAI Vaults (Bóvedas de DAI) deben interactuar con la aplicación Oasis Trade usando la Agent App (App de Agente) y un Frame instalados.
