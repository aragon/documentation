# Como migrar da "antiga" DAI para a "nova" DAI

Como migrar da "antiga" DAI para a "nova" DAIO token DAI, gerenciado pela [MakerDAO](https://makerdao.com/) , foi migrado para usar outro endereço de token às 16:00 UTC em 18/11/2019.Você pode ler mais sobre os detalhes específicos da migração no [blog do MakerDAO](https://blog.makerdao.com/multi-collateral-dai-is-live/) .

* O antigo token DAI em _0x89d24a6b4ccb1b6faa2625fe562bdd9a23260359_ agora se torna **SAI**.
* O novo contrato de token **DAI multicolateral é** _0x6b175474e89094c44da98b954eedeac495271d0f_

Uma ferramenta de migração entre SAI e DAI está disponível em [migrate.makerdao.com](https://migrate.makerdao.com/).

Para todas as organizações que possuem o token DAI "antigo" (também conhecido como SAI), o cliente Aragon começou a mostrar o nome correto após um lançamento por volta de 25/11/2019.

Para organizações que possuem SAI, há dois caminhos recomendados para atualizar para a DAI multicolateral:

* Transfira a SAI para uma conta externa ou contrato multisig que você controla. A partir daí, use a interface de migração em [migrate.makerdao.com](https://migrate.makerdao.com/) para trocar SAI por DAI e deposite a nova DAI de volta em sua organização
* Instale um aplicativo Agent , caso sua organização ainda não tenha instalado um. Transfira o SAI para o aplicativo Agente, configure as permissões necessárias para permitir interações com o aplicativo Agente e use [migrate.makerdao.com](https://migrate.makerdao.com/) via [Frame](https://frame.sh/) .

Para organizações que detêm a SAI Collateralized Debt Position (CDPs) antigas, os caminhos de migração recomendados são semelhantes se a organização estivesse apenas detendo SAI: transfira a propriedade do SAI CDP da organização para uma conta externa, multisig ou aplicativo de agente instalado com o qual você possa interagir e use a interface [migrate.makerdao.com](https://migrate.makerdao.com/) . Nesse cenário, certifique-se de que a conta com propriedade sobre o SAI CDP também tenha $MKR suficiente para pagar quaisquer taxas de estabilidade devidas.

As organizações que desejam criar novos cofres de DAI devem interagir com o aplicativo Oasis Trade usando um aplicativo de agente instalado e um Frame.
