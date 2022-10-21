# Aviso de seguridad para organizaciones creadas antes de Aragon 0.8

[Los cambios](https://github.com/aragon/aragonOS/issues/549) en las reglas de consenso de la Ethereum Network (Red Ethereum), que se activaron con el hard fork de Estambul, han roto una funcionalidad clave en la forma en que las versiones pre-0.8 de los contratos inteligentes de Aragon manejan los depósitos de ETH desde otros contratos inteligentes.

El resultado es que después del hard fork de Estambul (ocurrido el 7 de diciembre de 2019), los depósitos de ETH enviados desde un contrato inteligente a los contratos inteligentes de Aragon pre-0.8 fallarán, y la transacción se revertirá. **En algunos casos, esto podría conducir a una pérdida permanente de fondos.** Adicionalmente, ciertas funcionalidades se romperán, lo que llevará a una mala experiencia para los usuarios de las organizaciones de Aragon.&#x20;

Las organizaciones creadas después del lanzamiento de Aragon 0.8 tendrán automáticamente una solución para este problema, y no es necesario realizar ninguna otra acción.&#x20;

<mark style="color:red;">**Se aconseja a las organizaciones creadas antes del lanzamiento de Aragón 0.8 (11 de septiembre de 2019) que migren sus activos y miembros a una nueva organización de Aragon**</mark> creada con versiones posteriores a 0.8 de los contratos de Aragon.&#x20;

Puede crear su nueva organización en [app.aragon.org](https://app.aragon.org), configurar los permisos de la nueva organización para reflejar la antigua organización, luego transferir la membresía, los fondos y otros activos a la nueva organización, y continuar donde quedo.&#x20;

Para más detalles, lea [este artículo](https://blog.aragon.org/istanbul-hard-fork-impact/) (disponible actualmente solo en inglés) en el blog del proyecto Aragon.
