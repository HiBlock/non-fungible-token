# How to issue ERC875 token

## 0. Prerequisite
In order to issue ERC875 token, we need several things as below:

- MetaMask
- Ethereum Network (Testnet or Mainnet)
- Remix

## Install MetaMask
Visit [MetaMask official website](https://metamask.io/) to install Chrome Extension.(Assume you have chrome browser) Of course you could have add-on for Firefox, Opera, or a new browser named Brave browser.

### Import wallet seed

> NOTE: because we are using ropsten testnet, don't import your ethereum mainnet wallet.

Here I used a test wallet generated by [ganache](http://truffleframework.com/ganache). You can find the mnemonic as following pictures:

todo: upload ganache screenshot

In Metamask main window,  
- click "Import using account seed phrase" link, 
- then input the seed (mnemonic) from ganache,
- input wallet seed
- input password, and click "ok"

Now you have an ethereum wallet for testing.   

Absolutely you can use any wallet to generate an address, e.g [MyEtherWallet(MEW)](https://www.myetherwallet.com/), [ImToken](https://token.im/), etc.

## Choose ethereum network
Yes we can choose ethereum mainnet to issue ERC875 token, but we also can have it with ropsten testnet. Here is the example with ropsten testnet.

todo: upload metamask network choose pic

### Get rEth from ropsten testnet
Visit [MetaMask Ether Faucet](https://faucet.metamask.io/) to request test ether for ropsten testnet.

- check the address info in user section, make sure it is your address.
- click "request 1 ether from faucet" in faucet section.
- return to metamask to check you have got the ether you requested.

## Issue ERC875 token

We will use [remix](https://remix.ethereum.org/) to deploy our new token to ropsten testnet.

### program smart contract

todo: upload sample token to github.
Here is a sample token code you can download.   
- Then visit [remix](https://remix.ethereum.org/), 
- create a new file named TicketPro,
- copy and paste sample code into remix
- settings tab, choose solidity version as "Current version:0.4.24+commit.e67f0147.Emscripten.clang"
- compile tab, click "start to compile"

### prepare to deploy token

prepare the deploy script as following:

```
["0xeffb5bae17c000000000000000000001","0xeffb5bae17c000000000000000000002","0xeffb5bae17c000000000000000000003","0xeffb5bae17c000000000000000000004","0xeffb5bae17c000000000000000000005","0xeffb5bae17c000000000000000000006","0xeffb5bae17c000000000000000000007","0xeffb5bae17c000000000000000000008","0xeffb5bae17c000000000000000000009","0xeffb5bae17c00000000000000000000a","0xeffb5bae17c00000000000000000000b","0xeffb5bae17c00000000000000000000c","0xeffb5bae17c00000000000000000000d","0xeffb5bae17c00000000000000000000e","0xeffb5bae17c00000000000000000000f","0xeffb5bae17c000000000000000000010","0xeffb5bae17c000000000000000000011","0xeffb5bae17c000000000000000000012","0xeffb5bae17c000000000000000000013","0xeffb5bae17c000000000000000000014","0xeffb5bae17c000000000000000000015","0xeffb5bae17c000000000000000000016","0xeffb5bae17c000000000000000000017","0xeffb5bae17c000000000000000000018","0xeffb5bae17c000000000000000000019","0xeffb5bae17c00000000000000000001a","0xeffb5bae17c00000000000000000001b","0xeffb5bae17c00000000000000000001c","0xeffb5bae17c00000000000000000001d","0xeffb5bae17c00000000000000000001e","0xeffb5bae17c00000000000000000001f","0xeffb5bae17c000000000000000000020","0xeffb5bae17c000000000000000000021","0xeffb5bae17c000000000000000000022","0xeffb5bae17c000000000000000000023","0xeffb5bae17c000000000000000000024","0xeffb5bae17c000000000000000000025","0xeffb5bae17c000000000000000000026","0xeffb5bae17c000000000000000000027","0xeffb5bae17c000000000000000000028","0xeffb5bae17c000000000000000000029","0xeffb5bae17c00000000000000000002a","0xeffb5bae17c00000000000000000002b","0xeffb5bae17c00000000000000000002c","0xeffb5bae17c00000000000000000002d","0xeffb5bae17c00000000000000000002e","0xeffb5bae17c00000000000000000002f","0xeffb5bae17c000000000000000000030","0xeffb5bae17c000000000000000000031","0xeffb5bae17c000000000000000000032"], "<contract name>", "<contract symbols text>", "<your organiser addr here>", "<your payment server addr here>", "<your token recipient address here>"
```

Attention the parameters with <>. Here are descriptions:

- **<contract name>**, a meaningful smart contract name
- **<contract symbols text>**, token symbols, like "ETH" for ethereum
- **<your organiser addr here>**, ticket organiser's wallet address
- **<your payment server addr here>**, the wallet will pay for gas
- **<your token recipient address here>**, the wallet address will receive your ERC875 token, to make it simple, you can copy and paste your wallet address from [alphawallet](https://www.awallet.io/).	


- After preparation for the deploy parameters, copy and paste the deploy script to input text field right to "Deploy" button in Run tab in the right pane in remix.
- There prompts a metamask window to confirm the gas for creation smart contract. 
- Click "submit" to confirm. Wait for the success for contract.
- During wait, you can click etherscan link to check the progress.
- here is an [example](https://ropsten.etherscan.io/tx/0x1cca5d86958c9727c8083ed863a7028fef48a5844997ab4dfa0d0f2c4ba4b476).

### import token in your alphawallet

- download and install [alphawallet](https://www.awallet.io/)
- Before import token, find your contract address deployed. You can find it easily from etherscan, e.g from last [example](https://ropsten.etherscan.io/tx/0x1cca5d86958c9727c8083ed863a7028fef48a5844997ab4dfa0d0f2c4ba4b476), 
- click [contract created address](https://ropsten.etherscan.io/address/0x204ffa2a3edacf4a32a4874155ece51521c023ae). 
- click qrcode for contract overview
- in your alphawallet, click "+"
- click the scaner in address field
- scan the qrcode
- click save

### enjoy your ERC875 token

Finally in your alphawallet, you could find your own ERC875 token in my wallet part.

You can redeem, sell, or transfer your own token like a ticket.

Enjoy it!
