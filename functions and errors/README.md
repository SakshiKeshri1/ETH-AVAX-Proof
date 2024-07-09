## Smart Contract Project

In this, we have to create a smart contract that implements require(), assert() and revert() statements. This solidity contract implements the simple voting system where owner can create and users can vote on them.

## Description

I have done this project on the Remix Editor which is a coding platform and had set up the environment so it can compile and run successfully without any error.

I have use the pragma solidity ^0.8.25 version in this code and the License is //SPDX-License-Identifier : MIT

This Solidity smart contract project implements a basic voting system with functionalities create, manage and vote on proposals.

a. voteproposal(): a structure to hold proposals details includeing description, countvote and existence flag in it.

b. proposals(): a mapping from proposal id to voteproposal structs, storing all proposals.

c. hasvoted(): a nested mapping to track if an address has voted on a specific proposal. It maps and address to another mapping, which maps proposal id to a boolean which indicates that address gas voted on a specific proposal.

d. owner: address of contract owner.

//state variables
e. countproposal: to keep track of the number of proposals.

f. owneronly: a modifier to restrict certain functions in the code.

g. checkvote(uint id): checks if a proposal id exists.

h. recordvotes(uint id): it allows the address to vote on the proposal if checkvotes returns true after condition is met and increment the vote count for the proposal.

i. getvotecount(uint id): returns the vote count for a specific id.

j. removeproposal(uint id): allows the owner to mark the proposal as non-existent

k. receive(): it reverts any ether sent to the contract as it ensures it does not accept any payments.

To run code you can visit:  https://remix.ethereum.org/

In this site, click on VotingSystem_.sol under deafault_workspace

## Usage

*require(): this function is used to validate the input and conditions before executing the code. It further checks if a condition is true and if not, it revert the the transaction. It is used for input, precondition and access control.

*assert(): this function is used to check the condition given that should never be false. If an assert condition fails, it indicates a bug in the contract and revert the transaction. If the condition is true then function execution continues and jump to the next statement.

*revert(): function is used to explicitly revert the transaction, it can be used with or without error message. It is useful for conditional checks. It is often used to given more detailed information about the reason for thr failure.

## Code

```
/ SPDX-License-Identifier: MIT

pragma solidity 0.8.25;

contract VotingSystem_{
    struct Voteproposal {
        string descp;
        uint countVote_;
        bool exists;
    }

    mapping(uint=>Voteproposal) public proposals;
    mapping(address=>mapping(uint=>bool)) public hasVoted;

    uint public Countproposal;
    address public Owner;
```

## Author
Name- Sakshi Keshri
contact- keshrisakshi073@gmail.com

## License
MIT License

Copyright (c) 2024 SakshiKeshri1

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

