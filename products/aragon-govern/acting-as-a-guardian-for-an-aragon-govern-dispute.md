# Acting as a guardian for an Aragon Govern dispute

The first use case for [Aragon Court](../aragon-court/) is to be the subjective dispute resolution for Aragon Govern DAOs, enabling optimistic governance to take place with an extra layer of security.

Whenever an Aragon Govern transaction is challenged, a new dispute is created in Aragon Court. If you get summoned as a guardian for this kind of dispute, this is what you need to know.

## Understanding the content

### **Dispute fields**

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6113a430766e8844fc34f656/file-WrG7lYSfrJ.png)

**Description**

The basic description of the transactions. This should provide you with additional context on what the transaction is about.

**Agreement**

The agreement or contract that supports this transaction. All Aragon Govern DAOs MUST have a human-readable agreement that states how the DAO intends to operate, and what actions should be allowed or forbidden. For example, an agreement might say that a given DAO may only invest in sustainability projects, and a conflict would arise if a transaction instead intended to transfer funds to a car manufacturing company.

**Executor**

The address of the contract that will execute this transaction.

**Dispute creator**

The address of the person/contract that created the dispute.

**Actions**

The set of transactions that will be executed if the dispute is ruled in favor of who created this.

**Original justification**

This is a human-readable justification stating why actions were scheduled to be executed. For example the creator might say something like "Transferring funds to a project that is creating a carbon footprint offset device". This is added by the actions creator during scheduling.

**Dispute evidence**

The justification of why the actions are being challenged. For example "The destination address actually belongs to a car manufacturing company, and therefore we should not allow this transferring of the funds". This information is added by the person challenging the actions.

### **What are Actions?**

Actions are nothing more than smart contract transactions that have been scheduled with an Aragon Govern DAO. These can be any interaction with an EVM-compatible blockchain, such as transferring funds, minting tokens, swapping tokens, etc.

On Aragon Govern, an action can be a bundle of several transactions. This is what is shown in Aragon Court. Understanding the Actions is essential to ruling on a dispute.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/61139fe464a230081ba1e1d8/file-MUdTAgjhC3.png)

### The action contains the following information:

**To**: Smart contract that will receive the transaction

**Value**: Optional amount of ETH being sent in the transaction

**Function to be called**: Name of the function being called in the "**To**" smart contract

**Data**: The parameters being sent to the function.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6113a04bb37d837a3d0e2b5d/file-EGn7CGNTer.png)

{% hint style="info" %}
If you want to dig deeper and understand what a given function does, and what each parameter is used for, click on the **TO address** and open it on Etherscan. There you should be able to see details of the contract and function code.
{% endhint %}

Sometimes the function and data might not be available (when the contract is not verified on Etherscan ([Learn More](https://etherscan.io/verifyContract)). In this case, you will see the **Raw Data**, which can still be decompiled if you research the destination contract.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6113a0e26ffe270af2a97c43/file-xCv7UHQxZH.png)

You may always click on the addresses to check the contracts on Etherscan to better understand what the transactions will actually be performing.

### **The Pieces of Evidence**

The evidence section of Aragon Court shows the address of the person that submitted the evidence, as well as the date of the submission, and its content (text or file).

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6113a7fd6ffe270af2a97c76/file-5Js1MtD8Up.png)

### Ruling upon the dispute

Once the dispute goes into the voting stage (after the guardians have been summoned, and if you were one of them) it is time to vote if these actions should be permitted or not.

### **Voting**

When the voting time comes for an Aragon Govern dispute, you need to decide if the Actions should be allowed, blocked, or if you don't have enough context to rule upon it. Remember that if you voted with the majority (for any of the 3 aforementioned options) your tokens will not get slashed, and you will earn slashed tokens from whoever did not vote with the majority.

Voting is **MANDATORY** if you are summoned. If you don't cast your vote (the refusing to vote option is considered a cast vote as well) your tokens will be slashed.

**Allow action**

This means the transactions will happen if the majority votes for it.

**Block action**

This means the transactions will be canceled if the majority votes for it.

**Refuse to vote**

This means the transactions will happen if the majority refuses to vote.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6113a830766e8844fc34f672/file-IxTy2xkH3b.png)

### **Revealing vote**

To make sure guardians act without any bias, votes are kept secret during the voting phase. For this reason, when you commit your vote, you will be asked to save a one-time code to be used when the reveal phase starts.

You also have the option to enable the auto-reveal service.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6113a83f6ffe270af2a97c78/file-AfZaSlWkn6.png)

{% hint style="danger" %}
* Auto-reveal service might not be available sometimes. If this happens, please wait for about 2 minutes, and try again.
* If you do not enable auto-reveal, and do not manually reveal your vote when the reveal stage is available, the system will consider that you did not vote, and you will get your tokens slashed.
{% endhint %}

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6113a872b55c2b04bf6dd4e7/file-2ebMDlmKLp.png)

### Next steps

The next stages can be triggered by anyone in Aragon court (including you) but are not your responsibility. If a dispute is appealed, a new round of guardians will be summoned. If you are one of them, follow this same process again.
