# Redbelly
Deploying Smart Contract In Redbelly Devnet
What you need :

Metamask with RBNT
Metamask connected to Redbelly Devnet Network
Brain
First, you need to connect to Redbelly Devnet by manually adding network :

Open metamask and click Add Network

Then click Add a network manually
Paste this settings :
Network Name: Devnet Redbelly
RPC URL: https://rbn-gcp-us-east5-a-0-b.devnet.redbelly.network:8545/
ChainID: 161
Currency Symbol: RBNT
Block explorer URL: https://monitoring.devnet.redbelly.network/

After adding Redbelly Devnet manually you need RBNT, for faucet heads up to Redbelly Discord: Redbelly Discord
And paste your wallet in #devnet-faucet.

Second , Go to Remix IDE and Create new contract and name it smartcontract.sol or whatever you like , Zoom the image if you cant see.


Press the smartcontract.sol and paste this code and click CTRL + S or Save :
If there’s an alert just click OK

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.4;
contract FunctionTypes{
 uint256 public number = 5;
 
 constructor() payable {}
 // 函数类型
 // function (<parameter types>) {internal|external} [pure|view|payable] [returns (<return types>)]
 // 默认function
 function add() external{
 number = number + 1;
 }
 // pure: 纯纯牛马
 function addPure(uint256 _number) external pure returns(uint256 new_number){
 new_number = _number+1;
 }
 
 // view: 看客
 function addView() external view returns(uint256 new_number) {
 new_number = number + 1;
 }
 // internal: 内部
 function minus() internal {
 number = number - 1;
 }
 // 合约内的函数可以调用内部函数
 function minusCall() external {
 minus();
 }
 // payable: 递钱，能给合约支付eth的函数
 function minusPayable() external payable returns(uint256 balance) {
 minus(); 
 balance = address(this).balance;
 }
}
After you paste the smart contract code go to the Solidity Compiler as shown below :


Solidity Compiler
Then Compile the smartcontract :


Compile smartcontract.sol
Use compiler version 0.8.18 or below and click Compile smartcontract.sol , After that you will see checkmark on the compiler logo

Now Heads up to Deploy & Transactions tab


Deploy & Transactions
Change the Environment to Injected Provider and connect your Metamask, Make sure you’re on the Redbelly Devnet !!!


Connect Metamask
Then Deploy your smartcontract.sol , and make sure you have the same settings as shown bellow with the GASLIMIT , WEI and the CONTRACT on the smartcontract.sol , If you sure you have the same settings click “ Deploy “ and “Confirm” on your Metamask.


Deploy
If you see this just click Send Transaction


Confirm


Successful transaction :


Transaction History
Click “Copy” and Check if you have a smart contract in Redbelly Block Explorer.


Paste your smart contract address to the Block Explorer.


Successfull
Now you already deploy smart contract on Redbelly Devnet , Congratulations
