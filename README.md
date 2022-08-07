
# Module-21-Challenge - Building ERC20 based KaseiCoin(KSA) Cryptocurrency For Interstellar Usage using Solidity

--- 
---
## User Story
After waiting for years and passing several tests, you were selected by the Martian Aerospace Agency to be part of the first human colony on Mars. As a prominent fintech professional, you were chosen to lead a project to develop a monetary system for the new Mars colony. You have decided to base this new monetary system on blockchain technology, and to define a new cryptocurrency called KaseiCoin. (“Kasei” means “Mars” in Japanese.)

KaseiCoin will be a fungible token that is ERC-20 compliant. You will launch a crowdsale that will allow people who are moving to Mars to convert their earthling money to KaseiCoin.

The Starter Code was provided to expedite the development process. Remix IDE is used for the development and testing.

---
---
## Acceptance Criteria  

Create and work within a local blockchain development environment using the JavaScript VM provided by the Remix IDE. The starter code should be used to:

* Create the KaseiCoin token contract.

* Create the KaseiCoin crowdsale contract.

* Create the KaseiCoin deployer contract.

* Deploy the crowdsale to a local blockchain by using Remix, MetaMask, and Ganache.

* Record a short video or take several screenshots that show the deployed contract in action.

* Optional: Use OpenZeppelin to extend the functionality of your crowdsale contract by adding time restrictions, refund capabilities, and a cap for the number of tokens that may be created.

---
---
## The Application

The Starter code was modified in `Remix IDE` as follows:

### Create the KaseiCoin token contract
Create the smart contract using `ERC20` standard utilizing `ERC20`, `ERC20Detailed` and `ERC20Mintable` modules from the `OpenZeppelin` library. 
### Create the KaseiCoin crowdsale contract
Create the crowdsale smart contract using `Crowdsale`, `MintedCrowdsale` modules from the `OpenZeppelin` library.
### Create the KaseiCoin deployer contract
The deployer contract deploys the `token` and '`crowdsale` contracts, assigning the minting rights to the `crowdsale` contract, so that users could easily mint and purchase tokens. 
### Contract Deployment and Evaluation Evidence
1. Deploy the crowdsale contract using Remix, Metamask and Ganache. [Click here to witness how Remix,Metamask and Ganache are deployed together.](https://drive.google.com/file/d/1Be7rHMBudu9AhkO6leiIVNajsEjprd_n/view?usp=sharing).

2. Follow the following screenshots to verify the purchase of new tokens using test accounts in `Ganache` & `Metamask` and checking the associated balances.
* [Wallet before Purchasing the tokens](Images/wallet_before.png). Wallet balance is at 125.57 ETHs. Also, The Remix image shows `35` tokens. The amount shown is in `wei`.
* [Account Balance (account ending in 3CEA) before starting out](Images/acct3_bal_95eth.png). The account has 95ETHs.
* [Account 3 wants to buy 3 tokens](Images/acct3_wants_t_buy_3_tokens.png)
* [Post Purchase, all accounts updated](Images/all_accounts_updated.png). After purchase the balance in the account ending in 3CEA has reduced to 92, confirming the token purchase amount of 3ETHs. 
* [Total Supply of tokens](Images/total_supply_of_tokens.png). It has gone from 35 to 38. The unit here shows equivalent numbers in `wei`. 
* [Wallet final](Images/wallet_final.png). Wallet total has gone up to 128.57 ETHs from 125.57, increase of 3 ETHs, as is also evident from the Remix screen that Wei raised has gone from `35` to `38` ETHs, or 3 ETHs. The figure shown is in in `wei`.

3. After purchasing tokens with test accounts, the total supply of minted tokens has gone from 35 to 38 ETH equivalent in wei, i.e.  3000000000000000000,  and the amount of wei that has been raised by the crowdsale is 3 ETHs as is seen above.

### Optional: Use OpenZeppelin to extend the functionality of your crowdsale contract by adding time restrictions, refund capabilities, and a cap for the number of tokens that may be created.



## Installation Guide

### Clone the application code from Github as follows:
copy the URL link of the application from its Github repository      
open the Terminal window and clone as follows:  

   1. %cd to_your_preferred_directory_where_you want_to_store_this_application  
    
   2. %git clone URL_link_that_was_copied_in_step_1_above   
    
   3. %ls       
        Module-21    
        
   4. %cd Module-21   

The entire application files in the current directory are as follows:

* execution_results              (screenshots used in README)
    - after_deposit_eth_1.png
    - click_on_compile.png
    - compile_success.png
    - compile.png
    - deploy.png
    - deployed_contract.png
    - deposit_eth_1.png
    - deposit_eth_5.png
    - deposit_eth_10.png
    - remix_main.png
    - select_joint_savings.png
    - set_addresses.png
    - withdraw_5_eth_acct_1.png
    - withdraw_10_eth_acct_2.png
    - withdrawl_insuff_funds.png
* joint_savings.sol             (solidity contract)
* README.md                     (this file.. you are reading)
* Starter_Code                  (Starter Code)
    - joint_savings.sol         (starter code)

---
---

## Deploy the JointSavings smart contract to Transfer and Withdraw funds
The **JointSavings** contract was deployed using Remix IDE. The contract is defined in the file named `joint_savings.sol`, installed above.
* Invoke [Remix IDE - https://remix.ethereum.org/](https://remix.ethereum.org/) on your web browser like `Chrome`.  
* Use `Open Files` in the **File** section to navigate to `joint_savings.sol`
* [click on `joint_savings.sol`](execution_results/remix_main.png) to compile and run
      
### Compile and Deploy the JointSavings Contract

* [Click on the image just top-left of Solidity Compiler text (looks like recycle sign)](execution_results/compile.png) to compile the contract. Look at the [Green checkmark](execution_results/compile_success.png)  for success!
* Click on the image just below the `solidity compiler` button to navigate to the [Deploy & Run Transactions](execution_results/deploy.png) pane, and make sure that “Remix VM (London)” is selected as the environment.
* Click the `Deploy` button to deploy your smart contract, and then confirm that it [successfully deployed](execution_results/deployed_contract.png).

### Interact with the Deployed JointSavings Contract
* Use the `setAccounts` function to define the authorized Ethereum address that will be able to withdraw funds from your contract.

>NOTE
You can either use the following Ethereum addresses or create new, dummy addresses on the Vanity-ETH (Links to an external site.) website, which includes an Ethereum vanity address generator.

>Dummy account1 address: 0x0c0669Cd5e60a6F4b8ce437E4a4A007093D368Cb
>Dummy account2 address: 0x7A1f3dFAa0a4a19844B606CD6e91d693083B12c0  

* [We used the above addresses.](execution_results/set_addresses.png) 

* Test the deposit functionality of your smart contract by sending the following amounts of ether. After each transaction, use the `contractBalance` variable to verify that the funds were added to your contract:

    - Transaction 1: [Send 1 ether as wei](execution_results/after_deposit_eth_1.png)
    - Transaction 2: [Send 10 ether as wei](execution_results/deposit_eth_10.png)
    - Transaction 3: [Send 5 ether as wei](execution_results/deposit_eth_5.png)
>NOTE
Remembering how to convert ether to wei and vice versa can be challenging. So, you can use a website like [Ethereum Unit Converter](https://eth-converter.com/) to ease doing the conversion.

* Once you’ve successfully deposited funds into your contract, test the contract’s withdrawal functionality by withdrawing:  

    - [5 ether into accountOne](execution_results/withdraw_5_eth_acct_1.png) 
    - [10 ether into accountTwo](execution_results/withdraw_10_eth_acct_2.png) 
    - [7 ether and check for insufficient funds](execution_results/withdrawl_insuff_funds.png)
    
You can review `contractBalance`, `lastToWithdraw` and `lastWithdrawAmount` variables to verify that the transaction accuracy in the screenshots above.

---
---

## Technologies
The application is developed using:  
* Language: Solidity  
* Development Environment: VS Code and Terminal
* OS: Mac OS 12.1

---
---

## Contributors 
Ashok Pandey - ashok.pragati@gmail.com, www.linkedin.com/in/ashok-pandey-a7201237  

---
---

## License
The source code is the property of the developer. The users can copy and use the code freely but the developer is not responsible for any liability arising out of the code and its derivatives.

---
---
