# ITransferManager

Source file [../../../../contracts/modules/TransferManager/ITransferManager.sol](../../../../contracts/modules/TransferManager/ITransferManager.sol).

<br />

<hr />

```javascript
pragma solidity ^0.4.23;

import "../../interfaces/IPausable.sol";
import "../../interfaces/IModule.sol";

contract ITransferManager is IModule, IPausable {

    //If verifyTransfer returns:
    //  FORCE_VALID, the transaction will always be valid, regardless of other TM results
    //  INVALID, then the transfer should not be allowed regardless of other TM results
    //  VALID, then the transfer is valid for this TM
    //  NA, then the result from this TM is ignored
    enum Result {INVALID, NA, VALID, FORCE_VALID}

    function verifyTransfer(address _from, address _to, uint256 _amount, bool _isTransfer) public returns(Result);

    function unpause() onlyOwner public {
        super._unpause();
    }

    function pause() onlyOwner public {
        super._pause();
    }
}

```
