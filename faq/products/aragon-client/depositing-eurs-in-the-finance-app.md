# Depositar EURS no aplicativo Finanças

O [contrato de token EURS](https://etherscan.io/address/db25f211ab05b1c97d595516f45794528a807ad8#contracts) tem um mecanismo de taxas que pode não estar funcionando bem com a forma como o frontend do Aragon calcula as aprovações de tokens.

`Finance.deposit()` do _aplicativo Finanças_ faz um `transferFrom()` "sob o capô". O token EURS, na `transferFrom()`, transfere:

1\. O valor solicitado do detentor para o _aplicativo Finanças_&#x20;

2\. Um valor definido de "taxa" do detentor para o "cobrador de taxas"

Tanto o valor solicitado quanto o valor da taxa definida exigem aprovações do detentor para o _aplicativo Finanças_ (já que o aplicativo Finanças é o contrato que faz a chamada `transferFrom()` ), mas agora o _aplicativo Finanças_ solicita apenas a aprovação para a primeira transferência. Portanto, quando um usuário tenta depositar EURS usando o _aplicativo Finanças_, o valor da taxa não foi aprovado e a segunda transferência da taxa falha, revertendo toda a transação.

Deve-se notar que este mecanismo de "taxa" implementado pelo EURS não faz parte do padrão ERC20. O token EURS afirma ser "compatível com ERC20", mas o ajuste do `transferFrom()`que ele tem para esse mecanismo torna o EURS incompatível com o padrão ERC20. Sob o padrão ERC20, há uma proporção de taxa de 1:1 para aprovar a transferência, mas a transferência de taxa extra implementada pela EURS muda essa suposição e provavelmente quebrará muitos contratos existentes de gerenciamento de tokens.

Não há como contornar isso agora usando apenas o front-end de _Aragon Client_ porque o contrato do _aplicativo Finanças_ também pressupõe uma proporção de taxa de 1:1 para aprovar a transferência. Os usuários podem enviar EURS diretamente para o endereço do _aplicativo Cofre_ da organização deles e, em seguida, fazer um saque usando o [aragonCLI](https://hack.aragon.org/developers/tools/aragoncli) .
