# Integración legal con Otoco

{% hint style="info" %}
Porque a veces tienes que vivir en el mundo real. Este es un tutorial para **agregar un Delaware Series LLC estándar a un DAO** de Aragon Client existente; sin embargo, debería funcionar con cualquier DAO con tokens ERC20.
{% endhint %}

Así que empezo una nueva DAO de Aragón llamada Awesome Music, un sello discográfico descentralizado. Todo funciona bien al colaborar con personas en línea en diferentes países, pero pronto descubre que un músico de música clásica insiste en tener un contrato legal con su sello DAO en lugar de un acuerdo simbólico. Eso necesita que la DAO esté registrada en el mundo heredado como una LLC. Pero, ¿cómo hago eso? ¡Permítanos mostrarle cómo!​

Aquí está el enlace a la DAO: [https://client.aragon.org/#/awsmmusic/](https://client.aragon.org/#/awsmmusic/) (Este cliente de ejemplo está en Ethereum Mainnet).

![Muestra de la página de inicio del panel de control del cliente de Aragón](https://lh6.googleusercontent.com/9jPGBkFSqmTAGgzGafNHwJbn9RT6pdwpG7mMB-FJiv7aVwbesPPi5JkVLTds-IbXskzxQKTkwvi2loX372FyBw6orZVRVRtZUUPqyfJ39KSEcVjXw\_4-l9fRwNJ3OVE4DDxRXTzKWK4cmWe4LVLyDA)

Luego haga clic en 'Asignar tokens' en el área de navegación del menú de la izquierda.

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption><p>Página de tokens de clientes de Aragon con la dirección de la billetera de los titulares de tokens de clientes</p></figcaption></figure>

Aquí puede ver algunos de los Token Holders, artistas que se registraron en Awesome Music.

Ahora vamos a [Otoco](https://otoco.io/) (disponible actualmente solo en inglés), para crear un Legal Wrapper para la DAO:

![](https://lh6.googleusercontent.com/96D6ygT4pbD8\_WFZM3cLBAuPTib4OLDRTF4eAGhAQrdkG7\_9R8cukZLubjC6c1sA3d77bVO55NFR\_CbNz2u01e0u-\_fjeP4Mm-SH3vVApjJ3oGHYGbxz86O9q7P7VypNvYsou0s9DgZmqy6OKoRbiQ)

Aquí está el enlace [https://otoco.io/](https://otoco.io/). Siéntase libre de practicar un poco con el flujo de la aplicación Otoco utilizando la red de prueba Goerli. Es posible que necesite obtener algo [de goerli ETH para esto](https://goerlifaucet.com/) (disponible actualmente solo en inglés).

Haga clic en 'Spin up your project now (Gire su proyecto ahora)'.

Seleccione 'Ethereum Mainnet' y haga clic en 'Get started on next screen (Comenzar en la siguiente pantalla)'.

![](https://lh4.googleusercontent.com/gCbLVyz0bIefsqaiE4tbcSEJYp9Sildw9ljUh3WyYgolMJ8KVL3YMpL1G6LzhMboFhDkFl4w1SHPjkAEzUWVzTmXbml8eQrSe\_UI9SyEtRDaJVnQyO6gOvCrmIZGnWz8RVx07ysj5e14\_4ZGzqSgVA)

Seleccione 'Just me (Solo yo)' y luego 'continue (continuar)'.

![](https://lh5.googleusercontent.com/TZG-OSJnh89laDPv25ZuyhlT5rY7k2JnyjkbjQJHBNPyRGR7PKzdRl09WD-OBQJVsion1klBbSkovtVSsxWf8FWapsCM0y-PqR6qQW-KYtBWTXYMCVgPi4kF7NB\_lTyahXf7XBSlN7P9zwKx1nDgjw)

Por el momento las únicas opciones están en USA.

Seleccione 'check (verificar)' y luego 'continue (continuar)'.

![](https://lh3.googleusercontent.com/Qn5t1VJtdoKKXT0tRLpbFoxj3rdD0uu6VdVw1tHKALmlVR6w5HVmA9S4WKV7yP-IdymEWwL-N5hX0UVzHRWrajppt85nTPkAUDoz-DKcHVsDrG2Z56vdC\_YRrHBb7RsFjr8J7Dvm5tM6CVGPLU2Lww)

Conecte la misma cuenta de billetera que posee los tokens DAO y presione 'connect wallet (conectar billetera)'.

![](https://lh6.googleusercontent.com/GPiHnhh-D-YYh0huMOgvtDFObHSjCiHINzNYsoR3yYM4Od6-rSTrQqZVEEInYyeC53qDBjjXJ-3amRuS7G0Rrnvz\_k2SFmhLdi2ZR1w27Gc19qSPRR-4CrhamAscGm5U1TVhT2IiGjgE9hesDzLo\_w)

Presione 'activate company (activar compañía)', y confirme tx en Metamask.

![](https://lh6.googleusercontent.com/GPiHnhh-D-YYh0huMOgvtDFObHSjCiHINzNYsoR3yYM4Od6-rSTrQqZVEEInYyeC53qDBjjXJ-3amRuS7G0Rrnvz\_k2SFmhLdi2ZR1w27Gc19qSPRR-4CrhamAscGm5U1TVhT2IiGjgE9hesDzLo\_w)

Al momento de escribir, el ETH para cubrir las tarifas de gas era de alrededor de 5 USD.

Espere a que tx sea minado...

Haga clic en 'Go to Dashpanel (Ir al panel de control)'.

![](https://lh4.googleusercontent.com/C98NFdD89dpROjRsSmIZRieZYRhhN91Ib1EsSyctibGqbCvXLSQ1YI04cUVCoEe2R2ShlDtIxfipH0X\_5wVzMjv-nr5RhtjYoc9yEo6Vla4PS77aTAnh4Ia9Ab6X8JVnSPF9t0G3tC0scD\_cVQknew)

{% hint style="success" %}
¡Genial, ahora tenemos **un envoltorio legal preparado para nuestra DAO** ! ¡Ahora vinculémoslo al DAO de Aragon!
{% endhint %}

![](https://lh6.googleusercontent.com/zlhj1jPsksD2U-nVVIvy3Fw5d5tP1XBkOnlBz10y9PgmV3Ppdwq6OMdTvRUWJg8WrgJAqrpP4t\_LP4JjdEh-m-y48AJtlKym3P3QCBdrP\_c7TP7R0kqJ4ZWSuqmL6ESjDHe29aHTYQ3xcmo7-PXmOg)

Haga clic en tokens (fichas).

![](https://lh3.googleusercontent.com/bAPONMEYctecwAz1iuoV69fooidqnBWzN4vwTJ7dLNTvQ3jTmSGRZlvc6TzdwixKr0AfZP5ph6UMaMhQnzsEe5QKHTehU-telIokGfhxdAM83j2LlWiiG24oQgwxSZ5BY\_3fUxkWsgIVQ1mLTm\_zGA)

Ahora vamos a vincular los tokens de Awesome Music al envoltorio legal.

Vaya a la DAO de Aragon y copie allí la dirección del token.

![](https://lh5.googleusercontent.com/\_WiX29-5Epl0w\_W3yhzm2gN0kT3RM\_pNQLCnPL9zrdMIAW9a16HZ8-4QHmRCvZIxCOkeaoeWAWodTwWRwV8q4hWmSLgjSGZ0q-Zz55iLOwGitGYXwFyJWo1Z4U4KRZJ9p8pGxy-A\_93a4iMwUyOHIw)

Haga clic en el nombre del token.

Luego copie la dirección.

![](https://lh6.googleusercontent.com/9VQfuaOJybeuxC16STkB9HWnzmvnDDHbfFUDz6evfo88uZsvrKR\_KD7Z2wBP3tpvukjGSJYq4CN6HN457QiX0pnOzsLm2l3zYigiXH0ZhTR\_QKQfi\_-gj5scutxPREHLFMgTdD8\_wgzAFtx2q0ZwrQ)

Pegue la dirección en el cuadro del token del enlace erc-20 y presione 'attach token (adjuntar token)'.

![](https://lh3.googleusercontent.com/AHlOW8oSbNiq7T9h-Xrb5wt\_ofVCtyPmSMY5u8Sw4t82ZkzrCdq6Tlzox41tj3qQYGsfOx6Y536f8omA659cbrkiQeiL789veF4IF2UnncKY4K-SYhk08vq68dBSyzkF9a7--dRbf7bSPdM8xiRIHg)

Confirme la transacción de Metamask y espere a que sea minada.

![](https://lh3.googleusercontent.com/3SE87L4YicNC\_HKdT9KalZJXu2I5apLQQsXqt4sN6vHyhyXHTp23oefPcRtbJ681YvTeDz2uHpgtKPoF2QGIzcmf1U2569GOUI0LA8qvPL3kKpOZISYpCcTsPaRpIK8narWQqwfd9KUgoTYWTguk0A)

{% hint style="success" %}
¡Impresionante, el **envoltorio legal de Otoco ya está vinculado al DAO de Aragón**!
{% endhint %}

![](https://lh4.googleusercontent.com/a7JKZUo0IspMEOhHbxJOdNwJu27Jz8NYcKBdkYZrhQGCpBRMTh-EFHOxKLJaLPL3qDziiM67ilBSFD5ZPFJ-Jbjoq2mWxGDYGp8zQTBihQi2fLMPcnwDswZlxA\_l2ASHHvkueHpQuy1lK29NSa3WXg)

Haga clic en 'show (mostrar)' para ver aparecer todos los poseedores de tokens de Awesome Music:

![](https://lh3.googleusercontent.com/U3U6qAWIzlefNpidi1dEEqXqLmu5XB2dlo7Lq4yRGeaxJiM72lKeUR93OMtAEbxnHrDgTxarq-3QvRz\_Q2JEmSHyFVL4hBFe5hhR9QUd4DMD\_KdlGpxqfU2mJ1ez8Z17KR5KeQao1wu\_7wH62pSnjw)

Ahora, si volvemos a la DAO de Aragón, usted puede ver que todos los titulares de tokens están representados en el Legal Wrapper (Envoltura Legal).

![](https://lh4.googleusercontent.com/g-NoIu1y3lP6fLPCptcSmj3szpAZv7rgBYMblACdj12eD-OmzSuJpY5JPGzn5mgoX3O0yugiFqrR1JzCqK0iyD3hkWyu5NQsLetm8Jqv8yOXgbfKN6ordhbXJ0iPEazp5cQdhbpqBLjCiM15xHiWVw)

También los documentos oficiales de LLC como el Certificado de formación. Haga clic en Archivos. Puede descargar los documentos aquí.
