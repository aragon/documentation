# Aplicativo Tokens

O aplicativo Tokens é usado para **cunhar novos tokens** e **atribuí-los** a você ou a outras entidades. Os tokens cunhados pelo aplicativo Tokens **conferem habilidades de votação** aos detentores dos tokens.

Para obter instruções sobre como cunhar novos tokens com _EVM Crispr_, acesse aqui [https://docs.evmcrispr.blossom.software/aragonOS/token-manager/](https://docs.evmcrispr.blossom.software/aragonOS/token-manager/)

{% hint style="info" %}
#### O que é cunhagem? <a href="#what-is-minting" id="what-is-minting"></a>

Cunhagem _(minting)_ é o processo de criação de novos tokens. Você pode criar quantos tokens quiser (desde que os membros da organização estejam de acordo). Isso significa que você pode adicionar quantos novos usuários desejar à sua organização, basta criar novos tokens para eles. Abaixo, mostraremos "Como adicionar novos tokens" à sua organização.
{% endhint %}

## Razões para cunhar tokens para entidades <a href="#reasons-to-mint-tokens-for-entities" id="reasons-to-mint-tokens-for-entities"></a>

* A organização compromete-se a dar aos seus trabalhadores uma participação na empresa, por exemplo, metade dos tokens da empresa são detidos pelos trabalhadores e a outra metade por investidores.
* A organização cunha tokens para entidades proporcionalmente à quantidade de fundos que investiram na empresa.
* A organização cunha uma quantidade específica de tokens para uma entidade em troca de um bem ou serviço específico.
* A organização cunha uma quantidade fixa de tokens por mês e os distribui proporcionalmente a todos que contribuíram com valor para a organização naquele mês.

## Usando o aplicativo Tokens com diferentes modelos <a href="#using-tokens-app-with-different-templates" id="using-tokens-app-with-different-templates"></a>

O aplicativo Tokens é usado para **gerenciar a associação** e **o poder de voto** em uma organização. Para adicionar membros a uma organização, é tão fácil quanto cunhar e atribuir um token a eles.

Esse processo simples de gerenciamento de membros e poder de voto fornece a base para governar os recursos de uma organização que usa Aragon.

### Modelo de empresa <a href="#company-template" id="company-template"></a>

No modelo Empresa, um token equivale a um voto, os membros podem manter quantos tokens forem atribuídos a eles e os tokens são transferíveis.

### Modelo de associação <a href="#membership-template" id="membership-template"></a>

Com o modelo Associação, um token também equivale a um voto, mas os membros não podem ter mais de um token cada e os tokens são não transferíveis.

### Modelo de reputação <a href="#reputation-template" id="reputation-template"></a>

Em relação ao modelo de Reputação, um token equivale a um voto, e os membros podem manter quantos tokens forem-lhes atribuídos, mas os tokens são não transferíveis.

![Aplicativo Tokens](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d867d542c7d3a7e9ae174bd/file-3GPg0yG2o5.png)

## **Detentor (Holder)** <a href="#holder" id="holder"></a>

Na seção _Detentor_ (Holder_)_ do _aplicativo Tokens_, você pode ver a lista atual de detentores do token e o saldo de tokens da organização que cada um possui.

### Clicar no menu suspenso em uma das linhas da lista fornecerá opções para: <a href="#clicking-on-the-dropdown-menu-on-one-of-the-rows-in-the-list-will-provide-you-options-for" id="clicking-on-the-dropdown-menu-on-one-of-the-rows-in-the-list-will-provide-you-options-for"></a>

* Atribuir mais tokens a esse detentor do token (opção _Adicionar tokens_).
* Remover tokens do detentor de token (opção _Remover tokens_).
* Editar um rótulo personalizado (para saber mais sobre isso, clique [aqui](../home.md)).

![Tokens app view](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d867d622c7d3a7e9ae174be/file-dgpIXaBkm6.png)

## **Informações do token** <a href="#token-info" id="token-info"></a>

Na seção _**Informações do Token**_, você pode ver informações sobre o token usado para governança na sua organização.

### **Fornecimento de tokens** <a href="#token-supply" id="token-supply"></a>

Quantos tokens foram cunhados no total?

### **Transferível** <a href="#transferable" id="transferable"></a>

Se o token pode ou não ser transferido para outra entidade após ter sido atribuído.

### Símbolo <a href="#token" id="token"></a>

O nome do token e o símbolo do token.

![Visualização das informações do token](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d867df22c7d3a7e9ae174bf/file-7fiikNO0jj.png)

## **Distribuição de propriedade** <a href="#ownership-distribution" id="ownership-distribution"></a>

Na seção _**Distribuição de Propriedade**_, você pode ver quais entidades possuem qual porcentagem do fornecimento dos tokens da organização. Isso pode ser útil como uma verificação pontual para ver como a propriedade dos tokens está concentrada na organização.

![Distribuição de propriedade](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d867dff04286364bc8f65d9/file-nj7kpToblW.png)

## **Adicionar tokens** <a href="#add-tokens" id="add-tokens"></a>

Se você precisar adicionar membros à sua organização e atribuir tokens DAO a eles, será necessário usar a opção _**Adicionar token**_. Se você clicar no botão **\_Adicionar Tokens\_**, um painel será aberto com campos de texto para inserir:

* _**O destinatário**_: o endereço da entidade à qual você deseja atribuir tokens.
* _**Número de tokens**_: quantos tokens você deseja atribuir.

Depois de inserir essas informações, você pode clicar no botão do painel para concluir a ação.

![Adicionar tokens](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d867e382c7d3a7e9ae174c0/file-gQIE902ZlX.png)

### Neste ponto, a organização ainda exige um voto do detentor de tokens para cada ação. <a href="#at-this-point-the-organization-still-requires-a-token-holder-vote-for-every-action." id="at-this-point-the-organization-still-requires-a-token-holder-vote-for-every-action."></a>

Clique em _**Criar transação**_ para criar a transação que cria um **novo voto** para atribuir o novo token que você deseja cunhar. Assine a transação no seu provedor Ethereum, aguarde uma confirmação e passe para a próxima etapa.

![](https://lh3.googleusercontent.com/RVlpE5QIyKb2gvvr5KQOf8ukZa0k5wczXfgOnnHfcvXI2JnBUtLX4KjKob\_EWMF9k9y1NjB1yzNcYrJLm2ETRezy7v9DDWucQNQ18OEQT\_8dBjMvSoZsymVIGK\_BJv\_8Cw1Mk88L)

### Vote "Sim" para aprovar o voto "Atribuir Tokens" <a href="#vote-yes-to-approve-the-assign-tokens-vote" id="vote-yes-to-approve-the-assign-tokens-vote"></a>

Acesse o aplicativo Votação, clique na proposta de _**Cunhar tokens**_ que você acabou de criar e vote "Sim" para aprovar a cunhagem e a atribuição do token.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a553504286364bc8f7fff/file-qb1DOKAI56.png)

![](https://lh6.googleusercontent.com/OYlBJ41umTMbdfMLqS9geT8ycshlmUfUgPHz6pNkg9cwIx3zNKAb8elnfw0QAKpo5N9rpah\_vExxl2lJYQG3ChtEK-5evFmrDG\_C92IUjn6\_Gt1\_WD8sP2ntGPaiVAeo4jZrQq1\_)

![](https://lh5.googleusercontent.com/IJWz3XKDtHi4MlsuxGlLJ8zatP6RiAluev6UK72zn1kMlHkpzNMAZEGyqSxw\_sp5lRIwHNU5ErZI1F0tjh\_8yVfIx99ImrR3X\_Xy7DWd9MC8k\_nY9w4X5CVbH6EqwnR54SD3kBw7)

![](https://lh6.googleusercontent.com/SJXCuLvpm6UwVIvBsplOQCcH5mfm11meFrHj9HRVH1FOGiM\_ax8Wmzf4IoQtX2GJNSDLC7BrUn8RmdDuaZ0Vzd9fhH\_JT-TggnudmR\_408oQ6VC6N6JWZXi1Hc2SudTl\_Y1p0xzZ)

### **Confira o novo membro da sua organização** <a href="#check-out-the-newest-member-of-your-organization" id="check-out-the-newest-member-of-your-organization"></a>

{% hint style="success" %}
Sua organização acabou de passar de um para dois membros. Um bom começo para uma nova organização de Empresa!
{% endhint %}

{% hint style="warning" %}
* Se for emitido um voto que faça com que a % de Aprovação seja igual ou maior que o Suporte necessário (por exemplo, 60% de Suporte necessário com 65% de Aprovação atual), a proposta será concluída automaticamente.
* Se a % de Aprovação for menor que o Suporte necessário (por exemplo, 60% de Suporte necessário com 40% de Aprovação atual), então mais votos "não" ainda podem impedir que a proposta seja aprovada.

**Assim, a proposta permanecerá aberta até que a duração seja atingida ou a % de Aprovação seja igual ou maior que o requisito de Suporte.**
{% endhint %}

![](https://lh4.googleusercontent.com/DOedZ-Oj8ettsh6BPRTs7e7aY9ubI8k\_1R9oYcVTdiDouLo3coVdYI4s8pGTtZdHqw65aS1JgJ4ZTdQT77Unz86R9BvorceFOaebefJP9u1UJ2pfMY71PPZEerI3uVcGD\_CW13UA)

Se você estiver usando [https://evm-crispr.blossom.software/](https://evm-crispr.blossom.software/), poderá fazer coisas como atribuir tokens adquiridos a contas usando linha de código como a seguinte

```
connect <DAO> token-manager
exec token-manager assignVested <ACCOUNT> <AMOUNT>e18 <START-DATE> <CLIFF-DATE> <END-DATE> true
```

> <mark style="color:purple;">**Você tem uma pergunta? Deixe seus comentários aqui no nosso fórum Discourse**</mark>** 👇**

{% embed url="https://support.aragon.org/t/aragon-client-navigate-your-dao-token-app/26/2" %}
