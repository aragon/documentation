# Agent App

## O que é o aplicativo Agente? <a href="#what-is-the-agent-app" id="what-is-the-agent-app"></a>

O _**aplicativo Agent**_ permite que as organizações Aragon **interajam** diretamente com quaisquer **outros contratos inteligentes** no Ethereum. Antes do Agente, uma organização teria que nomear uma parte confiável para interagir com um contrato inteligente Ethereum em seu nome.

{% hint style="info" %}
Por exemplo, uma organização enviaria algum $DAI para um de seus funcionários, que então seria confiável para emprestar o $DAI em Composto, ganhar juros e então enviar os juros mais o princípio de volta para a organização.
{% endhint %}

Agora, com o Agent, uma organização pode emprestar seu $DAI diretamente no Compound, sem ter que confiar em nenhum intermediário.

## Como começar a usar o aplicativo Agente? <a href="#how-to-start-using-the-agent-app" id="how-to-start-using-the-agent-app"></a>

A maneira mais fácil de começar a usar o aplicativo Agente é **marcar a caixa** para instalá-lo opcionalmente ao criar sua organização pela primeira vez:

<figure><img src="../../../../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Observe que a instalação do Agent por meio de um dos modelos substituirá o aplicativo Vault normalmente incluído por modelos que não usam o aplicativo Agent.
{% endhint %}

{% hint style="warning" %}
Se você não instalou opcionalmente o aplicativo Agente ao criar sua organização pela primeira vez, ainda poderá instalá-lo após a criação da organização. Para fazer isso, você precisará seguir as instruções para [instalar e inicializar o aplicativo Agent usando o aragonCLI. ](https://github.com/aragon/aragon-apps)Observe que esta opção é voltada para especialistas.
{% endhint %}

## **Interface de front-end do agente** <a href="#agent-frontend-interface" id="agent-frontend-interface"></a>

Atualmente, o _**aplicativo Agent**_ tem uma **interface de front-end somente para visualização** que você pode usar para ver quais tokens são mantidos atualmente pelo aplicativo Agent (incluindo tokens ERC-20, ERC-677 e ERC-777), bem como ver um histórico de transações feito usando o aplicativo Agente. O histórico de transações pode ser filtrado por tipo de transação, token ou data e pode ser exportado como um arquivo CSV.

![Página do aplicativo do agente](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5e8ce5d32c7d3a7e9aea8d19/file-r5322DPQHX.png)

O endereço do contrato inteligente do Agente está disponível no menu _**Sistema na página Organização**_ .

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bcdad2c7d3a7e9ae1a16d/file-pJP6dzQfhR.png)

> <mark style="color:purple;">**Você tem uma pergunta?Deixe seus comentários aqui em nosso fórum do Discurso**</mark>** 👇**

{% embed url="https://support.aragon.org/t/aragon-client-navigate-your-dao-agent-app/28/2" %}
