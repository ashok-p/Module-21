
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

### Optional Features 
Use OpenZeppelin to extend the functionality of your crowdsale contract by adding time restrictions, refund capabilities, and a cap for the number of tokens that may be created.

The optional component is coded and deployed in the final code.

To test the Optional Features, these steps were followed:

- Send ether to the crowdsale from a different account (not the same account that is raising funds). Then, once you confirm that the crowdsale works as expected, try to add the token to your wallet and test a transaction.  

- the close time is set `now + 5 minutes`  

- When sending ether to the contract, make sure that you meet the contract’s `goal`. Then, finalize the sale using the Crowdsale contract's `finalize` function. To finalize the sale, `isOpen` must return false.

- View your tokens in `MetaMask`. In `MetaMask`, click Add Token, then click Custom Token, and enter the token contract’s address. Make sure to purchase higher amounts of tokens in order to see the denomination appear in your wallet as more than a few wei worth.

Example -[10000 cap. Purchased 7K tokens](Images/7k_pur_10k_cap.png) first, [then 3K](Images/3k_pur.png). [Goal Reached](Images/goal_10k_reached.png). Did a lot more testing with many scenerios, but did not save the screenshots everytime. Only saved a few to demonstrate that it was done.

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

* Images
    - 4connect_ganache_remix_metmask.mov      (low resolution mov file)
    - acct3_bal_95eth.png
    - acct3_wants_t_buy_3_tokens.png
    - all_accounts_updated.png
    - connect_ganache_remix_metmask.mov       (high resolutuion mov file)
    - total_supply_of_tokens.png
    - wallet_before.png
    - wallet_final.png
* KaseiCoin.sol                               (coin contract)
* KaseiCoinCrowdsale.sol                      (coin crowdsale contract)
* README.md                                   ( you're reading this file)
* Starter_Code                                (Starter Code)
    - KaseiCoin.sol
    - KaseiCoinCrowdsale.sol
    - README.md
---
---

## Deploy the KaseiCoinCrowdsale smart contract 
For the purpose of crowdsale, a deployer contract `KaseiCoinCrowdsaleDeployer` was defined in the file named `KaseiCoinCrowdsale.sol`. The same file also contains the `KaseiCoinCrowdsale` contract. The deployer contract deploys `KaseiCoin` contract, which is the minter contract, and `KaseiCoinCrowdsale` contract - the crowdsale contract. The minting rights are passed on to `KaseiCoinCrowdsale` contract so that tokens can be purchased and minted at the same time.

The contracts are deployed using Remix IDE. 

* Invoke [Remix IDE - https://remix.ethereum.org/](https://remix.ethereum.org/) on your web browser like `Chrome`. 
* Follow the steps outlined below to deploy the contract:
    - Use `Open Files` in the **File** section to navigate to and select [KaseiCoinCrowdsale.sol](Images/click_on_contract.png)
    - [Click on compile icon](Images/click_on_compile_icon.png) to [compile](Images/compile_contract.png) the contract   
    - [Deploy](Images/click_on_deploy_and_run_icon.png) by clicking on the icon below the Compile icon.   
    - Now [click to the Metmask (fox) sign](Images/select_account_for_deployment.png) and [select the account for deployment](Images/pick_account.png)
    - Click on the Contract list to [select](Images/pick_deployer_contract.png) the deployer [contract](Images/contract_selected.png)      
    - [Fill](Images/fill_the_Deployer_fields.png ) the deployer fields    
    - [Get the wallet address](Images/pick_wallet_address_from_Ganache.png) from Ganache. 
    - [Click on Transact](Images/deploy_clicking_transact.png) to Deploy  
    - Now, deploy the crowdsale contract to Remix by following
        - [click on crowdsale](click_crowdsale_from_deployed_contract.png) from the Deployed Contracts, and copy the address
        - [select the crowdsale](Images/select_crowdsale_contract.png) contract from the list of contracts
        - [paste the address copied above at field next to At Address](Images/paste_next_to_at_addr_n_click_At_Addr.png) and click on `At Address`
     - Follow the same procedure as last 3 steps for the token contract
        - [select KaseiCoin token](Images/select_coin_contract.png)
        - [copy and paste the contract address](Images/paste_at_addr_n_click.png) and click `At Address`  
    - You can see that now all the functions in both the contracts are visible now - [KaseiCoinCrowdsale Contract](Images/all_the_functions_visible_now.png), [KaseiCoin](Images/all_the_functions_2.png)

From here on you can run the various functions to purchase and track the tokens etc. See the 
**Contract Deployment and Evaluation Evidence** section above for the sample tests.

---
---

## Technologies
The application is developed using:  
* Language: Solidity  
* Development Environment: VS Code and Terminal, Metamask, Ganache, Remix
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
