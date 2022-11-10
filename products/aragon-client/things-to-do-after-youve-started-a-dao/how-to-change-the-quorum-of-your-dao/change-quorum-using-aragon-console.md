# Como alterar o Quorum usando o Console Aragon

{% hint style="info" %}
Este guia mostrará como alterar o Quorum mínimo (participação) necessário para que os votos na sua DAO sejam aprovados usando o Aragon Console.
{% endhint %}



Abra sua DAO, adicionando `/console`  ao final do endereço web da sua DAO. A URL ficaria assim:`https://client.aragon.org/#/<your-dao-name>/console`

{% hint style="warning" %}
Substitua `<your-dao-name>`pelo nome da sua DAO na URL acima
{% endhint %}



Você deve ver algo como o abaixo:

<figure><img src="../../../../.gitbook/assets/immagine1.png" alt=""><figcaption></figcaption></figure>

Depois selecione `Exec` qual é um comando usado para realizar transações DAOs.

Agora você deve ver a tela abaixo. Selecione `Voting`, pois você criará uma alteração no _aplicativo Votação_:

<figure><img src="../../../../.gitbook/assets/immagine2.png" alt=""><figcaption></figcaption></figure>

No código fonte do _aplicativo Votação_ no [​​Github](https://github.com/aragon/aragon-apps/blob/631048d54b9cc71058abb8bd7c17f6738755d950/apps/voting/contracts/Voting.sol) você pode encontrar uma função para alterar a Porcentagem de Quorum mínima aceita, exatamente o que precisamos:

```solidity
function changeMinAcceptQuorumPct(uint64 _minAcceptQuorumPct)
    external
    authP(MODIFY_QUORUM_ROLE, arr(uint256(_minAcceptQuorumPct), uint256(minAcceptQuorumPct)))
{
    require(_minAcceptQuorumPct <= supportRequiredPct, ERROR_CHANGE_QUORUM_PCTS);
    minAcceptQuorumPct = _minAcceptQuorumPct;

    emit ChangeMinQuorum(_minAcceptQuorumPct);
}
```

Agora vamos chamar essa função do Console Aragon. Teremos que adicionar `changeMinAcceptQuorumPct(uint64 _minAcceptQuorumPct)` ao comando no Console, mas primeiro vamos substituir `uint64 _minAcceptQuorumPct` pela porcentagem de Quorum mínima desejada.

Isso é expresso como uma porcentagem de `10^18`, então por exemplo `100% = 10^18` e `1% = 10^16`. Digamos que você queira um novo Quorum mínimo de 25%, então você precisa adicionar 16 zeros a 25 chegando a `250000000000000000`

{% hint style="danger" %}
**Aviso**

A **Porcentagem de Quorum mínima nunca pode ser maior que a Porcentagem de Suporte necessária** para votos na sua DAO! Portanto, assegure-se de que a porcentagem de Suporte necessária da sua DAO seja de 55% ou mais. Senão, use uma porcentagem menor do que a porcentagem de Suporte necessária para este tutorial (caso contrário, você terá um problema mais tarde).
{% endhint %}

Agora adicione `changeMinAcceptQuorumPct(250000000000000000)` ao comando no Console:

<figure><img src="../../../../.gitbook/assets/immagine 3.png" alt=""><figcaption></figcaption></figure>

Quando você pressiona '_Enter_', uma transação deve aparecer no seu provedor Web3 (Metamask para a maioria dos usuários). Verifique se a Porcentagem de Quorum mínima corresponde ao que você tinha em mente:

<figure><img src="../../../../.gitbook/assets/immagine4.png" alt=""><figcaption></figcaption></figure>

Clique em '_Criar transação_' e assine com seu provedor Web3.

Você está quase lá! Mas primeiro acesse o _aplicativo Votação_, pois essa alteração gerou um voto automaticamente. Agora você (e o suficiente dos membros da sua DAO) precisa aprovar a votação para que ela seja aceita:

<figure><img src="../../../../.gitbook/assets/immagine5.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
**Aviso**

A mudança só poderá ser **decretada** quando o tempo restante de votação se esgotar. No caso deste exemplo, `Time remaining`é`23H:59M:12S`☝​
{% endhint %}

Quando o tempo de votação se esgotar, clique em '_Aprovar esta votação'_ e assine a transação com seu provedor Web3:

<figure><img src="../../../../.gitbook/assets/immagine6.png" alt=""><figcaption></figcaption></figure>

Feito isso, a Porcentagem de Quórum mínima deveria ter sido ajustada para 25%. Você pode verificar isso criando um novo voto. Quando você abre a votação, o `MINIMUM APPROVAL` deveria ter sido ajustado para `>25% needed`.

{% hint style="success" %}
Se você chegou até aqui, parabéns!👏​
{% endhint %}

> <mark style="color:purple;">**Você tem uma pergunta? Deixe seus comentários aqui no nosso fórum Discourse**</mark>** 👇**

{% embed url="https://support.aragon.org/" %}
