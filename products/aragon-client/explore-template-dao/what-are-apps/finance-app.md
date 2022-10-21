# Finance App

The _**Finance app**_ is used to manage the financial resources of an organization.

## Purpose of the Finance App

* Checking **the balance** of each asset the organization owns.
* Checking the **history** of past transfers.
* Creating **new transfers** from the Finance app.

![](<../../../../.gitbook/assets/Schermata 2022-02-09 alle 09.52.02.png>)

## **Token Balance**

The _Token Balances_ section shows you the balance of each token owned by the organization.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62772c7d3a7e9ae190b0/file-eLUV9SRU2y.png)

## **Transfers**

The section shows you a history of past transfers that have been made using the Finance app, including information about the date of the transfer, what address the transfer was to or from, a reference with additional context about the transfer, and the amount of the transfer.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62832c7d3a7e9ae190b1/file-5lFKotQ4xB.png)

### The transfer history can be filtered by date, token symbol or transfer type

See the examples below.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a629604286364bc8f80c5/file-TXwf7noy6I.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62a52c7d3a7e9ae190b8/file-HWRr2HXIlA.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62b62c7d3a7e9ae190b9/file-vWgrnBRGM4.png)

#### For each transfer, you can click on the drop-down menu to get a link to view the transaction on the blockchain so you can see even more detail about the transfer:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62c904286364bc8f80cc/file-Puf5b59tKe.png)

#### If you need to export your transfer history for accounting in a separate app, there's an export button that you can use to export a CSV file:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62e604286364bc8f80ce/file-wgYMOA7KJK.png)

## **New Transfer**

### **Deposit Funds**

To send funds to your organization, you can create a deposit using the Finance app

* Click the _**New Transfer**_ button.
* Open the \_**Deposit** \_ tab.
* Select the token you want to deposit.
* Enter the amount.
* Enter an (optional) reference note.
* Then click the _**Submit** deposit_ button.

{% hint style="info" %}
For non-ETH tokens two transactions may be required to make a deposit.

The first transaction approves the Finance app to pull the deposit amount from your account balance, and the second transaction is the actual deposit transaction.

This is a safety feature to prevent the Finance app from pulling more funds from your account than you have explicitly authorized.
{% endhint %}

### **Withdrawal funds**

To create a new transfer from your organization to another address, you can create a withdrawal using the Finance app

* Click the _**New Transfer**_ button.
* Open the _**Withdrawal**_\*\* \*\* tab.
* Enter the address you want to make the transfer to.
* Enter what token you want to send.
* Enter the amount of tokens you want to send.
* Add (optionally) a reference note to provide more context for the transfer.

Once you have filled out all of this information you can click the _**Submit transfer**_ button to complete the action, if you have permission.

![Withdrawal funds - Finance App](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a63252c7d3a7e9ae190c4/file-L9njobkDLU.png)

### **Sign the transaction to create the New Transfer vote**

As mentioned before, all actions in the Company organization require a vote by token holders. Click _**Create transaction**_ then open your Ethereum provider to sign and send the transaction that creates the New Transfer vote.

![](https://lh3.googleusercontent.com/UXQwChFz66jOLkHe2GvPoJ\_dTc0dWafDE1aUsgS6GVP47AlL\_RNwSvBTLzZqQDq4M8rxpts6acwsYr2MIO4dRBwjJ6S56h8G1-w9f5c\_FJAK8usZabmT5WbQvR5bqCCXPr-fiGiX)

### **Vote on the transfer**

The transfer has to be approved by token holders. Cast a _**Yes**_ vote to approve the transfer and have the other token holders in the organization vote as well.

![](https://lh3.googleusercontent.com/BYjI\_u7oOJgw6s6\_0IVRxQy\_AAkEHiuc8aQes9a71HZNEknuNwO8FttrpeszbMIXY2j6AV7FfytR-eUi4Y\_eoILA\_WGjHiCz1cYasmUfj\_A0uhmod3bkh1ezWT6IhfP0GmyFmVG7)

### **The vote transaction is signed and sent to approve the transfer**

After confirmation, the transfer will execute.

![](https://lh4.googleusercontent.com/C86GPoGAqAHhOiN-534hCWcWFeLBfwv3gsnEZ\_aXKwbYeaj67c8nNnvb3\_AK5fEAwPm03a-btdc-mLNkdy\_u-ezuZQG-g7iAvtjfHFoBmZxpYLoukXi7FT88VWifr79\_L21sGjxC)

> <mark style="color:purple;">**Do you have a question? Leave your comments here at our Discourse forum**</mark>** 👇**

{% embed url="https://support.aragon.org/t/aragon-client-navigate-your-dao-finance-app/27/2" %}
