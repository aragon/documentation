# Governance - Which parameters of Court can be changed? How?

* Almost all parameters, except for the term duration, period duration, and Court start time can be changed. In particular:
  * Controller contract:
    * Court parameters:
      * Juror fees
      * Draft fees
      * Settlement fees
      * Argument submission period
      * Commit period
      * Reveal period
      * Appeal period
      * Appeal confirm period
      * Penalty percentage of min active balance to be slashed for losing guardians
      * Final round fees reduction percentage
      * First round guardians number
      * Factor used to increase guardians number in each appeal
      * Number of regular rounds (before final round with all guardians is triggered
      * Number of terms that a coherent guardians in a final round is disallowed to withdraw (to discourage 51% attacks)
      * Multiple of dispute fees required to appeal a preliminary ruling
      * Multiple of dispute fees required to confirm appeal
      * Minimum amount of guardian tokens that can be activated
    * Governor addresses:
      * Modules governor
      * Funds governor
      * Configuration governor
    * Eject governor addresses i.e. remove without replacing:
      * Eject Funds governor
      * Eject Modules governor
    * Module addresses:
      * Dispute Manager
      * Jurors Registry
      * Voting
      * Treasury
      * Subscriptions
      * Set addresses for new modules
  * Dispute Manager module:
    * Controller address (can only change by deploying a new Dispute Manager module)
    * Number of skipped disputes (can only change by deploying a new Dispute Manager module)
    * Maximum guardians per draft batch (relevant in case a draft is so large it requires multiple transactions or batches)
  * Jurors Registry module:
    * Controller address (can only change by deploying a new Jurors Registry module)
    * Jurors token contract address (can only change by deploying a new Jurors Registry module)
    * Total active balance limit
  * Voting module:
    * Controller address (can only change by deploying a new Voting module)
  * Treasury module:
    * Controller address (can only change by deploying a new Treasury module)
  * Subscriptions module
    * Controller address (can only change by deploying a new Subscriptions module)
    * Period duration (can only change by deploying a new Subscriptions module)
    * Subscriptions fee token
    * Subscriptions fee amount
    * Number of pre-payment periods
    * Number of resume pre-paid periods
    * Governor share %
    * Late payment penalty %
* Only the Aragon Network DAO can change them, through a vote. Currently, the Aragon Network DAO is composed of five council members. It is planned for [control to be transitioned to ANT holders](https://blog.aragon.org/evolving-aragon-network-governance/).
