# Alterar Quorum usando EVMcrispr

{% hint style="info" %}
Este guia mostrará como alterar o Quorum mínimo (participação) necessário para que os votos em seu DAO sejam aprovados usando [**EVMcrispr**](https://evm-crispr.blossom.software/#/).

O EVMcrispr é uma ferramenta poderosa que combina uma linguagem específica de domínio com uma biblioteca Javascript para interagir com os DAOs da Aragon.
{% endhint %}

Primeiro, abra o EVMcrispr [aqui](https://evm-crispr.blossom.software/#/) e clique em 'Abrir Terminal'. Agora, esta tela deve aparecer:

<figure><img src="../../../../.gitbook/assets/crisper1.png" alt=""><figcaption></figcaption></figure>

Em seguida, exclua todo o texto no terminal:

<figure><img src="../../../../.gitbook/assets/crisper2.png" alt=""><figcaption></figcaption></figure>

Clique em 'Connect' (Conectar) para se conectar ao seu provedor Web3 (Metamask para a maioria dos usuários).

{% hint style="danger" %}
**Aviso**

Certifique-se de conectar uma conta ao EVMcrispr que também tenha permissão de assinatura no seu DAO.
{% endhint %}

Agora vamos escrever os comandos para alterar a Porcentagem de Quorum Mínima.

Para alterar a Porcentagem de Quorum mínima para seu DAO, você terá que se conectar ao seu DAO com `connect <dao-name-or-address`. Em seguida, adicionamos `token-manager voting`porque o `token-manager`aplicativo tem o `CREATE_VOTES_ROLE`necessário para encaminhar ações para `voting`o aplicativo com o qual iremos interagir. Isto é o que temos até agora:

```
connect <dao-name-or-address> token-manager voting
```

Agora vamos escrever a segunda linha de comando para o terminal EVMcrispr. O primeiro a adicionar é `exec`qual é um comando usado para realizar transações DAOs. Em seguida, adicionamos `voting`o aplicativo com o qual iremos interagir. Isto é o que temos até agora:

```
connect <dao-name-or-address> token-manager voting
exec voting
```

Não estamos prontos no entanto. Quando olhamos no código-fonte do Voting App no [​​Github](https://github.com/aragon/aragon-apps/blob/631048d54b9cc71058abb8bd7c17f6738755d950/apps/voting/contracts/Voting.sol) , podemos encontrar uma função para alterar a porcentagem de quorum mínima aceita, é exatamente isso que precisamos:

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

Agora adicionaremos esta função aos comandos para o terminal chamá-la. Teremos que adicionar `changeMinAcceptQuorumPct(uint64 _minAcceptQuorumPct)`, mas primeiro substituiremos `uint64 _minAcceptQuorumPct`pela porcentagem mínima de quórum desejada.

Isso é expresso como uma porcentagem de `10^18`, então por exemplo `100% = 10^18`e `1% = 10^16`. Digamos que você queira um novo Quorum mínimo de 25%, então você precisa adicionar 16 zeros a 25 chegando`250000000000000000`

{% hint style="danger" %}
**Aviso**

A **Porcentagem de Quorum mínima nunca pode ser maior que a Porcentagem de Suporte necessária** para votos em seu DAO! Portanto, certifique-se de que a porcentagem de suporte necessária do seu DAO seja de 55% ou mais. Caso contrário, use uma porcentagem menor do que a porcentagem de suporte necessária para este tutorial (caso contrário, você terá um problema mais tarde).
{% endhint %}

Agora adicione `changeMinAcceptQuorumPct 250000000000000000`aos comandos para o terminal:

```
connect <dao-name-or-address> token-manager voting
exec voting changeMinAcceptQuorumPct 250000000000000000
```

Os comandos estão prontos! Copie/cole-os no terminal e clique no botão 'Forward...':

<figure><img src="../../../../.gitbook/assets/crisper3.png" alt=""><figcaption></figcaption></figure>

Assine a transação do seu provedor Web3 e agora ela deve ser executada com sucesso.

{% hint style="danger" %}
**Aviso**

Use seu endereço DAO no caso de seu nome DAO no caso deste erro:

`Error: ENS <dao-name>.aragonid.eth not found in rinkeby, please introduce the address of the DAO instead.`
{% endhint %}

Estamos quase prontos, mas primeiro abra seu DAO no navegador da web. A url deve ser:

`https://client.aragon.org/#/<dao-name-or-address>`

Em seguida, vá para o aplicativo Voting, pois essa alteração gerou um voto automaticamente. Agora você (e o suficiente de seus membros DAO) precisa aprovar a votação para que ela seja aprovada:

<figure><img src="../../../../.gitbook/assets/crisper4.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
**Aviso**

A mudança só poderá ser **decretada** quando o tempo restante de votação se esgotar. No caso deste exemplo, `Time remaining`é`23H:59M:12S`☝​
{% endhint %}

Quando o tempo de votação se esgotar, clique em 'Aprovar esta votação' e assine a transação com seu provedor Web3:

<figure><img src="../../../../.gitbook/assets/crisper5.png" alt=""><figcaption></figcaption></figure>

​Feito isso, a Porcentagem de Quórum mínima deveria ter sido ajustada para 25%. Você pode verificar isso criando um novo voto. Quando você abre a votação, o `MINIMUM APPROVAL`deveria ter sido ajustado para `>25% needed`.

{% hint style="success" %}
Se você chegou até aqui, muito bem!👏​​
{% endhint %}

> <mark style="color:purple;">**Você tem uma pergunta?Deixe seus comentários aqui em nosso fórum do Discurso**</mark>** 👇**

{% embed url="https://support.aragon.org/" %}
