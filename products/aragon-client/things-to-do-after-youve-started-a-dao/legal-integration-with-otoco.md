# Integração jurídica com a Otoco

{% hint style="info" %}
Porque às vezes você tem que viver no mundo real. Este é um tutorial para **adicionar um Delaware Series LLC padrão a um DAO cliente Aragon existente** , no entanto, deve funcionar com qualquer DAO com tokens ERC20.
{% endhint %}

Então você começou um novo Aragon DAO chamado Awesome Music, um selo musical descentralizado. Tudo está funcionando bem colaborando com pessoas online em diferentes países, mas logo você descobre que um músico de Música Clássica insiste em ter um contrato legal com sua gravadora DAO em vez de um acordo simbólico. Isso precisa que o DAO seja registrado no mundo legado como uma LLC. Mas como diabos eu faço isso? Nos deixe mostrar como!​

Aqui está o link para o DAO: [https://client.aragon.org/#/awsmmusic/](https://client.aragon.org/#/awsmmusic/) (Este cliente de exemplo está na Ethereum Mainnet).

![Exemplo de página inicial do painel do cliente Aragon](https://lh6.googleusercontent.com/9jPGBkFSqmTAGgzGafNHwJbn9RT6pdwpG7mMB-FJiv7aVwbesPPi5JkVLTds-IbXskzxQKTkwvi2loX372FyBw6orZVRVRtZUUPqyfJ39KSEcVjXw\_4-l9fRwNJ3OVE4DDxRXTzKWK4cmWe4LVLyDA)

Em seguida, clique em 'Atribuir Tokens' na área de navegação do menu à esquerda.

<figure><img src="../../../.gitbook/assets/Schermata 2022-08-31 alle 12.24.30.png" alt=""><figcaption><p>Página Aragon Client Tokens com o endereço da carteira dos titulares do token do cliente</p></figcaption></figure>

Aqui você pode ver alguns dos Token Holders, artistas que se inscreveram na Awesome Music.

Agora vamos para [Otoco](https://otoco.io/) , para criar um Legal Wrapper para o DAO:

![](https://lh6.googleusercontent.com/96D6ygT4pbD8\_WFZM3cLBAuPTib4OLDRTF4eAGhAQrdkG7\_9R8cukZLubjC6c1sA3d77bVO55NFR\_CbNz2u01e0u-\_fjeP4Mm-SH3vVApjJ3oGHYGbxz86O9q7P7VypNvYsou0s9DgZmqy6OKoRbiQ)

Segue o link [https://otoco.io/](https://otoco.io/) . Sinta-se à vontade também para praticar um pouco com o fluxo do aplicativo Otoco usando a rede de teste Goerli. Você pode precisar obter algum [ETH goerli para isso](https://goerlifaucet.com/).

Clique em 'Spin up your project now'.

Selecione 'Ethereum Mainnet' e clique em 'Começar na próxima tela'.

![](https://lh4.googleusercontent.com/gCbLVyz0bIefsqaiE4tbcSEJYp9Sildw9ljUh3WyYgolMJ8KVL3YMpL1G6LzhMboFhDkFl4w1SHPjkAEzUWVzTmXbml8eQrSe\_UI9SyEtRDaJVnQyO6gOvCrmIZGnWz8RVx07ysj5e14\_4ZGzqSgVA)

Selecione 'Só eu' e depois 'continuar'.

![](https://lh5.googleusercontent.com/TZG-OSJnh89laDPv25ZuyhlT5rY7k2JnyjkbjQJHBNPyRGR7PKzdRl09WD-OBQJVsion1klBbSkovtVSsxWf8FWapsCM0y-PqR6qQW-KYtBWTXYMCVgPi4kF7NB\_lTyahXf7XBSlN7P9zwKx1nDgjw)

No momento as únicas opções estão nos EUA.

Selecione 'verificar' e depois 'continuar'.

![](https://lh3.googleusercontent.com/Qn5t1VJtdoKKXT0tRLpbFoxj3rdD0uu6VdVw1tHKALmlVR6w5HVmA9S4WKV7yP-IdymEWwL-N5hX0UVzHRWrajppt85nTPkAUDoz-DKcHVsDrG2Z56vdC\_YRrHBb7RsFjr8J7Dvm5tM6CVGPLU2Lww)

Conecte a mesma conta de carteira que possui os tokens DAO e pressione 'conectar carteira'.

![](https://lh6.googleusercontent.com/GPiHnhh-D-YYh0huMOgvtDFObHSjCiHINzNYsoR3yYM4Od6-rSTrQqZVEEInYyeC53qDBjjXJ-3amRuS7G0Rrnvz\_k2SFmhLdi2ZR1w27Gc19qSPRR-4CrhamAscGm5U1TVhT2IiGjgE9hesDzLo\_w)

Pressione 'ativar empresa' e confirme tx no Metamask.

![](https://lh6.googleusercontent.com/GPiHnhh-D-YYh0huMOgvtDFObHSjCiHINzNYsoR3yYM4Od6-rSTrQqZVEEInYyeC53qDBjjXJ-3amRuS7G0Rrnvz\_k2SFmhLdi2ZR1w27Gc19qSPRR-4CrhamAscGm5U1TVhT2IiGjgE9hesDzLo\_w)

No momento da redação, o ETH para cobrir as taxas de gás era de cerca de 5 USD.

Aguarde o tx ser minerado...

Clique em 'Ir para o Painel'.

![](https://lh4.googleusercontent.com/C98NFdD89dpROjRsSmIZRieZYRhhN91Ib1EsSyctibGqbCvXLSQ1YI04cUVCoEe2R2ShlDtIxfipH0X\_5wVzMjv-nr5RhtjYoc9yEo6Vla4PS77aTAnh4Ia9Ab6X8JVnSPF9t0G3tC0scD\_cVQknew)

{% hint style="success" %}
Ótimo, agora temos **um wrapper legal preparado para nosso DAO** ! Agora vamos vinculá-lo ao Aragon DAO!
{% endhint %}

![](https://lh6.googleusercontent.com/zlhj1jPsksD2U-nVVIvy3Fw5d5tP1XBkOnlBz10y9PgmV3Ppdwq6OMdTvRUWJg8WrgJAqrpP4t\_LP4JjdEh-m-y48AJtlKym3P3QCBdrP\_c7TP7R0kqJ4ZWSuqmL6ESjDHe29aHTYQ3xcmo7-PXmOg)

Clique em fichas.

![](https://lh3.googleusercontent.com/bAPONMEYctecwAz1iuoV69fooidqnBWzN4vwTJ7dLNTvQ3jTmSGRZlvc6TzdwixKr0AfZP5ph6UMaMhQnzsEe5QKHTehU-telIokGfhxdAM83j2LlWiiG24oQgwxSZ5BY\_3fUxkWsgIVQ1mLTm\_zGA)

Agora vamos vincular os tokens Awesome Music ao wrapper legal.

Vá para o Aragon DAO e copie o endereço do token lá.

![](https://lh5.googleusercontent.com/\_WiX29-5Epl0w\_W3yhzm2gN0kT3RM\_pNQLCnPL9zrdMIAW9a16HZ8-4QHmRCvZIxCOkeaoeWAWodTwWRwV8q4hWmSLgjSGZ0q-Zz55iLOwGitGYXwFyJWo1Z4U4KRZJ9p8pGxy-A\_93a4iMwUyOHIw)

Clique no nome do token.

Em seguida, copie o endereço.

![](https://lh6.googleusercontent.com/9VQfuaOJybeuxC16STkB9HWnzmvnDDHbfFUDz6evfo88uZsvrKR\_KD7Z2wBP3tpvukjGSJYq4CN6HN457QiX0pnOzsLm2l3zYigiXH0ZhTR\_QKQfi\_-gj5scutxPREHLFMgTdD8\_wgzAFtx2q0ZwrQ)

Cole o endereço na caixa de token do link erc-20 e pressione 'anexar token'.

![](https://lh3.googleusercontent.com/AHlOW8oSbNiq7T9h-Xrb5wt\_ofVCtyPmSMY5u8Sw4t82ZkzrCdq6Tlzox41tj3qQYGsfOx6Y536f8omA659cbrkiQeiL789veF4IF2UnncKY4K-SYhk08vq68dBSyzkF9a7--dRbf7bSPdM8xiRIHg)

Confirme a transação Metamask e espere que ela seja minerada.

![](https://lh3.googleusercontent.com/3SE87L4YicNC\_HKdT9KalZJXu2I5apLQQsXqt4sN6vHyhyXHTp23oefPcRtbJ681YvTeDz2uHpgtKPoF2QGIzcmf1U2569GOUI0LA8qvPL3kKpOZISYpCcTsPaRpIK8narWQqwfd9KUgoTYWTguk0A)

{% hint style="success" %}
Impressionante, o **invólucro legal da Otoco agora foi vinculado ao Aragon DAO** !
{% endhint %}

![](https://lh4.googleusercontent.com/a7JKZUo0IspMEOhHbxJOdNwJu27Jz8NYcKBdkYZrhQGCpBRMTh-EFHOxKLJaLPL3qDziiM67ilBSFD5ZPFJ-Jbjoq2mWxGDYGp8zQTBihQi2fLMPcnwDswZlxA\_l2ASHHvkueHpQuy1lK29NSa3WXg)

Clique em 'show' para ver todos os titulares de tokens Awesome Music aparecerem:

![](https://lh3.googleusercontent.com/U3U6qAWIzlefNpidi1dEEqXqLmu5XB2dlo7Lq4yRGeaxJiM72lKeUR93OMtAEbxnHrDgTxarq-3QvRz\_Q2JEmSHyFVL4hBFe5hhR9QUd4DMD\_KdlGpxqfU2mJ1ez8Z17KR5KeQao1wu\_7wH62pSnjw)

Agora, se voltarmos ao Aragon DAO, você pode ver que todos os detentores de tokens estão representados no Legal Wrapper.

![](https://lh4.googleusercontent.com/g-NoIu1y3lP6fLPCptcSmj3szpAZv7rgBYMblACdj12eD-OmzSuJpY5JPGzn5mgoX3O0yugiFqrR1JzCqK0iyD3hkWyu5NQsLetm8Jqv8yOXgbfKN6ordhbXJ0iPEazp5cQdhbpqBLjCiM15xHiWVw)

Também os documentos oficiais da LLC, como o Certificado de Constituição. Clique em Arquivos. Você pode baixar os documentos aqui.
