# Forwarding

{% hint style="success" %}
Use <mark style="color:purple;">**forwarders**</mark> to allow app interoperability and governance.
{% endhint %}

## How does it work?

The ACL allows Aragon apps to be interoperable by creating and managing permissions.

A **Forwarder** is a contract that, given some conditions, will pass along a certain action to other contract(s).

### Example

A _Token Manager_ app may send an action to the _Voting_ app so if a vote passes the _Voting_ app can withdraw funds from the _Finance_ app.

This is possible thanks to Forwarders.&#x20;

Below is an extract of our _Voting_ app and is all the code required to make it a Forwarder:

```solidity
pragma solidity 0.4.24;

import "@aragon/os/contracts/apps/AragonApp.sol";
import "@aragon/os/contracts/common/IForwarder.sol";

contract Voting is IForwarder, AragonApp {
    /**
    * @notice Creates a vote to execute the desired action, and casts a support vote
    * @dev IForwarder interface conformance
    * @param _evmScript Start vote with script
    */
    function forward(bytes _evmScript) public {
        require(canForward(msg.sender, _evmScript));
        _newVote(_evmScript, "", true);
    }

    function canForward(address _sender, bytes _evmCallScript) public view returns (bool) {
        return canPerform(_sender, CREATE_VOTES_ROLE, arr());
    }

    function isForwarder() public pure returns (bool) {
        return true;
    }
}
```

`canForward` checks if a caller `canPerform` the action `CREATE_VOTES_ROLE`. If it can, it means the caller can create a vote.

`forward` checks if a caller `canForward`, and if it can, it creates a new vote with an `_evmScript`.

This `_evmScript` is the action that will be executed if the voting passes, which can be withdrawing some funds from a _Finance_ app, for example, but it can be any other action. The action is abstracted and doesn't need to be known in advance.

