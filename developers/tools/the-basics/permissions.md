# App permissions

{% hint style="success" %}
Use the <mark style="color:purple;">**Access Control List (ACL)**</mark> to control who can access your app's functionality.
{% endhint %}

## How does it work?

The ACL essentially just contains a set of who has permission to execute an action in an Aragon app and who can re-grant or revoke that permission.&#x20;

Most generally, an _Entity_ can hold the permission to call a function protected by _Role_ in an _App_, and their permission is managed by a _Manager_, who can revoke or regrant that permission.



### Example

Now let's say we have these 3 apps:

* A _Token Manager_ app, which represents BOB token holders and forwards all their intents to another app
* A _Voting_ app, which executes any arbitrary action after a voting of BOB token holders passes
* A _Finance_ app, which controls the funds of the organization

| Entity        | App     | Role       | Manager |
| ------------- | ------- | ---------- | ------- |
| Token Manager | Voting  | OPEN\_VOTE | Voting  |
| Voting        | Finance | WITHDRAW   | Voting  |

With the simple mapping in the table above, we have done the following:

* Given permission to BOB token holders, using the _Token Manager_, to open votes in the _Voting_ app
* Given permission to the _Voting_ app to withdraw funds from the _Finance_ app

{% hint style="info" %}
We have achieved a fully democratic way of withdrawing funds in Ethereum! :tada:
{% endhint %}

