# Configuração das Permissões

{% hint style="info" %}
Nesta seção, exploramos detalhadamente a configuração das Permissões. Você pode encontrar um vídeo (em inglês) dedicado no final desta página.
{% endhint %}

## O que é o aplicativo Permissões? <a href="#what-is-the-permissions-app" id="what-is-the-permissions-app"></a>

O _**aplicativo Permissões**_ \*\* \*\* é usado para visualizar todas as permissões atuais que foram definidas em uma organização e adicionar ou remover permissões conforme necessário.

As permissões determinadas pelo _aplicativo Permissões_ definem quais entidades têm quais permissões para realizar várias ações em uma organização.

Por exemplo, qualquer conta pode ter permissão para criar um voto, mas só os detentores dos tokens da organização podem ter permissão para votar.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a697f2c7d3a7e9ae19121/file-gDcISkpUXb.png)

## **Navegue pel**o **aplicativo** <a href="#browse-by-app" id="browse-by-app"></a>

O _aplicativo Permissões_ mostra uma lista de todos os **aplicativos instalados** na organização e **o endereço ou símbolo** do token desse aplicativo. Você pode alterar as _permissões do aplicativo_ e as _permissões do sistema_.

![Permissões do aplicativo](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6a562c7d3a7e9ae1912e/file-0y5pgj1j2k.png)

![Permissões do sistema](../../../../.gitbook/assets/file-mnVytX0QZA.png)

### Cada aplicativo tem: <a href="#every-app-has" id="every-app-has"></a>

* uma lista de **ações que podem ser executadas** no aplicativo,
* uma lista de **ações que outras entidades receberam permissão para realizar** no aplicativo,
* uma lista de **permissões que o aplicativo recebeu** .

{% hint style="info" %}
A imagem abaixo mostra a lista de ações que podem ser executadas pelo _Aplicativo Finanças_ _(_coluna _Ação_ ), as demais entidades que possuem permissões para realizar essas ações (coluna _Atribuída à entidade_) e quem tem autoridade para atribuir a permissão a esta entidade (coluna _Gerenciado por_).
{% endhint %}

![Exemplo das permissões financeiras](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6a7104286364bc8f8145/file-NKD9Oqrl0V.png)

### Exemplo <a href="#example" id="example"></a>

Se precisarmos executar um **\_Criar novos pagamentos\_** no _aplicativo Finanças_, essa ação passará pela votação no _aplicativo Votação_. A razão por trás disso é que a ação _"Criar novos pagamentos"_ no _aplicativo Finanças_ é atribuída à entidade "Votação".

### **Permissões disponíveis** <a href="#available-permissions" id="available-permissions"></a>

A seção de permissões disponíveis mostra:

* **quais ações** podem ser executadas no aplicativo,
* **qual entidade** tem permissão para **executar** cada ação,
* **qual entidade administra** cada ação. Essa entidade é chamada de “gerente”.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b052c7d3a7e9ae19132/file-68mYNPchqp.png)

Um **gerente** tem a capacidade de **escolher quais entidades têm permissão para executar uma ação** _(Atribuir permissão)_ e a capacidade de **alterar o gerente dessa ação** (_função Gerenciar_). Essas ações podem ser feitas usando o menu suspenso sob os três pontos.

![](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.25.57 (1).png>)

### Atribuir permissões <a href="#assign-permissions" id="assign-permissions"></a>

Clique no menu suspenso nos _três pontos_ e selecione _Atribuir permissão._ Selecione um aplicativo no menu "_No Aplicativo"_, uma entidade no menu "_Atribuir à Entidade"_ e uma Ação.

![Atribuir uma permissão](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.26.48.png>)

### Função Gerenciar  <a href="#manage-role" id="manage-role"></a>

Clique no menu suspenso nos **** três pontos **e selecione** _função Gerenciar_. \*\*Selecione uma atualização no menu _**Atualizar**_.

![Gerenciar permissão](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.37.21.png>)

{% hint style="warning" %}
Se um gerente se remover como gerente de permissão sem reatribuir a função de gerente a outra entidade, o gerenciamento dessa ação será padronizado para qualquer entidade que gerencie a ação _**Criar permissões**_ no aplicativo ACL.&#x20;

No exemplo abaixo, a gestão da ação será atribuída ao _aplicativo Votação_.
{% endhint %}

![](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.12.59.png>)

{% hint style="danger" %}
Se o gerente de ação estiver definido como `0x0000000000000000000000000000000000000001`, nenhum novo gerente poderá ser definido e as permissões concedidas para essa ação serão bloqueadas para sempre.
{% endhint %}



### Inicializar permissão <a href="#initialize-permission" id="initialize-permission"></a>

Se uma ação ainda não recebeu um gerente, ela deve ser inicializada. Para inicializar uma ação, insira o endereço (_Conceder permissão para_) da entidade que você deseja gerencie a ação, selecione a qual entidade você deseja conceder a permissão para executar a ação e clique no botão _Inicializar permissão_ para inicializar a permissão, se você tem permissão para fazê-lo.

![](../../../../.gitbook/assets/inizialize.png)

### **Navegue pela entidade** <a href="#browse-by-entity" id="browse-by-entity"></a>

De volta à página principal de Permissões, você pode obter uma visão rápida de todas as permissões definidas em uma organização na seção _Navegue pela entidad_ .

Aqui, você pode ver rapidamente quais entidades receberam permissão para executar quais ações na organização.

Clicar em _**Ver detalhes**_ levará você à página de permissões dessa entidade.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b6104286364bc8f8153/file-W609vjv1Pi.png)

### **Adicionar permissão** <a href="#add-permission" id="add-permission"></a>

Para conceder permissão a uma entidade para executar uma ação em um aplicativo, clique no botão _**Adicionar permissão**_, selecione em qual aplicativo você deseja que a entidade execute a ação, selecione a entidade à qual deseja conceder a permissão e selecione a ação desejada para conceder à entidade permissão para executar.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b732c7d3a7e9ae1913a/file-xsxDomUDSy.png)

Cada aplicativo tem ações diferentes para as quais uma entidade pode receber permissão para executar.

Conceder permissão a uma entidade para realizar essas ações nesses aplicativos permitirá que ela:

#### **ACL (Lista de Controle de Acesso)** <a href="#acl-access-control-list" id="acl-access-control-list"></a>

* Criar permissões: crie permissões que ainda não foram inicializadas em qualquer aplicativo que use esta expressão de ACL`*`

> `*`_Essas ações são muito confidenciais e darão à entidade permissão para executar essas ações  e o controle quase completo da sua organização._

#### **Registro de scripts EVM (Ethereum Virtual Machine)** <a href="#evm-ethereum-virtual-machine-script-registry" id="evm-ethereum-virtual-machine-script-registry"></a>

* **Adicionar executores**: adicione um executor à organização`*`
* **Habilitar e desabilitar executores**: habilitar e desabilitar executores em uma organização`*`

> `*` _Essas ações são ações muito confidenciais que darão à entidade permissão para executar essas ações e o controle quase completo da sua organização._

{% hint style="warning" %}
Um executor é um intérprete para executar scripts em uma organização. Todos os aplicativos em uma organização usam os executores da organização para executar scripts que fazem parte das transações enviadas ao aplicativo. Cada script possui um identificador que determina qual executor é usado para executar o script.

Por exemplo, sempre que uma transação de voto é enviada para o _aplicativo Votação_, o aplicativo executa um script e, em seguida, usa um executor para executar o script na transação. Você pode encontrar mais documentação sobre executores no [Portal do Desenvolvedor de Aragon](https://hack.aragon.org/).
{% endhint %}

#### Kernel <a href="#kernel" id="kernel"></a>

* Gerencie aplicativos: instale aplicativos, atualize aplicativos e altere aplicativos padrão em uma organização. Os Registros de scripts ACL e EVM são aplicativos padrão na organização. Quem tiver permissão para realizar esta ação também pode alterar o contrato padrão do Cofre (Vault) da organização (que é o Cofre para o qual os tokens serão enviados se os tokens forem enviados para o endereço de um aplicativo que não aceite depósitos de tokens).`*`

> `*` _Essas ações são ações muito confidenciais que darão à entidade permissão para executar essas ações e o controle quase completo da sua organização._

#### **Tokens** <a href="#tokens" id="tokens"></a>

* Cunhe tokens: crie novos tokens e transfira-os para um endereço especificado
* Emite tokens: crie novos tokens e transfira-os para o _aplicativo Tokens_ da organização, para posteriormente atribuí-los a uma entidade especificada
* Atribue tokens: transfere tokens mantidos pelo _aplicativo Tokens_ para uma entidade especificada
* Revogue aquisição: revogue a aquisição dos tokens de uma entidade especificada
* Queime tokens: exclua tokens mantidos por um detentor de tokens, reduzindo o fornecimento total dos tokens

#### **Votação** <a href="#voting" id="voting"></a>

* Criar novos votos: criar um novo voto
* Modificar suporte: modifique o parâmetro _Suporte_
* Modificar quorum: modifique o parâmetro % de _Aprovação mínima_

{% hint style="info" %}
**A % Mínima de Aprovação** é a porcentagem do fornecimento total de tokens que o suporte para uma proposta deve alcançar para que a proposta seja considerada válida.

**Exemplo 1**

Se a % Mínimo de Aprovação for definido como 20%, mais de 20% do fornecimento dos tokens pendentes deverá votar para aprovar uma proposta para que o voto seja considerado válido. Se uma votação não obtiver quórum, ela será reprovada, mesmo que mais tokens tenham votado para aprovar a proposta do que contra ela.

**Exemplo 2**

Se a % Mínimo de Aprovação for definido como 20% e 10% dos tokens pendentes fornecer votos contra a proposta, mas apenas 15% de votos a favor, a proposta falhará porque não atingiu a % Mínimo de Aprovação.&#x20;
{% endhint %}

{% hint style="info" %}
**Suporte** é a porcentagem de votos em uma proposta que deve ser atingida relativamente ao suporte total para a proposta ser aprovada. Por exemplo, se o "Suporte" for definido como 51%, mais de 51% dos votos em uma proposta devem votar "Sim" para que a proposta seja aprovada.
{% endhint %}

#### Finanças <a href="#finance" id="finance"></a>

* Criar novos pagamentos: crie uma transferência do aplicativo Finanças para outra entidade
* Executar pagamentos: acionar um pagamento recorrente devido a uma entidade
* Alterar duração do período: modifique a duração em segundos entre os períodos contábeis
* Alterar orçamentos: modifique quantos tokens podem ser gastos em um determinado período contábil
* Gerenciar pagamentos: ative e desative pagamentos recorrentes

#### **Cofre (Vault)** <a href="#vault" id="vault"></a>

* Transferir tokens do Cofre (Vault): transferir os tokens mantidos pelo aplicativo Cofre (Vault)

{% embed url="https://youtu.be/kMF7Y_KPm-4?t=666" %}

> <mark style="color:purple;">**Você tem uma pergunta? Deixe seus comentários aqui no nosso fórum Discourse**</mark>** 👇**

{% embed url="https://support.aragon.org/t/aragon-client-navigate-your-dao-permissions-settings/29/2" %}
