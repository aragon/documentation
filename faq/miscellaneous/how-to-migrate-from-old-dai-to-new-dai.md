# Como migrar da "antiga" DAI para a "nova" DAI

O token DAI, gerenciado pela [MakerDAO](https://makerdao.com/), foi migrado para usar outro endereço de token às 16:00 UTC em 18/11/2019. Você pode ler mais sobre os detalhes específicos da migração no [blog da MakerDAO](https://blog.makerdao.com/multi-collateral-dai-is-live/) .

* O antigo token DAI em _0x89d24a6b4ccb1b6faa2625fe562bdd9a23260359_ agora se torna **SAI**.
* O novo contrato do token **DAI Multicolateral** é: **** _0x6b175474e89094c44da98b954eedeac495271d0f_

Uma ferramenta de migração entre SAI e DAI está disponível em [migrate.makerdao.com](https://migrate.makerdao.com/).

Para todas as organizações que possuem o token DAI "antigo" (também conhecido como SAI), o _Aragon Client_ começou a mostrar o nome correto após um comunicado por volta de 25/11/2019.

Para organizações que possuem SAI, há dois caminhos recomendados para atualizá-los para os DAI multicolaterais:

* Transfira os SAI para uma conta externa ou para um contrato multisig que você controla. A partir daí, use a interface de migração em [migrate.makerdao.com](https://migrate.makerdao.com/) para trocar SAI por DAI e deposite os novos DAI de volta na sua organização
* Instale um _aplicativo Agente_, caso sua organização ainda não tenha instalado um. Transfira os SAI para o _aplicativo Agente_, configure as permissões necessárias para permitir interações com o _aplicativo Agente_ e use [migrate.makerdao.com](https://migrate.makerdao.com/) via [Frame](https://frame.sh/) .

Para organizações que detêm os antigos "SAI Collateralized Debt Position" (CDPs), os caminhos de migração recomendados são parecidos se a organização estivesse apenas detendo SAI: transfira a propriedade dos SAI CDP da organização para uma conta externa, multisig ou _aplicativo Agente_ instalado com o qual você possa interagir, e use a interface [migrate.makerdao.com](https://migrate.makerdao.com/) . Nesse cenário, assegure-se de que a conta proprietária dos SAI CDP também tenha $MKR suficiente para pagar quaisquer taxas de estabilidade devidas.

As organizações que desejam criar novos cofres de DAI devem interagir com o aplicativo 'Oasis Trade' usando um _aplicativo Agente_ instalado e 'Frame'.
