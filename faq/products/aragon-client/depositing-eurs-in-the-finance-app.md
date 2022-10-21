# Depositar EURS na aplicação Finanças

O [contrato de token EURS](https://etherscan.io/address/db25f211ab05b1c97d595516f45794528a807ad8#contracts) tem um mecanismo de taxa que pode não estar funcionando bem com a forma como o frontend da Aragon calcula as aprovações de token.

O aplicativo Finanças `Finance.deposit()`faz um `transferFrom()`sob o capô. O token EURS, em `transferFrom()`, transfere:

1\. O valor solicitado do titular para o aplicativo de finanças&#x20;

2\. Um valor definido de "taxa" do titular para o "cobrador de taxas"

Tanto o valor solicitado quanto o valor da taxa definida exigem aprovações do titular para o aplicativo Finance (já que o Finance é o contrato que faz a `transferFrom()`chamada), mas agora o aplicativo Finance solicita apenas a aprovação para a primeira transferência. Portanto, quando um usuário tenta depositar EURS usando o aplicativo Finance, o valor da taxa não foi aprovado e a segunda transferência da taxa falha, revertendo toda a transação.

Deve-se notar que este mecanismo de "taxa" implementado pelo EURS não faz parte do padrão ERC20. O token EURS afirma ser "compatível com ERC20", mas o ajuste `transferFrom()`que ele tem para esse mecanismo torna o EURS incompatível com o padrão ERC20. Sob o padrão ERC20, há uma taxa de aprovação para transferência de 1:1, mas a transferência de taxa extra implementada pela EURS muda essa suposição e provavelmente quebrará muitos contratos existentes de manipulação de tokens.

Não há como contornar isso agora usando apenas o cliente front-end Aragon porque o contrato de finanças também pressupõe uma taxa de aprovação para transferência de 1:1. Os usuários podem enviar EURS diretamente para o endereço do aplicativo Vault de sua organização e, em seguida, fazer uma retirada usando o [aragonCLI](https://hack.aragon.org/developers/tools/aragoncli) .
