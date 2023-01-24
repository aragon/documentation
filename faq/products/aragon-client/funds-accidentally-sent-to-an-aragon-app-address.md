# Como recuperar fundos enviados acidentalmente para um endereço de um aplicativo Aragon

Se você acidentalmente enviou tokens para o endereço de um aplicativo instalado em uma organização Aragon, você pode recuperar os tokens e enviá-los para o _Cofre_ da organização, o aplicativo da organização que deve reter seus fundos DAO. Existem duas maneiras de fazer isso:

1. [Usando o **recurso de Console integrado (mas oculto)** da interface da DAO](funds-accidentally-sent-to-an-aragon-app-address.md#recover-your-funds-using-the-console-feature)
2. [Usando **aragonCLI** na linha](funds-accidentally-sent-to-an-aragon-app-address.md#recover-your-funds-using-aragoncli)

{% hint style="danger" %}
É altamente recomendável usar a _opção Console,_ pois é muito mais fácil​
{% endhint %}

### Recupere seus fundos usando o recurso Console <a href="#recover-your-funds-using-the-console-feature" id="recover-your-funds-using-the-console-feature"></a>

Siga as seguintes etapas:

Abra seu DAO e adicione `/console` ao final do endereço web da sua DAO. A URL ficaria assim: `https://client.aragon.org/#/<your-dao-name>/console`

{% hint style="warning" %}
Substitua `<your-dao-name>` pelo nome da sua DAO na URL acima​
{% endhint %}

Você deve ver algo como o abaixo:

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

​Em seguida, selecione `Exec` qual é um comando usado para realizar transações nas DAOs.

Aqui você seleciona o aplicativo para o qual os fundos foram enviados acidentalmente. Neste exemplo, os fundos foram enviados acidentalmente para o _aplicativo Finanças_, então selecionamos `Finance`:

<figure><img src="../../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

​No código-fonte do _aplicativo Finanças_ no [​​Github](https://github.com/aragon/aragon-apps/blob/631048d54b9cc71058abb8bd7c17f6738755d950/apps/finance/contracts/Finance.sol#L399-L410) você encontra uma função chamada `recoverToVault`, exatamente o que precisamos!

Agora vamos chamar essa função do Console Aragon. Para fazer isso, teremos que adicionar `recoverToVault(address _token)` ao comando no console, mas primeiro substituiremos `address _token` pelo endereço do contrato dos tokens que foram enviado acidentalmente ao _aplicativo Finanças_.

No caso deste exemplo o endereço é `0x3255D2D022Ef80F58dA2D107235010367cCdF0fD`, então adicionaremos `recoverToVault(0x3255D2D022Ef80F58dA2D107235010367cCdF0fD)` ao comando no Console. O comando completo para este exemplo agora é o seguinte:

```
exec/0xa4bb9c789cccdce9565ee5a6d066dccef05c6a42/recoverToVault(0x3255D2D022Ef80F58dA2D107235010367cCdF0fD)
```

Agora clique em '_Entrar'_: __&#x20;

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

​Agora confirme a transação clicando em '_Criar transação'_:

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

​A seguir, confirme a transação em sua carteira Web3 (na maioria dos casos MetaMask).

{% hint style="danger" %}
Assegure-se de usar uma conta Web3 que criou a DAO ou (e) está mantendo seus tokens DAO, para assinar esta transação
{% endhint %}

Agora vá para o _aplicativo Finanças_ na sua organização e seus fundos devem aparecer magicamente lá!😅​🎉​

Neste exemplo, os tokens BRT foram recuperados do _aplicativo Finanças_ para o _Cofre_ (Vault):

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

### Recupere seus fundos usando aragonCLI <a href="#recover-your-funds-using-aragoncli" id="recover-your-funds-using-aragoncli"></a>

Use as seguintes etapas:

1. [Instale o aragonCLI](https://hack.aragon.org/developers/tools/aragoncli), que é uma interface de linha de comando para interagir com as organizações de Aragon.
2. Execute `aragon ipfs` no seu Terminal para fornecer ao aragonCLI uma maneira de acessar dados (por exemplo, ABIs) para organizações de Aragon.
3. Defina[ uma chave privada para o aragonCLI usar](https://hack.aragon.org/developers/tools/guides/how-to-sign-with-web3-providers) e, logo depois, envie algum 'ether' para o endereço dessa chave privada para pagar pelo gás.
4. Envie o seguinte comando de transação do aragonCLI, substituindo cada "endereço" pelo endereço correspondente relevante para a sua transação travada:

```powershell
dao exec OrganizationAddress AppAddress recoverToVault TokenContractAddress --environment aragon:mainnet
```

O `OrganizationAddress`\_\_ é o endereço da organização que hospeda os fundos bloqueados, o `AppAddress` é o endereço do aplicativo para o qual você enviou os fundos bloqueados e o `TokenContractAddress` é o endereço do contrato de token dos tokens que você enviou.

Por exemplo, se você enviou [Dai](https://etherscan.io/token/0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359) para o endereço do _aplicativo Finanças_ da organizaçã <mark style="color:blue;">genesis.aragonid.eth</mark>, o comando de transação que você enviaria do aragonCLI seria:

```
dao exec 0x8A83D4bCE45b4C4F751f76cf565953D1E4A3BF0a 0x98516C82Bda8B3dE6E2670B718848949Ae6a4643 recoverToVault 0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359 --environment aragon:mainnet
```

Obrigado a Chris Hobcroft por documentar essos passos [neste comentário do GitHub](https://github.com/ethereum-cat-herders/funding/issues/2#issuecomment-477174751) .