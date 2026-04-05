# OwnerControl-9
OwnerControl.sol
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract OwnerControl {
    address public owner;

    constructor() {
        owner = msg.sender;
    }

    modifier onlyOwner() {
        require(msg.sender == owner, "Only owner can call this");
        _;
    }

    function changeOwner(address _newOwner) public onlyOwner {
        owner = _newOwner;
    }

    function restrictedFunction() public onlyOwner {
        // Hàm chỉ owner mới gọi được
    }
}
