# Usando o modelo da empresa

{% hint style="info" %}
Nesta seção, você aprenderá como criar um DAO de empresa usando o modelo de empresa no cliente Aragon.
{% endhint %}

{% hint style="danger" %}
Antes de começar, certifique-se de ter lido [Como criar um DAO](./).
{% endhint %}

## O que é uma organização empresarial? <a href="#what-is-a-company-organization" id="what-is-a-company-organization"></a>

Uma organização da empresa é uma organização que usa tokens transferíveis para representar participação na empresa. As decisões são tomadas usando votação ponderada por token, onde um token é igual a um voto.

## Criar um DAO da empresa <a href="#create-a-company-dao" id="create-a-company-dao"></a>

Clique em _**Ver detalhes**_ , revise os aplicativos disponíveis, marque as caixas para instalar os aplicativos opcionais que deseja instalar. Quando terminar, clique em _**Usar este modelo**_.

![Selecione o modelo](<../../../.gitbook/assets/Schermata 2022-02-04 alle 18.41.40.png>)

![Modelo de empresa](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d86242f04286364bc8f6507/file-QeXiahqUec.png)

## Reivindicar um nome <a href="#claim-a-name" id="claim-a-name"></a>

Selecione o nome do seu DAO e preencha a guia _Nome da Organização ._ Aragon usa o [Ethereum Name Service](https://ens.domains/) (ENS) para atribuir nomes a organizações.

{% hint style="warning" %}
Este nome será útil para acessar seu DAO. Não se esqueça disso!
{% endhint %}

![Selecione um nome DAO](<../../../.gitbook/assets/Schermata 2022-02-04 alle 18.52.45.png>)

## Configure os parâmetros do Voting App <a href="#configure-the-parameters-of-the-voting-app" id="configure-the-parameters-of-the-voting-app"></a>

Os parâmetros do aplicativo Voting atualmente não podem ser alterados no cliente front-end Aragon. Para alterar os parâmetros do aplicativo Voting após a criação da sua organização, você deve primeiro inicializar as permissões para alterar esses parâmetros e, em seguida, pode alterar os parâmetros usando o [aragonCLI](https://hack.aragon.org/developers/tools/aragoncli) .

### Defina as configurações de votação <a href="#configure-the-voting-settings" id="configure-the-voting-settings"></a>

#### A porcentagem de suporte <a href="#the-support-percentage" id="the-support-percentage"></a>

É é a porcentagem relativa de tokens que são necessários para votar _**Sim**_ para que uma proposta seja aprovada. Por exemplo, se _**o Suporte**_ estiver definido como 50%, mais de 50% dos tokens usados ​​para votar em uma proposta devem votar _**Sim**_ para que ela seja aprovada.

#### A porcentagem mínima de aprovação <a href="#the-minimum-approval-percentage" id="the-minimum-approval-percentage"></a>

É a porcentagem do fornecimento total de tokens necessária para votar _**Sim**_ em uma proposta antes que ela possa ser aprovada. Por exemplo, se a _**Aprovação Mínima**_ for definida como 20%, mais de 20% do fornecimento de token pendente deverá votar _**Sim**_ em uma proposta para que ela seja aprovada.

#### A duração do voto <a href="#the-vote-duration" id="the-vote-duration"></a>

É o período de tempo que a votação ficará aberta para participação. Por exemplo, se a Duração da votação for definida como 24 horas, os detentores de tokens terão 24 horas para participar da votação.

![Defina as configurações de votação](<../../../.gitbook/assets/Schermata 2022-02-04 alle 19.01.42.png>)

## Configure os parâmetros do Token App <a href="#configure-the-parameters-of-the-token-app" id="configure-the-parameters-of-the-token-app"></a>

Escolha um nome de token, um símbolo, os detentores de token e o valor (saldo) de token para cada detentor de token. Você pode adicionar o titular do token usando o botão _**Adicionar mais**_.

{% hint style="warning" %}
O nome do token e o símbolo atualmente não podem ser alterados. Não adicione mais do que alguns detentores de token à sua organização nesta tela ou a transação para criar sua organização pode falhar. Você pode adicionar mais detentores de token após a criação da organização.
{% endhint %}

![Configurações do aplicativo de token](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624862c7d3a7e9ae173e4/file-wSKI8WfAzK.png)

## Revise as informações da organização <a href="#review-organization-information" id="review-organization-information"></a>

Abra cada painel para certificar-se de que as informações inseridas para iniciar sua organização estejam corretas. Se algo estiver incorreto, você pode clicar no botão _**Voltar**_ para retornar a uma tela anterior e fazer a correção necessária.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624af04286364bc8f650a/file-QLxk1Q0FZj.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624b704286364bc8f650b/file-IsP1SOVaHO.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624bf2c7d3a7e9ae173e5/file-Qn8KEkg3If.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624c604286364bc8f650c/file-Fqvyo6L3Kz.png)

## Lançar sua organização <a href="#launch-your-organization" id="launch-your-organization"></a>

Agora você precisa assinar uma transação para criar sua organização. Abra seu provedor Ethereum se a janela não abrir automaticamente. Clique no botão **\_confirmar** \_ em seu provedor Ethereum para assinar e transmitir a transação.

Aguarde até que a transação seja concluída.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624d704286364bc8f650d/file-arEtXF8S0j.png)

Não feche ou atualize a página até que o processo seja concluído e o DAO seja implantado.

## Clique em "Começar" <a href="#click-get-started" id="click-get-started"></a>

{% hint style="success" %}
A nova organização da sua empresa está pronta!
{% endhint %}

Agora você pode [explorar a nova organização da sua empresa](../explore-template-dao/).

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624ee04286364bc8f650e/file-a4bAYgLmxU.png)

{% hint style="info" %}
Se o seu DAO não abrir automaticamente, acesse [aqui](../../../faq/products/aragon-client/where-is-my-dao.md) e veja como acessá-lo.
{% endhint %}



> <mark style="color:purple;">**Você tem uma pergunta?Deixe seus comentários aqui em nosso fórum do Discurso**</mark>** 👇**

{% embed url="https://support.aragon.org/t/aragon-client-company-template/32/2" %}
