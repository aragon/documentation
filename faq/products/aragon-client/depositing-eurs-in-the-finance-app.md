# Finance AppでEURSを入金する

[EURSトークンコントラクト（英語のみ）](https://etherscan.io/address/db25f211ab05b1c97d595516f45794528a807ad8#contracts)には手数料メカニズムがあり、Aragonフロントエンドのトークン承認の際の計算方法とうまく連携していない可能性があります。

Finance Appの`Finance.deposit()`は、内部で`transferFrom()`を実行します。EURS トークンは、`transferFrom()`により、以下の2つが転送が必要になります。

1\. ホルダーが要求した金額がFinance Appに転送される

2\. 手数料が手数料コレクターに転送される

要求額と設定された手数料額の両方のFinance Appへの承認が必要です（Financeは`transferFrom()`を呼び出すコントラクトであるため）が、現在、Finance Appは最初の転送に対してのみ承認を要求します。そのため、ユーザーがFinance Appを使用してEURSを入金しようとすると、手数料の金額が承認されておらず、手数料のための2回目の送金が失敗し、トランザクション全体が元に戻ってしまいます。

EURSが実装しているこの「手数料」の仕組みは、ERC20規格の一部ではないことに注意する必要があります。EURSトークンは「ERC20準拠」と主張していますが、この仕組みのために`transferFrom()`を調整すること、ERC20標準と互換性がなくなります。ERC20規格の下では、承認と転送の比率は1:1ですが、EURSによって実装された追加料金の転送はこの前提を覆し、既存の多くのトークン処理コントラクトでは機能しない可能性があります。

Finance Appのコントラクトも1:1の送金承認比率を想定しているため、Aragonフロントエンドクライアントだけを使用してこの問題を回避する方法は今のところ存在しません。ユーザーは、DAOのVaultアプリのアドレスに直接EURSを送信し、[aragonCLI（英語のみ）](https://hack.aragon.org/developers/tools/aragoncli)を使用して引き出しを行うことができます。
