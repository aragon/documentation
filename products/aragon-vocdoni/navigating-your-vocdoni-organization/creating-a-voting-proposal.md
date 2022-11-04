# Creating a voting proposal

{% hint style="info" %}
In this section, you will learn how to create a voting process in the Aragon Vocdoni Organization.
{% endhint %}

## Steps for creating a voting proposal

### Create a Vote

On the top right click on the name of your entity/organization select the **Dashboard** option.

![Dashboard page - Create a voting process](<../../../.gitbook/assets/Schermata 2022-03-07 alle 14.40.42.png>)

Click on the _**Create a voting process**_ and fill in the fields on the _**New Vote**_ page.

### Details page

{% hint style="info" %}
**Title:** the title of your voting process

**Header image:** the header to your voting process

**Documentation (optional field):** here you can add an URL to the documentation related to this voting process (it could be a link to a web, a cloud, a folder)

**Questions and Answers (optional field):** here you can add an URL to a question and answer system (it could be a forum, e-mail, website, telegram group)

**Video stream link (optional field):** here you can add an URL to a video (like a Youtube video)

**Description:** the description of the voting process

**Question:** the question of the voting process (what is the vote about). Each question has a Title, a Description, and Options (these are the options among which the users can choose at the voting time). More options can be added using the **Add an option** button.
{% endhint %}

The voting process can have more than one question. More questions can be added using the _**Add a question**_ button.

![New vote page details](<../../../.gitbook/assets/Schermata 2022-03-07 alle 14.45.39.png>)

The _**Preview**_ button shows a preview of the voting process.

![Preview of the Voting process](<../../../.gitbook/assets/Schermata 2022-03-07 alle 15.01.20.png>)

### Who can Vote Page

On the _**Who can Vote**_ page you can:

* _**Select voting type**_**:**&#x20;
  * _normal voting_ (where all the voters have the same voting power)&#x20;
  * _weighted voting_ (where voters may have different voting power)
* _**Select voting options**_**:** you can enable anonymous voting (_**yes**_ or _**no**_ option). In our example, we have selected the anonymous voting option.
* _**Import the list of voters**_**:** only the voters on the list can vote in the voting process. To create the list of voters you can download the available template (_**Download template**_ button), adjust the fields (you can add for example the National Id) and then drag and drop the file (.csv, .xlsx, .ods formats are supported).

{% hint style="warning" %}
**Anonymous voting** allows users to vote with the **cryptographic assurance** that nobody can correlate their identity with the contents of their ballot. You can read more about anonymous voting [here](https://blog.aragon.org/introducing-vocdoni-anonymous-voting/).
{% endhint %}

<figure><img src="../../../.gitbook/assets/vote.png" alt=""><figcaption><p>Who can vote page</p></figcaption></figure>

When the list of voters loading is completed a **Form preview** is shown. This form will be filled in but the community in order to vote. Accept the disclaimer and **continue.**

<figure><img src="../../../.gitbook/assets/Loaded Template.png" alt=""><figcaption><p>Form for the voters</p></figcaption></figure>

### Settings Page

On the _**Settings**_ page enter:

The **Calendar** settings:

* _**Start Date**_**:** the start date at which votes are accepted. It could start on a specific date or start right away. The start date of the voting process must start at least 10 min in the future.
* _**End Date**_**:** the date until votes are accepted.

{% hint style="danger" %}
Anonymous voting requires an **additional voter pre-registration** step, which begins immediately after the process creation is completed and will last until the voting start date.
{% endhint %}



The **Results Availability**:

* _**In Real-Time:**_ the voting results are shown as soon as the first vote is submitted
* _**After vote**_**:** the voting results are shown only when the voting process is closed.

<figure><img src="../../../.gitbook/assets/new vote period.png" alt=""><figcaption></figcaption></figure>

### Creation page

After clicking the _**Continue**_ button the vote process will be created.

![Creation voting process](<../../../.gitbook/assets/Schermata 2022-03-07 alle 15.35.10.png>)

### Ready page

After the vote is set, the _**ready page**_ will show the voting process link.&#x20;

{% hint style="success" %}
Share the voting process link with the voters. :partying\_face:
{% endhint %}

Now, in your _**Dashboard,**_ the **Upcoming Vote** is 1**.**&#x20;

<figure><img src="../../../.gitbook/assets/Upcoming vote.png" alt=""><figcaption><p>The upcoming vote is 1.</p></figcaption></figure>

When the voting process starts the **Active vote** will be 1 (and the Upcoming vote return 0). Now the voters can cast their votes.

![Active vote in the Dashboard.](<../../../.gitbook/assets/Schermata 2022-03-07 alle 15.39.41.png>)

### Vote details

To access, the vote information goes to the _**Dashboard**_ and click on the Vote. A **Vote details** page will be opened.

<figure><img src="../../../.gitbook/assets/Upcoming voting details.png" alt=""><figcaption><p>Vote details page</p></figcaption></figure>

* If you need to cancel or end a vote, go to the _**Dashboard**_ and click the Vote you need to cancel or end. On the _**Vote details**_ page click the _**Cancel Vote**_ or _**End Vote**_ button.
* If you need to share the Voting link with the community go to the _**Dashboard**_ and click the Vote that you want to share. On The _**Vote details**_ page is available the link.
*   To pre-register for the upcoming vote, go to the _**Dashboard**_ and click the Vote you want to pre-register. On the _**Vote details**_ click the _**Preview**_ button: a dedicated page with the vote details will be opened. A _**Pre-register**_ button allows the user to pre-register for the upcoming vote process.&#x20;

    <figure><img src="../../../.gitbook/assets/Preview button.png" alt=""><figcaption></figcaption></figure>



> <mark style="color:purple;">**Do you have a question? Leave your comments here at our Discourse forum**</mark>** 👇**

{% embed url="https://support.aragon.org/t/aragon-vocdoni-navigate-your-organization-create-a-vote/65/2" %}
