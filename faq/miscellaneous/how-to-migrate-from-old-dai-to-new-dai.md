# 旧DAIから新DAIへの移行方法

[MakerDAO](https://makerdao.com/)が管理するDAIトークンは、2019年11月18日16:00UTCに別のトークンアドレスを使用するように移行されました。

移行の具体的な内容については、[MakerDAOのブログ（英語のみ）](https://blog.makerdao.com/multi-collateral-dai-is-live/)で詳しく紹介されています。

* 旧DAIのトークンアドレス（0x89d24a6b4ccb1b6faa2625fe562bdd9a23260359）は現在**SAI**になります。
* 新しい**マルチコラテラル**DAIのトークンアドレスは0x6b175474e89094c44da98b954eedeac495271d0fです。

SAIとDAI間の移行ツールは、[migrate.makerdao.com（英語のみ）](https://migrate.makerdao.com/)で利用可能です。

旧DAI（別名SAI）トークンを保有する組織については、2019年11月25日頃のSAIリリースに伴い、Aragonクライアントが正しい名前を表示するようになりました。

SAIを保有する組織では、マルチコラテラルDAIにアップグレードするための推奨方法が2つあります。

* SAIをあなたが管理する外部口座またはマルチシグコントラクトに転送します。そこから[migrate.makerdao.com（英語のみ）](https://migrate.makerdao.com/)の移行インターフェースを使用して、SAIをDAIに交換し、新しいDAIを組織に戻します。
* [Agent App](../../products/aragon-client/explore-template-dao/what-are-apps/agent-app/)をインストールしていない場合は、インストールします。SAIをAgentアプリに転送し、Agentアプリとのやり取りを許可するために必要な権限を設定し、[Frame（英語のみ）](https://frame.sh/)経由で[migrate.makerdao.com（英語のみ）](https://migrate.makerdao.com/)を使用します。

古いSAI担保付き債務ポジション（CDP）を保有する組織の場合、推奨される移行方法は、組織がSAIのみを保有していた場合と同様です。組織のSAI CDP所有権を、外部アカウント、マルチシグ、またはやり取りが可能なインストール済みのAgentアプリに移行し、[migrate.makerdao.com（英語のみ）](https://migrate.makerdao.com/)インターフェイスを使用することで、移行できます。このシナリオでは、SAI CDPの所有権を持つアカウントが、支払うべきスタビリティ手数料（利息）を返済するのに十分な$MKRを保持している必要があります。

新しいDAI Vaultsを作成したい組織は、インストールされたAgentアプリとFrameを使用して、Oasis Tradeアプリケーションと対話する必要があります。
