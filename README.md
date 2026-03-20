# Ownable-Counter-
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract OwnableCounter {
    address public owner;
    uint256 public count;

    constructor() {
        owner = msg.sender;
    }

    modifier onlyOwner() {
        require(msg.sender == owner, "Not owner");
        _;
    }

    function increment() public onlyOwner {
        count++;
    }

    function reset() public onlyOwner {
        count = 0;
    }
}
