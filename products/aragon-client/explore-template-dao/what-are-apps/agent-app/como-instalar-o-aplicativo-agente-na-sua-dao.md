# 🏗 Como instalar o aplicativo Agente na suDAO

Você precisa do _aplicativo Agente_, mas ainda não foi instalado na sua DAO? Não se preocupe, ele ainda pode ser instalado usando o [**EVM Crispr**](https://evm-crispr.blossom.software/#/)**,** uma ferramenta para modificar 'o ADN' da sua DAO.



O aplicativo Agente não está instalado porque não aparece em '_APPS_' na barra do menu DAO:

<figure><img src="../../../../../.gitbook/assets/agent 1.png" alt=""><figcaption></figcaption></figure>



Antes de começar com _EVM Crispr_, precisamos que você colete o 'endereço' da sua DAO. Você pode encontrá-lo em _'SISTEMA > Organização_':

<figure><img src="../../../../../.gitbook/assets/agent 2.png" alt=""><figcaption></figcaption></figure>



Agora vamos ao terminal do _EVM Crispr_:

{% embed url="https://evm-crispr.blossom.software/#/terminal" %}

Limpe o terminal removendo todos os comandos de exemplo que você encontrará ao abri-lo:

<figure><img src="../../../../../.gitbook/assets/agent 3.png" alt=""><figcaption></figcaption></figure>

Agora copie/cole os seguintes comandos no terminal:

```
load aragonos as ar
  
ar:connect <your dao address> token-manager voting (
  install agent:new
  grant voting agent:new TRANSFER_ROLE voting
  grant voting agent:new EXECUTE_ROLE voting
  grant voting token-manager ISSUE_ROLE voting
)
```

{% hint style="info" %}
Além de instalar o _aplicativo Agente_, também concedemos a licença ao _aplicativo Votação_ com o`TRANSFER_ROLE`, `EXECUTE_ROLE`, e`ISSUE_ROLE` , assim os comandos`exec agent` e `act agent` podem ser usados ​​no futuro.
{% endhint %}



É assim que o terminal deve ficar depois de copiar/colar os comandos acima:

<figure><img src="../../../../../.gitbook/assets/agent 4.png" alt=""><figcaption></figcaption></figure>

Encontre o endereço da DAO que você salvou anteriormente e agora substitua `<your dao address>` pelo endereço. Clique em **Conectar** e conecte-se à sua carteira Web3 (geralmente MetaMask).

{% hint style="danger" %}
Assegure-se de que a sua carteira Web3 esteja conectada à **Rede** na qual a DAO de Aragon foi criada. Também deve ser definido para a **Conta** que criou a DAO no Aragon Client e/ou possui os tokens da DAO.
{% endhint %}



Agora clique em _**Forwarding from...**_ :

<figure><img src="../../../../../.gitbook/assets/agent 5.png" alt=""><figcaption></figcaption></figure>

Uma solicitação de transação deve aparecer na sua carteira Web3. Confirme a transação. Assim que a transação for processada com sucesso na sua carteira Web3, retorne a sua DAO no _Aragon_ e abra o _aplicativo Votação_ na barra do menu. Você deve ver que um voto foi gerado:

<figure><img src="../../../../../.gitbook/assets/agent 6.png" alt=""><figcaption></figcaption></figure>

Agora abra a votação clicando nela e conecte a sua carteira Web3 no canto superior direito. Uma vez conectado, role para baixo e aprove a votação clicando em _**Sim**_:

<figure><img src="../../../../../.gitbook/assets/agent 7.png" alt=""><figcaption></figcaption></figure>

Após clique em _**Criar transação**_ e confirme a transação na sua carteira Web3. Depois que a transação for processada e a votação for aprovada, você deverá ver o _aplicativo Agent_ aparecer automaticamente na barra do menu! :partying\_face:

<figure><img src="../../../../../.gitbook/assets/agent 8.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Se o seu endereço não tiver suficientes 'tokens da DAO' para que a votação atenda ao Suporte e Aprovação Mínima necessária, mobilize outros detentores dos tokens para votar de modo que a votação possa ser aprovada.&#x20;
{% endhint %}



O aplicativo Agente deve ficar assim:

<figure><img src="../../../../../.gitbook/assets/agent 9.png" alt=""><figcaption></figcaption></figure>

Leia o próximo artigo sobre [como usar o aplicativo Agente](using-agent-with-frame.md)!

E para mais opções de uso do _aplicativo Agente_ com _EVM Crispr_, confira aqui:

{% embed url="https://docs.evmcrispr.blossom.software/aragonOS/agent/" %}
