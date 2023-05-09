# TAO Voting

{% hint style="info" %}
TAO se encuentra actualmente en el proceso de propuesta, y la demostración se someterá a votación por parte del titular de la ficha en el otoño.
{% endhint %}

## El comienzo...

Incialmente Aragon fue manejado centralmente por sus fundadores, **Luis Cuende** and **Jorge Izquierdo**. Con el liderazgo derivado de miles de horas de inversión con sudor, delegaron el trabajo directamente a los empleados que cumplieron con la visión central del liderazgo en un ["Desarrollo en cascada"](https://es.wikipedia.org/wiki/Desarrollo\_en\_cascada) de gobernanza.

A medida que pasaba el tiempo, Aragón pasó a una estrategia de votación tokenizada que permitía a los **poseedores de tokens** **votar sobre las decisiones** de la empresa. Los poseedores de tokens emiten votos en un enfoque de [democracia ponderada](https://es.wikipedia.org/wiki/Juego\_de\_mayor%C3%ADa\_ponderada) en el que 50 tokens equivalen a 50 votos, 500 tokens equivalen a 500 votos, etc... Este método ha facilitado oportunidades únicas para que nuevas ideas ingresen al ecosistema, sin embargo, en la práctica, uno de los mayores dilemas ha sido el compromiso. Tal vez una evolución de la [paradoja del voto](https://es.wikipedia.org/wiki/Paradoja\_de\_Condorcet) abordada hace más de 200 años por el pionero de la gobernanza [Nicolas de Condorcet](https://es.wikipedia.org/wiki/Nicolas\_de\_Condorcet) - Aragon (y muchos otros DAO) han redescubierto que para la mayoría de las personas el costo de votar excede sabiamente el valor de los resultados.&#x20;



## La transferencia de los fondos de Aragon

Para poner un punto más fino, en mayo de 2022 Aragón votó a favor de "[**T**ransferir los Fondos del Proyecto de Aragón a un DAO de Aragón Gobernado por (Delegado) ANT](https://voice.aragon.org/processes/#/0x21b2ea5345d2e0c941dd44ff4c43fc4683088b846ddb3234d1690b000000000e)**"** Esta decisión implica mover cientos de millones de dólares de un sistema de gobierno a otro en la cadena de bloques de Ethereum. En cualquier medida esto es "algo Importante" y una **oportunidad espectacular para presenciar y participar en un proceso de gobernanza** que nunca hubiera sido posible sin el acceso al conjunto de herramientas de blockchain ahora disponible.  Y, sin embargo, solo votaron 46 de [las 13,000 billeteras con tokens](https://etherscan.io/token/0xa117000000f279d81a1d3cc75430faa017fa5a2e), lo que representa menos del 4% del total de tokens emitidos. En la industria, esto a menudo se denomina "no ideal".™

No estamos solos en nuestro esfuerzo por aumentar el compromiso y mejorar los resultados. En muchas DAOs, la participación de votos en el rango del 1-3% es la norma, y ​​obtener un compromiso del 5-10% es casi inaudito. Una de las emocionantes ventajas de los mecanismos de votación digital es que nos brindan la oportunidad de explorar nuevos enfoques que los productos tradicionales de lápiz y papel nunca podrían considerar seriamente.

[Democracia líquida](https://es.wikipedia.org/wiki/Democracia\_l%C3%ADquida) es uno de esos sistemas que ha sido promovido en las últimas dos décadas por grupos como el [Partido Pirata de Alemania](https://es.wikipedia.org/wiki/Partido\_Pirata\_de\_Alemania) en un intento de aumentar la participación al **permitir que los usuarios deleguen su poder de voto** a otros usuarios temporalmente y para incentivar o coaccionar aún más a aquellos a quienes se les ha delegado autoridad para actuar, rompiendo así la paradoja.

> La siguiente imagen muestra un ejemplo de un voto democrático delegado en el que se producen varias capas de delegación. Por ejemplo, dos votantes delegan sus votos a un tercer votante, y luego ese votante delega los tres votos bajo su control a otro delegado que termina votando por una decisión o candidato.

<figure><img src="../../.gitbook/assets/Delegative_democracy,_proxy_voting,_liquid_democracy.png" alt=""><figcaption><p>Un ejemplo de voto democrático delegado</p></figcaption></figure>



En 2021 el equipo [Token Engineering Commons](https://tecommons.org/) lanzó un panel de configuración [https://config.tecommons.org/config/1](https://config.tecommons.org/config/1) para respaldar su trabajo en[ Conviction Voting ](https://medium.com/giveth/conviction-voting-a-novel-continuous-decision-making-alternative-to-governance-aa746cfb9475)(disponible solo en ingles) - un mecanismo experimental que aprovecha algunas de las oportunidades técnicas derivadas de herramientas de votación totalmente digitales tales como Aragón. Organizaron una serie de "Param Parties" que a su vez llevaron al lanzamiento de un token comunitario.

Con el avance de la votación para financiar la gobernanza descentralizada ([aprobar 72k para financiar la gobernanza descentralizada (dGov) S1 del 1 de mayo al 31 de agosto de 2022](https://voice.aragon.org/processes/#/0x21b2ea5345d2e0c941dd44ff4c43fc4683088b846ddb3234d1690b0000000008)), el equipo de dGov trabajó en una variedad de propuestas, incluida la decisión de trabajar con Blossom labs, General Magic para tomar el trabajo que habían hecho para TECommons y entregar un producto y proceso similar a ello para la comunidad de Aragon. El financiamiento y la supervisión fueron entregados por el subDAO ejecutivo con [notas de comunicación y presupuesto que se llevaron a cabo en el foro](https://forum.aragon.org/t/financial-proposal-demoing-a-tao-voting-dao/3622) (disponible actualmente solo en ingles).

[**L**a votación Tao](https://token--engineering--commons-gitbook-io.translate.goog/tec-handbook/governance/voting-tools-and-methods/tao-voting?\_x\_tr\_sl=auto&\_x\_tr\_tl=es&\_x\_tr\_hl=es-419&\_x\_tr\_pto=wapp)  es una variación de la democracia líquida desarrollada por [Token Engineering Commons](https://tecommons.org/) con un conjunto limitado de parámetros (Links disponibles actualmente solo en ingles):

* [Support Required](https://forum.aragon.org/t/tao-voting-support-required/3663) (Soporte Requerido)- Cuánto apoyo total se requiere para que se apruebe una propuesta
* [Minimum Quorum](https://forum.aragon.org/t/tao-voting-minimum-quorum/3664) (Quórum Mínimo)- Porcentaje mínimo de soporte de token requerido
* [Vote Duration](https://forum.aragon.org/t/tao-voting-execution-delay/3668) (Duración del Voto) - La duración de la votación (generalmente en días) de una propuesta
* [Execution Delay](https://forum.aragon.org/t/tao-voting-vote-duration/3665) (Retraso de Ejecución) - Cantidad de tiempo después de que se aprueba una propuesta para que ocurra la ejecución
* [Delegated Voting](https://forum.aragon.org/t/tao-voting-delegated-voting-period/3666) (Voto Delegado) - Este es el período de tiempo, dentro de la duración de la votación, en el que los delegados pueden emitir los votos que les han sido conferidos. Cuando finaliza este período, los delegados ya no pueden votar.
* [Quiet Ending](https://forum.aragon.org/t/tao-voting-quiet-ending-period-and-quiet-ending-extension/3667) (Final Silencioso)- Verifica los resultados invertidos durante la parte final de la duración de la votación y agrega más tiempo de votación en caso de un cambio.
* [Proposal and Challenge Deposit](https://forum.aragon.org/t/deposit-and-challenge-deposit/3669) (Propuesta y Depósito de Desafío) - Una cantidad fija de fondos utilizados como garantía necesaria para crear una propuesta
* [Settlement Period](https://forum.aragon.org/t/settlement-period/3670) (Periodo de Asentamiento) - si un individuo cree que cierta propuesta es maliciosa, contiene un error o no está alineada con el Pacto Comunitario, puede [desafiar la propuesta](https://forum.1hive.org/t/disputable-honey-pot-celeste-and-agreement-user-process/1343).

> Usando un tablero (imagen a continuación) con algunos parámetros en la pantalla, vamos a **involucrar a la comunidad** en una discusión sobre los valores y riesgos asociados con el **proceso delegado**.  Este tablero se vincula a discusiones sobre cada parámetro y sirve para ayudarnos a dar forma a la estructura de gobernanza de nuestra DAO en el futuro.

<figure><img src="../../.gitbook/assets/tao2.png" alt=""><figcaption><p>El tablero con algunos parámetros en la pantalla que usados para involucrar a la comunidad.</p></figcaption></figure>

Si bien estos parámetros no pretenden abarcar toda la amplitud de la posibilidad democrática líquida, nos brindan un punto de partida para explorar las oportunidades, los riesgos, los éxitos y los fracasos. Esperamos que trabaje con nosotros para arrojar luz sobre estas ideas y continuar con este trabajo de investigación viviente en progreso.



Hay cientos de excelentes artículos sobre el tema; aquí hay algunos:

* [La convergencia de delegaciones iterativas en democracia líquida en una red social ](https://arxiv.org/pdf/1904.05775.pdf)(disponible solo en ingles)
* [https://es.wikipedia.org/wiki/Democracia\_líquida](https://es.wikipedia.org/wiki/Democracia\_l%C3%ADquida)

