# EVMcrisprでQuorum（定足数）を変更する

{% hint style="info" %}
このガイドでは、[**EVMcrispr（英語のみ）**](https://evm-crispr.blossom.software/#/)を使ってDAOの投票に必要な最小限の Quorum (定足数) を変更する方法を説明します。

EVMcrispr は、Aragon DAOとやり取りするために、ドメイン特有の言語とJavascriptライブラリを組み合わせた強力なツールです。
{% endhint %}

まず最初に、[こちら（英語のみ）](https://evm-crispr.blossom.software/#/)からEVMcrisprを開き、Open Terminalをクリックします。これで、以下の画面が表示されるはずです。

<figure><img src="../../../../.gitbook/assets/crisper1.png" alt=""><figcaption></figcaption></figure>

次にターミナル内のテキストをすべて削除します。

<figure><img src="../../../../.gitbook/assets/crisper2.png" alt=""><figcaption></figcaption></figure>

Connectをクリックし、Metamaskに接続します。

{% hint style="danger" %}
**注意**

DAOに署名する権限を持つアカウントをEVMcrisprに接続していることを確認してください。
{% endhint %}

これから最小定足数（Quorum Percentage）を変更するためのコマンドを記述します。

DAOの最小定足数を変更するには、`connect <dao-name-or-address`でDAOに接続する必要があります。 次に、`token-manager voting`を追加します。これは`token-manager`アプリが`CREATE_VOTES_ROLE`関数を持っていて、これからやり取りする`voting`に必要なためです。以下がここまでで説明したコマンドです。

```
connect <dao-name-or-address> token-manager voting
```

それでは、EVMcrispr端末の2つ目のコマンドラインを記述します。最初に追加するのは、DAOでトランザクションを実行するためのコマンドである`Exec`です。次に、対話するアプリの`voting`を追加します。以下がここまでで説明したコマンドです。

```
connect <dao-name-or-address> token-manager voting
exec voting
```

[Github（英語のみ）](https://github.com/aragon/aragon-apps/blob/631048d54b9cc71058abb8bd7c17f6738755d950/apps/voting/contracts/Voting.sol)にあるVoting Appのソースコードを見ると、受け入れられるQuorum Percentageの最小値を変更する関数が見つかります。この関数を利用しましょう。

```solidity
function changeMinAcceptQuorumPct(uint64 _minAcceptQuorumPct)
    external
    authP(MODIFY_QUORUM_ROLE, arr(uint256(_minAcceptQuorumPct), uint256(minAcceptQuorumPct)))
{
    require(_minAcceptQuorumPct <= supportRequiredPct, ERROR_CHANGE_QUORUM_PCTS);
    minAcceptQuorumPct = _minAcceptQuorumPct;

    emit ChangeMinQuorum(_minAcceptQuorumPct);
}
```

それでは、この関数を呼び出すために、端末のコマンドに追加していきます。コマンドに `changeMinAcceptQuorumPct(uint64 _minAcceptQuorumPct)`を追加する必要がありますが、まず`uint64 _minAcceptQuorumPct`を希望の最小Quorum Percentage（定足数）に置き換えます。

これは10^18に対するパーセンテージで表され、例えば`100% = 10^18`、`1% = 10^16`となります。例えば、最小限のQuorumを25%にしたい場合、25に0を16個足して`250000000000000000`となります。

{% hint style="danger" %}
**注意**

**最小定足数は、DAO内の投票に必要な支持率より高くなることはありません**！ですから、あなたのDAOに必要なSupport Percentageが55%以上であることを確認してください。もしそうでなければ、このチュートリアルでは必要なSupport Percentageより低い値を使用してください (そうしないと後で問題が発生します)。
{% endhint %}

ここで、コンソールのコマンドに`changeMinAcceptQuorumPct(250000000000000000)`を追加します。

```
connect <dao-name-or-address> token-manager voting
exec voting changeMinAcceptQuorumPct 250000000000000000
```

コマンドの準備ができました。ターミナルにコピペして、'Forward ...'ボタンをクリックします。

<figure><img src="../../../../.gitbook/assets/crisper3.png" alt=""><figcaption></figcaption></figure>

Metamaskでトランザクションに署名すると、正常に実行されるはずです。

{% hint style="danger" %}
**`注意`**

以下のエラーが出た場合、DAOアドレスにあなた自身のDAOのアドレスを入力してください。

`Error: ENS <dao-name>.aragonid.eth not found in rinkeby, please introduce the address of the DAO instead.`
{% endhint %}

準備はほぼ整いましたので、ウェブブラウザでDAOを開いてください。URLは以下のようにします。

`https://client.aragon.org/#/<dao-name-or-address>`

これでほぼ完了です。しかし、この変更によって自動的に投票が生成されたので、まずVoting Appに移動してください。この変更を可決するには、あなた（とDAOの十分な数のメンバー）が投票を承認する必要があります。

<figure><img src="../../../../.gitbook/assets/crisper4.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
**注意**

この変更は、投票の残り時間が終了したときにのみ実行されます。この例の場合、残り時間は23時間59分12秒です。:point\_up:
{% endhint %}

投票時間が終了したら、Enact this voteをクリックし、 Metamaskでトランザクションに署名してください。

<figure><img src="../../../../.gitbook/assets/crisper5.png" alt=""><figcaption></figcaption></figure>

これが完了すると、定足数の最小値が25%に変更されているはずです。新しい投票を作成することで、これを再確認することができます。投票を開くと、`MINIMUM APPROVAL`が`>25% needed`に変更されているはずです。

{% hint style="success" %}
ここまで終わった方、お疲れ様でした！:clap:
{% endhint %}

> <mark style="color:purple;">**ご質問はありますか？Aragonフォーラムであなたの考えをお聞かせください**</mark>**👇**

{% embed url="https://support.aragon.org/" %}
