# Usando o modelo de reputação

{% hint style="info" %}
Nesta seção, você aprenderá como criar um DAO de reputação usando o modelo de reputação no cliente Aragon.
{% endhint %}

{% hint style="danger" %}
Antes de começar, certifique-se de ter lido [Como criar um DAO](./).
{% endhint %}

Uma organização de reputação é uma organização que usa **tokens não transferíveis** para representar a reputação. As decisões são tomadas por meio **de votação ponderada pela reputação** .

## Criando um DAO de reputação <a href="#creating-a-reputation-dao" id="creating-a-reputation-dao"></a>

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.02.19.png>)

Clique em _**Ver detalhes**_ , revise os aplicativos disponíveis, marque as caixas para instalar os aplicativos opcionais que deseja instalar. Quando terminar, clique em _**Usar este modelo**_.

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.22.29.png>)

## Reivindicar um nome <a href="#claim-a-name" id="claim-a-name"></a>

Selecione o nome do seu DAO e preencha a guia _**Organization Name**_ \*\* \*\*. Aragon usa o [Ethereum Name Service](https://ens.domains/) (ENS) para atribuir nomes às organizações.

{% hint style="warning" %}
Este nome será útil para acessar seu DAO. Não se esqueça disso!
{% endhint %}

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.23.36.png>)

## Configure os parâmetros do Voting App <a href="#configure-the-parameters-of-the-voting-app" id="configure-the-parameters-of-the-voting-app"></a>

{% hint style="info" %}
Os parâmetros do aplicativo Voting atualmente não podem ser alterados no cliente front-end Aragon. Para alterar os parâmetros do aplicativo Voting após a criação da sua organização, você deve primeiro inicializar as permissões para alterar esses parâmetros e, em seguida, pode alterar os parâmetros usando o [aragonCLI](https://hack.aragon.org/developers/tools/aragoncli).
{% endhint %}

### Defina as configurações de votação <a href="#configure-the-voting-settings" id="configure-the-voting-settings"></a>

#### A porcentagem de suporte <a href="#the-support-percentage" id="the-support-percentage"></a>

É é a porcentagem relativa de tokens que são necessários para votar _**Sim**_ para que uma proposta seja aprovada. Por exemplo, se _**o Suporte**_ for definido como 50%, mais de 50% dos tokens usados ​​para votar em uma proposta devem votar _**Sim**_ para que ela seja aprovada.

#### A porcentagem mínima de aprovação <a href="#the-minimum-approval-percentage" id="the-minimum-approval-percentage"></a>

É a porcentagem do fornecimento total de tokens necessária para votar _**Sim**_ em uma proposta antes que ela possa ser aprovada. Por exemplo, se a _**Aprovação Mínima**_ for definida como 20%, mais de 20% do fornecimento de token pendente deverá votar _**Sim**_ em uma proposta para que ela seja aprovada.

#### A duração do voto <a href="#the-vote-duration" id="the-vote-duration"></a>

É o período de tempo que a votação ficará aberta para participação. Por exemplo, se a Duração da votação for definida como 24 horas, os detentores de tokens terão 24 horas para participar da votação.

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.08.36.png>)

## Configure os parâmetros do Token App <a href="#configure-the-parameters-of-the-token-app" id="configure-the-parameters-of-the-token-app"></a>

Escolha um nome de token, um símbolo, os detentores de token e o valor (saldo) de token para cada detentor de token. Você pode adicionar o titular do token usando o botão _**Adicionar mais**_.

{% hint style="warning" %}
O nome do token e o símbolo atualmente não podem ser alterados. Não adicione mais do que alguns detentores de token à sua organização nesta tela ou a transação para criar sua organização pode falhar. Você pode adicionar mais detentores de token após a criação da organização.
{% endhint %}

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.25.03.png>)

## Revise as informações da organização <a href="#review-organization-information" id="review-organization-information"></a>

Abra cada painel para certificar-se de que as informações inseridas para iniciar sua organização estejam corretas. Se algo estiver incorreto, você pode clicar no botão _**Voltar**_ para retornar a uma tela anterior e fazer a correção necessária.

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.25.54.png>)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.26.03.png>)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.26.14.png>)

## Lançar sua organização <a href="#launch-your-organization" id="launch-your-organization"></a>

Agora você precisa assinar uma transação para criar sua organização. Abra seu provedor Ethereum se a janela não abrir automaticamente. Clique no botão _**confirmar**_ em seu provedor Ethereum para assinar e transmitir a transação.

Aguarde até que a transação seja concluída.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624d704286364bc8f650d/file-arEtXF8S0j.png)

Não feche ou atualize a página até que o processo seja concluído e o DAO seja implantado.

## Clique em "Começar" <a href="#click-get-started" id="click-get-started"></a>

{% hint style="success" %}
Sua nova organização de Reputação está pronta!
{% endhint %}

Agora você pode [explorar sua nova organização de reputação](../explore-template-dao/).

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.17.04.png>)

{% hint style="info" %}
Caso seu DAO não abra automaticamente, acesse [aqui](../../../faq/products/aragon-client/where-is-my-dao.md) e veja como acessar.
{% endhint %}

> <mark style="color:purple;">**Você tem uma pergunta?Deixe seus comentários aqui em nosso fórum do Discurso**</mark>** 👇**

{% embed url="https://support.aragon.org/t/aragon-client-reputation-template/33/2" %}
