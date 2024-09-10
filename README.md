# aelf DAO Smart Contract

This guide will walk you through the steps to deploy a DAO (Decentralized Autonomous Organization) smart contract on the aelf testnet, acquire testnet ELF tokens, and interact with your deployed contract.</br>


## Prerequisites

- Ensure you have the aelf CLI tools installed.
- Have a wallet address and password ready.

## Steps

### 1. Create a wallet

Run this command to create an aelf wallet:

```shell
aelf-command create
```

### 2. Export Wallet Address and Password

Then export your wallet address and password as environment variables:

```shell
export WALLET_ADDRESS=your_wallet_address_here
export WALLET_PASSWORD=your_password_here
```
```shell
E.g.
export WALLET_ADDRESS=renvwy4neaUgk2ce1qztSSbEjjt1zupQf1UzuR5jbQucUjXfi
```

### 3. Acquire Testnet ELF Tokens

To deploy smart contracts or execute on-chain transactions on aelf, you'll require testnet ELF tokens. Use the following command to get testnet ELF tokens:

```shell
curl -X POST "https://faucet.aelf.dev/api/claim?walletAddress=$WALLET_ADDRESS" -H "accept: application/json" -d ""
```

To check your ELF balance, use the following command:

```shell
aelf-command call ASh2Wt7nSEmYqnGxPPzp4pnVDU4uhj1XW9Se5VeZcX2UDdyjx -a $WALLET_ADDRESS -p $WALLET_PASSWORD -e https://tdvw-test-node.aelf.io GetBalance
```
```shell
✔ Fetching contract successfully!

If you need to pass file contents as a parameter, you can enter the relative or absolute path of the file

Enter the params one by one, type `Enter` to skip optional param:
? Enter the required param <symbol>: ELF
? Enter the required param <owner>: renvwy4neaUgk2ce1qztSSbEjjt1zupQf1UzuR5jbQucUjXfi
The params you entered is:
{
  "symbol": "ELF",
  "owner": "renvwy4neaUgk2ce1qztSSbEjjt1zupQf1UzuR5jbQucUjXfi"
}
✔ Calling method successfully!
AElf [Info]: 
Result:
{
  "symbol": "ELF",
  "owner": "renvwy4neaUgk2ce1qztSSbEjjt1zupQf1UzuR5jbQucUjXfi",
  "balance": "19705422500"
} 
✔ Succeed!
```
Or you can check from the website, the account will be created on Mainchain AELF within aelf Testnet
```shell
https://testnet.aelfscan.io/AELF/address/ELF_renvwy4neaUgk2ce1qztSSbEjjt1zupQf1UzuR5jbQucUjXfi_AELF
```
### 4. Prepare the Smart Contract

Ensure your smart contract is compiled and ready for deployment. Set the path to your contract:

```shell
export CONTRACT_PATH=$(find ~+ . -path "*patched*" | head -n 1)
```

### 5. Deploy the Smart Contract

Use the following command to deploy your smart contract:

```shell
aelf-deploy -a $WALLET_ADDRESS -p $WALLET_PASSWORD -c $CONTRACT_PATH -e https://tdvw-test-node.aelf.io/
```
```shell
Start to deploy contract: 
/home/hien/aelfContracts/capstone_aelf/src/bin/Debug/net6.0/BuildersDAO.dll.patched
Using account: renvwy4neaUgk2ce1qztSSbEjjt1zupQf1UzuR5jbQucUjXfi

Deploying contract without audit.
Added Genesis Contract address to whitelist successfully.        
                                                                 
[Processing]: ProposalId=93b01f909b38962557bc0c39fbb0e151c3243b3e1fe8bc662fa9fbebfed2922b,eploying contract ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ ⣷    
ToBeReleased: False, using time: 01s: 291ms                      
[Processing]: ProposalId=93b01f909b38962557bc0c39fbb0e151c3243b3e1fe8bc662fa9fbebfed2922b,eploying contract ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ ⣻    
ToBeReleased: False, using time: 02s: 582ms                      
[Processing]: ProposalId=93b01f909b38962557bc0c39fbb0e151c3243b3e1fe8bc662fa9fbebfed2922b,eploying contract ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ ⣟    
ToBeReleased: False, using time: 03s: 887ms                      
[Processing]: ProposalId=93b01f909b38962557bc0c39fbb0e151c3243b3e1fe8bc662fa9fbebfed2922b,eploying contract ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ ⣷    
ToBeReleased: False, using time: 05s: 265ms                      
[Processing]: ProposalId=93b01f909b38962557bc0c39fbb0e151c3243b3e1fe8bc662fa9fbebfed2922b,eploying contract ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ ⣽    
ToBeReleased: False, using time: 06s: 680ms                      
[Processing]: ProposalId=93b01f909b38962557bc0c39fbb0e151c3243b3e1fe8bc662fa9fbebfed2922b,eploying contract ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ ⡿    
ToBeReleased: False, using time: 08s: 009ms                      
[Processing]: ProposalId=93b01f909b38962557bc0c39fbb0e151c3243b3e1fe8bc662fa9fbebfed2922b,eploying contract ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ ⣯    
ToBeReleased: False, using time: 09s: 374ms                      
[Processing]: ProposalId=93b01f909b38962557bc0c39fbb0e151c3243b3e1fe8bc662fa9fbebfed2922b,eploying contract ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ ⣽    
ToBeReleased: False, using time: 10s: 725ms                      
[Processing]: ProposalId=93b01f909b38962557bc0c39fbb0e151c3243b3e1fe8bc662fa9fbebfed2922b,eploying contract ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ ⣽    
ToBeReleased: True, using time: 12s: 308ms                       
Author: "renvwy4neaUgk2ce1qztSSbEjjt1zupQf1UzuR5jbQucUjXfi"      
Code hash: 4a40f62a52666918519309442979281eb8bee2e424c93088c637be6d60a6f33a
Address: "GxahuPgJfxqqy43ycUYLK4heaxRP7UpiX9eEtEGV6EV1FELuS"     
Version: 1contract ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ ⣻    
ContractVersion: 1.0.0.0                                         
Height: 138060743
Deploy Contract Info: { "serialNumber": "2152", "author":        
"renvwy4neaUgk2ce1qztSSbEjjt1zupQf1UzuR5jbQucUjXfi", "codeHash": 
"4a40f62a52666918519309442979281eb8bee2e424c93088c637be6d60a6f33a", "version": 1, 
"contractVersion": "1.0.0.0", "isUserContract": true, "deployer": 
"renvwy4neaUgk2ce1qztSSbEjjt1zupQf1UzuR5jbQucUjXfi" }
Contract deployed.     
```

If the deployment is successful, you'll receive a contract address. Save this address for future interactions:

```shell
export CONTRACT_ADDRESS="your_contract_address_here"
```
```shell
E.g.
export CONTRACT_ADDRESS="GxahuPgJfxqqy43ycUYLK4heaxRP7UpiX9eEtEGV6EV1FELuS"
```
If you re-deploy same contract, the deployment will be failed

```shell
Start to deploy contract: /home/hien/aelfContracts/capstone_aelf/src/bin/Debug/net6.0/BuildersDAO.dll.patched
Using account: renvwy4neaUgk2ce1qztSSbEjjt1zupQf1UzuR5jbQucUjXfi

Deploying contract without audit.
Added Genesis Contract address to whitelist successfully.        
                                                                 
Deployment failed: AElf.Sdk.CSharp.AssertionException: contract code has already been deployed before.
Will close this deployment tool.━━━━━━━━━━━━━━━━━━━━━━━━━━━ ⣾    
                                                                 
Deploying contract ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ ⣾    
                                                                 
```
You can find the contract here, it'll be deployed in sidechain tDVW within aelf Testnet
```shell
https://testnet.aelfscan.io/tDVW/address/ELF_GxahuPgJfxqqy43ycUYLK4heaxRP7UpiX9eEtEGV6EV1FELuS_tDVW?tab=contract
```

### 6. Interact with the Deployed Contract

Now that your contract is deployed, you can interact with it using the aelf-command CLI.

#### Initializing the DAO

```shell
aelf-command send $CONTRACT_ADDRESS -a $WALLET_ADDRESS -p $WALLET_PASSWORD -e https://tdvw-test-node.aelf.io Initialize
```
```shell

```
#### Join the DAO
```shell
aelf-command send $CONTRACT_ADDRESS -a $WALLET_ADDRESS -p $WALLET_PASSWORD -e https://tdvw-test-node.aelf.io joinDAO
```
```shell

```
#### Create a Proposal
```shell
aelf-command send $CONTRACT_ADDRESS -a $WALLET_ADDRESS -p $WALLET_PASSWORD -e https://tdvw-test-node.aelf.io CreateProposal
```
```shell

```
#### Vote on a Proposal
```shell
aelf-command send $CONTRACT_ADDRESS -a $WALLET_ADDRESS -p $WALLET_PASSWORD -e https://tdvw-test-node.aelf.io VoteOnProposal
```
```shell

```

#### Get All Proposals
```shell
aelf-command call $CONTRACT_ADDRESS -a $WALLET_ADDRESS -p $WALLET_PASSWORD -e https://tdvw-test-node.aelf.io GetAllProposals
```
```shell

```

#### Get Member Count
```shell
aelf-command call $CONTRACT_ADDRESS -a $WALLET_ADDRESS -p $WALLET_PASSWORD -e https://tdvw-test-node.aelf.io GetMemberCount
```
```shell

```

#### Check if an Address is a Member
```shell
aelf-command call $CONTRACT_ADDRESS -a $WALLET_ADDRESS -p $WALLET_PASSWORD -e https://tdvw-test-node.aelf.io GetMemberExist
```
```shell

```
### 7. Verify Contract Deployment

You can verify your contract deployment by checking the transaction status or by calling a method on your contract.

### 8. Best Practices

- Always keep your wallet private key and password secure.
- Test your smart contract thoroughly on the testnet before deploying to mainnet.
- Monitor your contract's performance and interactions regularly.

### 9. Troubleshooting

If you encounter issues during deployment or interaction:
- Double-check your wallet address and password.
- Ensure you have sufficient testnet ELF tokens.
- Verify that your contract code compiles without errors.
- Check the aelf network status and ensure you're connected to the correct endpoint.

## Contract Details
The DAO smart contract includes the following main functions:

- Initialize: Sets up the initial state of the DAO.
- joinDAO: Allows an address to join the DAO.
- CreateProposal: Creates a new proposal for the DAO.
- VoteOnProposal: Allows DAO members to vote on proposals.
- GetAllProposals: Retrieves all proposals in the DAO.
- GetProposal: Retrieves a specific proposal by ID.
- GetMemberCount: Returns the total number of DAO members.
- GetMemberExist: Checks if a given address is a DAO member.

For more detailed information about each function and its parameters, refer to the smart contract code.