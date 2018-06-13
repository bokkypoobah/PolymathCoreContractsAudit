# IModuleRegistry

Source file [../../../contracts/interfaces/IModuleRegistry.sol](../../../contracts/interfaces/IModuleRegistry.sol).

<br />

<hr />

```javascript
pragma solidity ^0.4.23;


//Simple interface that any module contracts should implement
contract IModuleRegistry {

    /**
     * @dev Called by a security token to notify the registry it is using a module
     * @param _moduleFactory is the address of the relevant module factory
     */
    function useModule(address _moduleFactory) external;

    /**
     * @dev Called by moduleFactory owner to register new modules for SecurityToken to use
     * @param _moduleFactory is the address of the module factory to be registered
     */
    function registerModule(address _moduleFactory) external returns(bool);

    /**
     * @dev Use to get all the tags releated to the functionality of the Module Factory.
     * @param _moduleType Type of module
     */
    function getTagByModuleType(uint8 _moduleType) public view returns(bytes32[]);

}

```
