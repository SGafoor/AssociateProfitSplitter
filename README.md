# AssociateProfitSplitter

Navigate to the [Remix IDE](https://remix.ethereum.org) and create a new contract called AssociateProfitSplitter.sol.

While developing and testing your contract, use the [Ganache](https://www.trufflesuite.com/ganache) development chain, and point MetaMask to localhost:8545.

![image](https://user-images.githubusercontent.com/83382006/135957905-908eda31-0b35-4bb1-89a2-9a4c7aaa3765.png)


### Level One: The `AssociateProfitSplitter` Contract

Create a constructor function that accepts:

* address payable _one

* address payable _two

* address payable _three


![image](https://user-images.githubusercontent.com/83382006/136111582-3a62af4c-8a99-434b-a0b7-84650a4211fc.png)

Within the constructor, set the employee addresses to equal the parameter values. This will allow you to avoid hardcoding the employee addresses.

Next, create the following functions:

* deposit — This function should be set to public payable check, ensuring that only the owner can call the function.

  * In this function, perform the following steps:

    * Set a uint amount to equal msg.value / 3.

    * Transfer the amount to employee_one.

    * Repeat the steps for employee_two and employee_three.
    
    * transfer the msg.value - amount * 3 back to msg.sender. This will re-multiply the amount by 3, then subtract it from the msg.value to account for any leftover wei, and send it back to human resources.

* Create a fallback function and call the deposit function from within it. This will ensure that the logic in deposit executes if ether is sent directly to the contract. This is important to prevent ether from being locked in the contract, since we don't have a withdraw function in this use case.

#### Test the contract

In the `Deploy` tab in Remix, deploy the contract to your local Ganache chain by connecting to Injected Web3 and ensuring MetaMask is pointed to localhost:8545.

![image](https://user-images.githubusercontent.com/83382006/136111671-56c0d9d7-453d-4fdb-9bc1-7bca9c3f4d02.png)

Test the deposit function.

![image](https://user-images.githubusercontent.com/83382006/136110590-ae0db672-7e2a-4523-a334-063b854ecb27.png)

![image](https://user-images.githubusercontent.com/83382006/136110629-39720162-9111-4638-b527-722dee0ba869.png)

![image](https://user-images.githubusercontent.com/83382006/136111285-246ce59f-a5b6-4fd6-ba97-182a57be146d.png)

![image](https://user-images.githubusercontent.com/83382006/136111942-b8142e19-6a5e-4f15-8a35-8914aaba3c84.png)

