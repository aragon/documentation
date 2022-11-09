# Modelo de empresa

{% hint style="info" %}
Nesta seção, você aprenderá como criar uma DAO de empresa usando o modelo de empresa no _Aragon Client_.
{% endhint %}

{% hint style="danger" %}
Antes de começar, assegure-se de ter lido [Como criar uma DAO](./).
{% endhint %}

## O que é uma organização de empresa? <a href="#what-is-a-company-organization" id="what-is-a-company-organization"></a>

Uma organização de empresa é uma organização que usa tokens transferíveis para representar participação na empresa. As decisões são tomadas usando votação ponderada por token, onde um token é igual a um voto.

## Como criar uma DAO de empresa <a href="#create-a-company-dao" id="create-a-company-dao"></a>

Clique em _**Ver detalhes**_, revise os aplicativos disponíveis, marque as caixas para instalar os aplicativos opcionais que deseja instalar. Quando terminar, clique em _**Usar este modelo**_.

![Selecione o modelo](<../../../.gitbook/assets/Schermata 2022-02-04 alle 18.41.40.png>)

![Modelo de empresa](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d86242f04286364bc8f6507/file-QeXiahqUec.png)

## Solicite um nome <a href="#claim-a-name" id="claim-a-name"></a>

Selecione o nome da sua DAO e preencha a guia _Nome da Organização._ Aragon usa o [Ethereum Name Service](https://ens.domains/) (ENS) para atribuir nomes a organizações.

{% hint style="warning" %}
Este nome será usado para acessar sua DAO. Não se esqueça disso!
{% endhint %}

![Selecione um nome pela DAO](<../../../.gitbook/assets/Schermata 2022-02-04 alle 18.52.45.png>)

## Configure os parâmetros do Aplicativo Votação <a href="#configure-the-parameters-of-the-voting-app" id="configure-the-parameters-of-the-voting-app"></a>

{% hint style="info" %}
Os parâmetros do "aplicativo votação" atualmente não podem ser alterados no front-end do _Aragon Client_. Para alterar os parâmetros do "aplicativo votação" após a criação da sua organização, você deve primeiro inicializar as permissões para alterar esses parâmetros e, em seguida, pode alterar os parâmetros usando o [aragonCLI](https://hack.aragon.org/developers/tools/aragoncli) .
{% endhint %}

### Defina as configurações de votação <a href="#configure-the-voting-settings" id="configure-the-voting-settings"></a>

#### A porcentagem de suporte <a href="#the-support-percentage" id="the-support-percentage"></a>

É a porcentagem relativa de tokens que são necessários para votar _**Sim**_ para que uma proposta seja aprovada. Por exemplo, se o _**Suporte**_ estiver definido como 50%, mais de 50% dos tokens usados ​​para votar em uma proposta devem votar _**Sim**_ para que ela seja aprovada.

#### A porcentagem mínima de aprovação <a href="#the-minimum-approval-percentage" id="the-minimum-approval-percentage"></a>

É a porcentagem do fornecimento total dos tokens necessária para votar _**Sim**_ em uma proposta para que ela possa ser aprovada. Por exemplo, se a _**Aprovação Mínima**_ for definida como 20%, mais de 20% do fornecimento total dos tokens deverá votar _**Sim**_ em uma proposta para que ela seja aprovada.

#### A duração do voto <a href="#the-vote-duration" id="the-vote-duration"></a>

É o período de tempo que a votação ficará aberta para participação. Por exemplo, se a Duração da votação for definida como 24 horas, os detentores dos tokens terão 24 horas para participar na votação.

![Defina as configurações de votação](<../../../.gitbook/assets/Schermata 2022-02-04 alle 19.01.42.png>)

## Configure os parâmetros do Aplicativo Token <a href="#configure-the-parameters-of-the-token-app" id="configure-the-parameters-of-the-token-app"></a>

Escolha um nome pelo token, um símbolo, os detentores de tokens e a quantidade (saldo) dos tokens para cada detentor. Você pode adicionar o detentor de tokens usando o botão _**Adicionar mais**_.

{% hint style="warning" %}
O nome do token e o símbolo atualmente não podem ser alterados. Não adicione mais do que alguns detentores de tokens à sua organização nesta tela ou a transação para criar sua organização pode falhar. Você pode adicionar mais detentores de tokens após a criação da organização.
{% endhint %}

![Configurações do Aplicativo Token](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624862c7d3a7e9ae173e4/file-wSKI8WfAzK.png)

## Revise as informações da organização <a href="#review-organization-information" id="review-organization-information"></a>

Abra cada painel para assegurar-se de que as informações inseridas para iniciar a sua organização estejam corretas. Se algo estiver incorreto, você pode clicar no botão _**Voltar**_ para retornar a uma tela anterior e fazer a correção necessária.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624af04286364bc8f650a/file-QLxk1Q0FZj.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624b704286364bc8f650b/file-IsP1SOVaHO.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624bf2c7d3a7e9ae173e5/file-Qn8KEkg3If.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624c604286364bc8f650c/file-Fqvyo6L3Kz.png)

## Lance a sua organização <a href="#launch-your-organization" id="launch-your-organization"></a>

Agora você precisa assinar uma transação para criar a sua organização. Abra seu provedor Ethereum se a janela não abrir automaticamente. Clique no botão **\_confirmar**\_ no seu provedor Ethereum para assinar e transmitir a transação.

Aguarde até que a transação seja concluída.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624d704286364bc8f650d/file-arEtXF8S0j.png)

Não feche ou atualize a página até que o processo seja concluído e a DAO seja implantada.

## Clique em "Começar" <a href="#click-get-started" id="click-get-started"></a>

{% hint style="success" %}
A sua nova organização de empresa está pronta!
{% endhint %}

Agora você pode [explorar a sua nova organização de empresa](../explore-template-dao/).

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624ee04286364bc8f650e/file-a4bAYgLmxU.png)

{% hint style="info" %}
Se a sua DAO não abrir automaticamente, vá [aqui](../../../faq/products/aragon-client/where-is-my-dao.md) e veja como acessá-la.
{% endhint %}



> <mark style="color:purple;">**Você tem uma pergunta? Deixe seus comentários aqui no nosso fórum Discourse**</mark>** 👇**

{% embed url="https://support.aragon.org/t/aragon-client-company-template/32/2" %}
