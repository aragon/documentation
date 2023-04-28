# Court Dashboard

{% hint style="info" %}
In this section, we will explore the Aragon Court Dashboard.
{% endhint %}

## What is the Aragon Court Dashboard?

The Aragon Court Dashboard is the central app where all dispute-related tools are available for guardians. It also contains **detailed information about past and current disputes**, including arguments, rulings, timelines, and much more.

The following guide presents an overview of the various sections of the Dashboard.

![](<../../.gitbook/assets/Screenshot 2022-02-07 at 11.19.38.png>)

## **Connecting to the Dashboard**

The Dashboard is accessible to all users at [court.aragon.org](https://court.aragon.org). General information and statistics are available on the main page as well as more specific information related to disputes, tasks, and guardians on their respective pages.

You need to connect your Ethereum account to the Aragon Court Dashboard to use your app. To do so, simply click on the _**Connect account**_ button at the upper right and select the provider of your choice.

![](<../../.gitbook/assets/Screenshot 2022-02-07 at 11.13.48 (2).png>)

On the top of the dashboard, you can see a countdown timer for the current **Court Term**. Time in Aragon Court is measured in Court Terms, and **each term lasts for 8 hours**.

{% hint style="warning" %}
Occasionally you may see a message on this countdown timer that says "Term needs updating".

Aragon hosts the Aragon Court Dashboard instance at [court.aragon.org](https://court.aragon.org) and runs an automated service that will automatically update the Court within a couple of hours of the term ending, so this message can be disregarded.
{% endhint %}

![](<../../.gitbook/assets/Screenshot 2022-02-07 at 11.21.54.png>)

## **Notifications**

Aragon Court guardians can sign up for email notifications to be notified of important events, such as when they have been drafted to a dispute, task reminders, and more.

Email notifications are important so that as a guardian you do not miss out on any important tasks.

{% hint style="danger" %}
**Remember that if you do not complete the required tasks, you will lose a portion of your locked tokens (more info about this** [**here**](https://help.aragon.org/article/43-dispute-lifecycle#drafting-jury)**).**

It is strongly recommended that you sign up for email notifications and monitor them closely while you are an active guardian. If you fail to complete your tasks on time, you will lose your money.
{% endhint %}

To opt-in, click the \*\* **\_**gear-shaped**\_ Settings icon in the top corner and click \_**Notifications\*\*\_.

![](../../.gitbook/assets/Screenshot\_2022-02-07\_at\_11\_57\_40.png)

Click **Unlock notification settings**. Sign the message on the prompt to prove ownership of your Ethereum address, so that you can modify your notification settings.

![](<../../.gitbook/assets/Screenshot 2022-02-07 at 11.59.05 (1).png>)

Once you have proven ownership of your address, you will be able to enter your email address to opt-in to notifications.

After entering your email address, a verification email will be sent to your email address (if you don't see it in the inbox, check the Spam folder). Click the link in the verification email to confirm your address.

![](<../../.gitbook/assets/Screenshot 2022-02-07 at 12.18.10 (2).png>)

After you successfully verify your email address, click the _**x**_ button in the top corner to close the notification verification window then re-enable your Ethereum account on the main Dashboard page.

You will then be able to go back to the Notifications section of the Settings menu to manage your notification subscription.

![](../../.gitbook/assets/Screenshot\_2022-02-07\_at\_12\_25\_02.png)

## **Balances**

![](<../../.gitbook/assets/Screenshot 2022-02-07 at 12.51.36.png>)

The first section you will see at the top of the Dashboard contains your token balance information.

This section is divided into three columns:

* My wallet
* Inactive
* Active

Each column contains its history of recent actions executed in the last 24 hours.

#### The **wallet** shows the number of tokens that your Ethereum wallet currently contains and its relative value in US dollars.

{% hint style="info" %}
Those tokens are not being managed by the Court and are at any given time fully under your control. To activate them and increase your chances of being drafted as a guardian, you can click the Activate button at the bottom of the section and a side panel will appear asking for the amount of tokens that you want to activate. The amount will be transferred to the Active section once the transaction is executed.
{% endhint %}

#### The second column contains your **Inactive token** balance along with its value in US dollars. Inactive tokens are held in the Court contract but don't increase your probability of being drafted.

Two actions are available when you have an inactive balance:

* **Withdraw:** Withdraws a specified portion of the inactive tokens to your wallet.
* **Activate:** Activates a specified portion of the inactive tokens and transfers it to the Active section.

#### The third column contains your **Active tokens.** Active tokens serve three main purposes:

* They determine your probability of being drafted as a guardian. The higher the amount, the higher the probability.
* Subscription rewards are directly proportional to active tokens.

{% hint style="info" %}
[Click here](court-dashboard.md#rewards) to learn more about the different types of rewards.
{% endhint %}

* To incentivize consensus decisions and honest behaviors, a portion of your active tokens are locked when drafted for a dispute and you can get rewarded or penalized depending on the final ruling.

{% hint style="info" %}
[Click here ](dispute-lifecycle.md)to learn more about disputes.
{% endhint %}

The _**Deactivate**_ button can be used to transfer tokens to an inactive state.

{% hint style="danger" %}
Tokens do not get deactivated immediately, but only at the start of the next term (reminder here that each term currently lasts for 8 hours). You can still be drafted to rule on a dispute before your tokens are deactivated. After you rule on the dispute, your deactivated tokens will enter an inactive state.
{% endhint %}

#### Finally, at the top of the section, you can see in real-time your probability of being drafted as a guardian.

The more tokens you have activated relative to the rest of the tokens other guardians have activated, the higher the probability will be.

## **Tasks**

#### Aragon Court requires certain tasks to be executed at various points in the lifecycle of a dispute. Some tasks can be executed by anyone while others are strictly assigned to specific accounts.

You can quickly see every task assigned to you along with their due date in the \*\* **\_**Upcoming Tasks**\_ section of the main page. A page dedicated to tasks is also available by clicking the \_**Tasks\*\*\_ menu item in the left side panel.

If you are concerned about missing important tasks, don't worry, if you signed up for email notifications then notifications about your tasks will be sent directly to your email inbox.

![](<../../.gitbook/assets/Screenshot 2022-02-07 at 12.55.26.png>)

#### The following list contains every task you may encounter:

* **Summon Guardians:** This task must be executed at the beginning of a round to select the guardians. Anyone can execute this task by clicking on the _**Summon Guardians**_ button of the dispute. A small DAI reward is granted for successfully executing the task.
* **Commit vote**: One of the most important tasks in Aragon Court. When a guardian is drafted to adjudicate a dispute, their duty is to review the submitted arguments and commit a vote within the voting period limit. Failure to execute this action would penalize the guardian.

{% hint style="info" %}
Click [here](dispute-lifecycle.md) for more information about committing votes.
{% endhint %}

* **Reveal vote**: Since votes are secret until the end of the voting period, a task is also needed in order for the ruling to be revealed. However, an option is available to make this task fully automated.

{% hint style="info" %}
Click [here](dispute-lifecycle.md) to learn more about revealing votes.
{% endhint %}

* **Appeal ruling**: Once the ruling is revealed, it can be appealed by anyone who disagrees with its result. Be aware that you need to lock an amount of DAI to appeal a ruling. You will get rewarded if the ruling ends up turning in your favor at the end of the dispute.

{% hint style="info" %}
Learn more about appeals[ here](dispute-lifecycle.md).
{% endhint %}

* **Confirm appeal:** To officially appeal a ruling and launch a new adjudication round, a second account also needs to lock an amount of DAI to confirm that there is indeed a need for an appeal.

{% hint style="info" %}
Learn more about appeal confirmation [here.](dispute-lifecycle.md)
{% endhint %}

* **Execute ruling**: If no appeal has been requested and confirmed within their respective periods of time, the "Execute ruling" task is available to finalize the dispute.

{% hint style="info" %}
[Click here](dispute-lifecycle.md) to learn more about final rulings.
{% endhint %}

## **Rewards** <a href="#rewards" id="rewards"></a>

Rewards can be obtained in multiple ways, both as a guardian and as a normal user.

![](<../../.gitbook/assets/Screenshot 2022-02-07 at 12.56.38.png>)

### **As a guardian:**

* **Subscription fees:** You earn a monthly reward, in DAI, proportional to your active tokens, whether you are drafted or not.
* **Dispute fees:** If drafted, you earn reward for ruling in favor of the dispute's final ruling.
* **Ruling fees:** The locked tokens of guardians who voted in the minority in a given dispute are redistributed to guardians who voted in the [plurality](aragon-court.md) according to the final ruling. Ruling fees are automatically transferred to your inactive wallet.

{% hint style="info" %}
Click [here](dispute-lifecycle.md) for further information about ruling fees.
{% endhint %}

### **As a normal user:**

* **Maintenance action fees:** Certain tasks (e.g. draft jury) reward the user with a small amount of DAI.
* **Appeal Fees:** Anyone can earn a reward in DAI for successfully appealing a dispute (i.e. correctly predicting a dispute's final ruling).

{% hint style="info" %}
Click [here ](dispute-lifecycle.md)for further information about appeal fees.
{% endhint %}

## **Subscription rewards**

As mentioned above, through subscription fees activated guardians can earn a monthly reward, in DAI, proportional to their active tokens, whether they are drafted or not.

### However, there are a few relevant factors guardians should consider about how these rewards are computed.

Subscription rewards can be claimed by guardians after each Court period.

{% hint style="info" %}
Note that Court periods are not the same as Court terms.

Each Court period lasts 90 Court terms, and with each term lasting 8 hours, this means each Court period lasts exactly 30 days.
{% endhint %}

Since subscription rewards are computed based on the active tokens each guardian has, we need to define a checkpoint in the whole Court period to check these balances and assign a portion of all the subscription fees to each guardian.

Because a guardian's balance can change during each period, to avoid gaming we are using the randomness assigned to the first Court term of the following period, i.e. a future event that cannot be known beforehand.

This effectively means that the longer guardians keep their tokens activated, the higher their chances to receive a portion of the subscription fees being assigned among them.

{% hint style="info" %}
For example, for the first period of Aragon Court, the resulting random checkpoint was the Court Term #84. This means if you had the minimum necessary tokens activated in Court Term #84, then you are eligible to claim rewards for the first Court period.
{% endhint %}

**So, to increase your chances of receiving subscription rewards after each Court period, you should keep your tokens activated as long as possible.**

## **Disputes**

![](<../../.gitbook/assets/Screenshot 2022-02-07 at 15.42.09.png>)

### Disputes are at the core of Aragon Court.

A dedicated page can be accessed by clicking the _**Disputes**_\*\* \*\* menu item in the side panel where you will see a list of disputes related to your account as well as every other past and active dispute.

**By clicking on one of them, you will get redirected to a page containing all the relevant details to this specific dispute, like its current status, description, timeline, and arguments.**

Additionally, every single task related to a dispute can be executed from here.

{% hint style="info" %}
[Click here](dispute-lifecycle.md) for a complete guide about the lifecycle of disputes and what you need to do as a guardian to manage them.
{% endhint %}

![](<../../.gitbook/assets/Screenshot 2022-02-07 at 15.44.08.png>)
