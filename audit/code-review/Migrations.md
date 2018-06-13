# Migrations

Source file [../../contracts/Migrations.sol](../../contracts/Migrations.sol).

<br />

<hr />

```javascript
pragma solidity ^0.4.23;


contract Migrations {

    address public owner;

    uint public lastCompletedMigration;

    modifier restricted() {
        require(msg.sender == owner);
        _;
    }

    function Migrations() public {
        owner = msg.sender;
    }

    function setCompleted(uint _completed)public  restricted {
        lastCompletedMigration = _completed;
    }

    function upgrade(address _newAddress)public  restricted {
        Migrations upgraded = Migrations(_newAddress);
        upgraded.setCompleted(lastCompletedMigration);
    }
}

```
