# Modelo de associação

{% hint style="info" %}
Nesta seção, você aprenderá como criar uma DAO de associação usando o modelo de associação no _Aragon Client_.
{% endhint %}

{% hint style="danger" %}
Antes de começar, assegure-se de ter lido [Como criar uma DAO](./).
{% endhint %}



Uma organização de associação é uma organização que usa **tokens não transferíveis** para representar a associação. As decisões são tomadas com base na governança de "**um membro, um voto".**

## Como criar uma DAO de associação <a href="#creating-a-membership-dao" id="creating-a-membership-dao"></a>

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.02.19.png>)

Clique em _**Ver detalhes**_, revise os aplicativos disponíveis, marque as caixas para instalar os aplicativos opcionais que deseja instalar. Quando terminar, clique em _**Usar este modelo**_ .

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.03.48.png>)

## Solicite um nome <a href="#claim-a-name" id="claim-a-name"></a>

Selecione o nome da sua DAO e preencha a guia _**Nome da Organizaçã .**_ Aragon usa o [Ethereum Name Service](https://ens.domains/) (ENS) para atribuir nomes a organizações.

{% hint style="warning" %}
Este nome será usado para acessar sua DAO. Não se esqueça disso!
{% endhint %}

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.06.23.png>)

## Configure os parâmetros do Aplicativo Votação <a href="#configure-the-parameters-of-the-voting-app" id="configure-the-parameters-of-the-voting-app"></a>

{% hint style="info" %}
Os parâmetros do "aplicativo votação" atualmente não podem ser alterados no front-end do Aragon Client. Para alterar os parâmetros do "aplicativo votação" após a criação da sua organização, você deve primeiro inicializar as permissões para alterar esses parâmetros e, em seguida, pode alterar os parâmetros usando o [aragonCLI](https://hack.aragon.org/developers/tools/aragoncli).
{% endhint %}

### Defina as configurações de votação <a href="#configure-the-voting-settings" id="configure-the-voting-settings"></a>

#### A porcentagem de suporte <a href="#the-support-percentage" id="the-support-percentage"></a>

É a porcentagem relativa de tokens que são necessários para votar Sim para que uma proposta seja aprovada. Por exemplo, se o Suporte estiver definido como 50%, mais de 50% dos tokens usados ​​para votar em uma proposta devem votar Sim para que ela seja aprovada.

#### A porcentagem mínima de aprovação <a href="#the-minimum-approval-percentage" id="the-minimum-approval-percentage"></a>

É a porcentagem do fornecimento total dos tokens necessária para votar Sim em uma proposta para que ela possa ser aprovada. Por exemplo, se a Aprovação Mínima for definida como 20%, mais de 20% do fornecimento total dos tokens deverá votar Sim em uma proposta para que ela seja aprovada..

#### A duração do voto <a href="#the-vote-duration" id="the-vote-duration"></a>

É o período de tempo que a votação ficará aberta para participação. Por exemplo, se a Duração da votação for definida como 24 horas, os detentores dos tokens terão 24 horas para participar na votação.

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.08.36.png>)

## Configure os parâmetros do Aplicativo Token <a href="#configure-the-parameters-of-the-token-app" id="configure-the-parameters-of-the-token-app"></a>

Escolha um nome pelo token, um símbolo, os detentores de tokens e a quantidade (saldo) dos tokens para cada detentor. Você pode adicionar o detentor de tokens usando o botão Adicionar mais.

{% hint style="warning" %}
O nome do token e o símbolo atualmente não podem ser alterados. Não adicione mais do que alguns detentores de tokens à sua organização nesta tela ou a transação para criar sua organização pode falhar. Você pode adicionar mais detentores de tokens após a criação da organização..
{% endhint %}

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.10.13.png>)

## Revise as informações da organização <a href="#review-organization-information" id="review-organization-information"></a>

Abra cada painel para assegurar-se de que as informações inseridas para iniciar a sua organização estejam corretas. Se algo estiver incorreto, você pode clicar no botão Voltar para retornar a uma tela anterior e fazer a correção necessária.

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.10.59.png>)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.11.44.png>)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.11.57.png>)

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.12.17.png>)

## Lance a sua organização <a href="#launch-your-organization" id="launch-your-organization"></a>

Agora você precisa assinar uma transação para criar a sua organização. Abra seu provedor Ethereum se a janela não abrir automaticamente. Clique no botão _confirmar_ no seu provedor Ethereum para assinar e transmitir a transação.

Aguarde até que a transação seja concluída.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624d704286364bc8f650d/file-arEtXF8S0j.png)

Não feche ou atualize a página até que o processo seja concluído e a DAO seja implantada.

## Clique em "Começar" <a href="#click-get-started" id="click-get-started"></a>

{% hint style="success" %}
A sua nova organização de associação está pronta para começar!
{% endhint %}

Agora você pode [explorar a sua nova organização de associação](../explore-template-dao/).

![](<../../../.gitbook/assets/Schermata 2022-02-10 alle 15.17.04.png>)

{% hint style="info" %}
Caso a sua DAO não abra automaticamente, vá [aqui](../../../faq/products/aragon-client/where-is-my-dao.md) e veja como acessar.
{% endhint %}

> <mark style="color:purple;">**Você tem uma pergunta? Deixe seus comentários aqui no nosso fórum Discourse**</mark>** 👇**

{% embed url="https://support.aragon.org/t/aragon-client-membership-templates/34/2" %}
