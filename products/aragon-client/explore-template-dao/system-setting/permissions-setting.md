# Permissions Setting

{% hint style="info" %}
In this section, we explore in-depth the Permissions setting. You can find a dedicated video at the end of this page.
{% endhint %}

## What is the Permissions app?

The _**Permissions app**_\*\* \*\* is used to view all of the current permissions that have been set in an organization and add or remove permissions as needed.

The permissions set by the Permissions app define which entities have what permissions to perform various actions in an organization.

For example, any account may have permission to create a vote but only token holders in an organization may have permission to cast a vote.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a697f2c7d3a7e9ae19121/file-gDcISkpUXb.png)

## **Browse by app**

The Permissions app shows a list of every **app installed** in the organization and **the address or token symbol** of that app. You can change _App permissions_ and _System permissions_.

![App permissions](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6a562c7d3a7e9ae1912e/file-0y5pgj1j2k.png)

![System permissions](../../../../.gitbook/assets/file-mnVytX0QZA.png)

### Every app has:

* a list of **actions that can be performed** on the app,
* a list of **actions that other entities have been given permission to perform** on the app,
* a list of **permissions that the app has been granted**.

{% hint style="info" %}
The image below shows the list of actions that can be performed by the _Finance_ App (_Action_ column), the other entities that have the permissions to perform these actions (_Assigned to entity_ column) and who has the authority to assign the permission to this entity (_Managed by_ column).
{% endhint %}

![Finance permissions example](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6a7104286364bc8f8145/file-NKD9Oqrl0V.png)

### Example

If we need to perform a \_**Create new payments** \_ on the Finance App, this action will pass through a vote in the Voting App. The reason behind is that the Create new payments action in the Finance App is assigned to the Voting entity.

### **Available permissions**

The Available permissions section shows:

* **what actions** can be performed on the app,
* **what entity** has permission to **perform** each action,
* **which entity manages** each action. This entity is called a “manager”.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b052c7d3a7e9ae19132/file-68mYNPchqp.png)

A **manager** has the ability to **choose which entities have permission to perform an action** _(Assign Permission)_ and the ability to **change the manager of that action** (_Manage Role_). These actions can be done using the drop-down menu under the three dots.

![](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.25.57 (1).png>)

### Assign Permissions

Click on the drop-down menu on the _three dots_ and select _Assign Permission._ Select an App under the _On App_ menu, an entity under the _Assign to Entity_ menu and an Action.

![Assign a permission](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.26.48.png>)

### Manage Role

Click on the drop-down menu on the \*\* **\_**three dots**\_ and select \_**Manage Role\*\*.\_ Select an update under the _**Update**_\*\* \*\* menu.

![Manage Permission](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.37.21.png>)

{% hint style="warning" %}
If a manager removes themselves as a manager of permission without re-assigning the manager role to another entity, then management of that action defaults to whichever entity manages the _**Create permissions**_\*\* \*\* action in the ACL app.

In the example below, the management of the action will be assigned to the Voting App.
{% endhint %}

![](<../../../../.gitbook/assets/Schermata 2022-03-09 alle 10.12.59.png>)

{% hint style="danger" %}
If the manager of action is set as `0x0000000000000000000000000000000000000001` then no new manager can be set and permissions granted for that action will be locked forever.
{% endhint %}

### Initialize Permission

If an action has not been given a manager yet, then it must be initialized. To initialize an action, enter the address (_Grant permission to_) of the entity that you want to manage the action, select which entity you want to grant permission to perform the action, then click the _Initialize permission_ button to initialize the permission, if you have permission to do so.

![](../../../../.gitbook/assets/inizialize.png)

### **Browse by entity**

Back on the main Permissions page, you have the ability to get an at-a-glance view of all of the permissions set in an organization in the _Browse by entity_ section.

Here, you can quickly see which entities have been granted permission to perform which actions in the organization.

Clicking \*\* **\_**View details\*\*\_ will take you to the permissions page for that entity.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b6104286364bc8f8153/file-W609vjv1Pi.png)

### **Add permission**

To give permission to an entity to perform an action on an app, click the _**Add permission**_ button, select which app you want the entity to perform the action on, select which entity you want to grant the permission to, then select the action you want to grant the entity permission to perform.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b732c7d3a7e9ae1913a/file-xsxDomUDSy.png)

Each app has different actions that an entity can be granted permission to perform.

Granting permission to an entity to perform these actions on these apps will allow them to:

#### **ACL (Access Control List)**

* Create permissions: create permissions that have not been initialized yet in any app that uses this ACL instance`*`

> `*`_These actions are very sensitive and will give the entity with permission to perform these actions almost complete control of your organization._

#### **EVM (Ethereum Virtual Machine) Script Registry**

* **Add executors**: add an executor to the organization`*`
* **Enable and disable executors**: enable and disable executors in an organization`*`

> `*` _These actions are very sensitive actions that will give the entity with permission to perform these actions almost complete control of your organization._

{% hint style="warning" %}
An executor is an interpreter for running scripts in an organization. All of the apps in an organization use the executors in the organization to execute scripts that are part of transactions sent to the app. Each script has an identifier that determines which executor is used for running the script.

For example, whenever a vote transaction is sent to the Voting app, the app runs a script, then uses an executor to execute the script in the transaction. You can find more documentation about executors in the [Aragon Developer Portal](https://hack.aragon.org/).
{% endhint %}

#### Kernel

* Manage apps: install apps, upgrade apps, and change default apps in an organization. The ACL and the EVM Script Registry are default apps in the organization. Whoever has permission to perform this action can also change the default Vault contract of the organization (which is the Vault that tokens will be sent to if tokens are sent to the address of an app that is not meant to accept token deposits). `*`

> `*` _These actions are very sensitive actions that will give the entity with permission to perform these actions almost complete control of your organization._

#### **Tokens**

* Mint tokens: create new tokens and transfer them to a specified address
* Issue tokens: create new tokens and transfer them to the organization's Tokens app, for later assignment to a specified entity
* Assign tokens: transfer tokens held by the Tokens app to a specified entity
* Revoke vesting: revoke token vesting from a specified entity
* Burn tokens: delete tokens held by a tokenholder, reducing the total token supply

#### **Voting**

* Create new votes: create a new vote
* Modify support: modify the Support parameter
* Modify quorum: modify the Minimum Approval % parameter

\_\_

{% hint style="info" %}
**Minimum Approval %** is the percentage of the total token supply that support for a proposal must be greater than for the proposal to be considered valid.

**Example 1**

If the Minimum Approval % is set to 20%, then more than 20% of the outstanding token supply must vote to approve a proposal for the vote to be considered valid. If a vote does not make quorum, then it will fail, even if more tokens voted to approve the proposal than voted against it.

**Example 2**

If the Minimum Approval % is set to 20% and 10% of the outstanding token supply votes against the proposal but only 15% vote in support, then the proposal will fail because it has not reached the Minimum Approval % threshold.
{% endhint %}

{% hint style="info" %}
**Support** is the percentage of votes on a proposal that the total support must be greater than for the proposal to be approved. For example, if “Support” is set to 51%, then more than 51% of the votes on a proposal must vote “Yes” for the proposal to pass.
{% endhint %}

#### Finance

* Create new payments: create a transfer from the Finance app to another entity
* Execute payments: trigger a recurring payment owed to an entity
* Change period duration: modify the duration in seconds between accounting periods
* Change budgets: modify how many tokens can be spent within a given accounting period
* Manage payments: enable and disable recurring payments

#### **Vault**

* Transfer Vault’s tokens: transfer tokens held by the Vault app

{% embed url="https://youtu.be/kMF7Y_KPm-4?t=666" %}
