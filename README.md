TITLE:-
A smart contract that implements the require(), assert() and revert() statements.

Description:-
The provided code is a Solidity smart contract named `AssertionContract` that contains three functions: `requireStatement`, `assertStatement`, and `revertStatement`. Let's describe each function's purpose and behavior:

1. `requireStatement(uint256 x, uint256 y)`: This function takes two unsigned integer parameters, `x` and `y`. Its purpose is to demonstrate the usage of the `require()` statement. The function verifies whether `x` is greater than `y`. If the condition evaluates to `true`, the function returns the difference between `x` and `y`. However, if the condition evaluates to `false`, the function reverts the transaction with the error message "x must be greater than y".

2. `assertStatement(uint256 x)`: This function takes an unsigned integer parameter, `x`. Its purpose is to showcase the usage of the `assert()` statement. Within the function, a local variable `y` is assigned the value `10`. The function asserts that `x` is greater than `y`. If the condition evaluates to `true`, the function returns the difference between `x` and `y`. However, if the condition evaluates to `false`, indicating an internal error or an invariant violation, the function triggers an exception, causing the transaction to be reverted.

3. `revertStatement()`: This function does not take any parameters. Its purpose is to demonstrate the usage of the `revert()` statement. Inside the function, two local variables, `x` and `y`, are initialized with values `5` and `10`, respectively. The function includes an if statement to check if `x` is less than or equal to `y`. If the condition evaluates to `true`, indicating that the requirement "x must be greater than y" is not met, the function halts execution and reverts the transaction with the specified error message. If the condition evaluates to `false`, the function completes execution without reverting.

In summary, this contract showcases different error handling mechanisms in Solidity. The `require()` statement is used for precondition checks, the `assert()` statement for internal error handling, and the `revert()` statement for exceptional conditions. These statements ensure proper validation and control flow within smart contracts.

Getting Started:-

Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract AssertionContract {
    function requireStatement(uint256 x, uint256 y) public pure returns (uint256) {
        require(x > y, "x must be greater than y");
        return x - y;
    }

    function assertStatement(uint256 x) public pure returns (uint256) {
        uint256 y = 10;
        assert(x > y);
        return x - y;
    }

    function revertStatement() public pure {
        uint256 x = 5;
        uint256 y = 10;
        if (x <= y) {
            revert("x must be greater than y");
        }
    }
}
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile HelloWorld.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "HelloWorld" contract from the dropdown menu, and then click on the "Deploy" button.
Once the contract is deployed, you can interact with it opening the deployed contract and going through assert and require statement by putting different values for x and y and seeing the output .

Authors:-
AnkitBisht
@AnkitBisht28

License:-
This project is licensed under the MIT License - see the LICENSE.md file for details
