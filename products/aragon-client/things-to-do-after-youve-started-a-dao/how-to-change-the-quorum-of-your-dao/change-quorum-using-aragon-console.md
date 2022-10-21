# AragonコンソールでQuorum（定足数）を変更する

{% hint style="info" %}
このガイドでは、Aragonコンソールを使って、DAOの投票に必要な最小限のQuorum（定足数）を変更する方法を紹介します。
{% endhint %}

DAOを開き、DAOのウェブアドレスの末尾に`/console`を追加します。URLは次のようになります`https://client.aragon.org/#/<your-dao-name>/console`

{% hint style="warning" %}
上記URLのをあなたのDAOの名前に置き換えてください。
{% endhint %}

以下のような画面が表示されます。

<figure><img src="../../../../.gitbook/assets/immagine1.png" alt=""><figcaption></figcaption></figure>

次にDAOでトランザクションを実行するためのコマンドである`Exec`を選択します。

すると、以下のような画面が表示されるはずです。Voting Appに変更を加えるので、`Voting`を選択します。

<figure><img src="../../../../.gitbook/assets/immagine2.png" alt=""><figcaption></figcaption></figure>

[Github（英語のみ）](https://github.com/aragon/aragon-apps/blob/631048d54b9cc71058abb8bd7c17f6738755d950/apps/voting/contracts/Voting.sol)にあるVoting Appのソースコードには、私たちが必要としているQuorum Percentageの最小値を変更する関数が含まれています。

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

それでは、Aragonコンソールからこの関数を呼び出します。コンソールのコマンドに `changeMinAcceptQuorumPct(uint64 _minAcceptQuorumPct)`を追加する必要がありますが、まず`uint64 _minAcceptQuorumPct`を希望の最小Quorum Percentage（定足数）に置き換えます。

これは10^18に対するパーセンテージで表され、例えば`100% = 10^18`、`1% = 10^16`となります。例えば、最小限のQuorumを25%にしたい場合、25に0を16個足して`250000000000000000`となります。

{% hint style="danger" %}
**注意**

**最小定足数は、DAO内の投票に必要な支持率より高くなることはありません**！ですから、あなたのDAOに必要なSupport Percentageが55%以上であることを確認してください。もしそうでなければ、このチュートリアルでは必要なSupport Percentageより低い値を使用してください (そうしないと後で問題が発生します)。
{% endhint %}

ここで、コンソールのコマンドに`changeMinAcceptQuorumPct(250000000000000000)`を追加します。

<figure><img src="../../../../.gitbook/assets/immagine 3.png" alt=""><figcaption></figcaption></figure>

Enterキーを押すと、Metamaskにトランザクションが表示されるはずです。Quorum Percentageの最小値があなたの考えていたものと一致しているかどうか確認してください。

<figure><img src="../../../../.gitbook/assets/immagine4.png" alt=""><figcaption></figcaption></figure>

Create transactionをクリックし、MetaMaskで署名してください。

これでほぼ完了です。しかし、この変更によって自動的に投票が生成されたので、Voting Appに移動してください。この変更を可決するには、あなた（とDAOの十分な数のメンバー）が投票を承認する必要があります。

<figure><img src="../../../../.gitbook/assets/immagine5.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
**注意**

この変更は、投票の残り時間が終了したときにのみ実行されます。この例の場合、残り時間は23時間59分12秒です。:point\_up:
{% endhint %}

投票時間が終了したら、Enact this voteをクリックし、MetaMaskでトランザクションに署名してください。

<figure><img src="../../../../.gitbook/assets/immagine6.png" alt=""><figcaption></figcaption></figure>

これが完了すると、定足数の最小値が25%に変更されているはずです。新しい投票を作成することで、これを再確認することができます。投票を開くと、`MINIMUM APPROVAL`が`>25% needed`に変更されているはずです。

{% hint style="success" %}
ここまで終わった方、お疲れ様でした！:clap:
{% endhint %}

> <mark style="color:purple;">**ご質問はありますか？Aragonフォーラムであなたの考えをお聞かせください**</mark>👇

{% embed url="https://support.aragon.org/" %}
