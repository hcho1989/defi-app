# defi-app

## Prerequisites

ganache-cli for ethereum testing env and truffle for compiling smart contracts
```
$ npm i -g truffle
$ npm i -g ganache-cli
```

## Build

To build the contracts

```
$ truffle compile
```

## Deploy to ganache

To deploy the smart contract on ganache

```
$ truffle migrate
```

## Overview
The scripts are written from following ethereum's tutorial "Create And Deploy A Defi App" (https://ethereum.org/en/developers/tutorials/create-and-deploy-a-defi-app/#create-farmtoken-smart-contract)

There is no input from myself, everything is just a direct copy, for learning purpose.

Run `$ truffle migrate` to creates an ERC20 smart contract (called MyToken), then a Defi smart contract (ERC20 as well, called FarmToken)

The Defi smart contract provides 2 functions `withdraw` and `deposit`

Deposit transfers `MyToken` from message sender to the smart contract (need to call approve first), and mint `FarmToken` and transfer back to the message sender.

Withdraw burns `FarmToken` from message sender and transfers the `MyToken` back to the message sender.

## P.S.
The FarmToken is similar to how a liquidity pools works. Follow up questions about Defi:

1. How to issue interest? Mint new FarmTokens?
2. How does lending works? Some articles on the www says lender has to stake coins more valuable than how much they lend. Why on earth would anyone do that? 
3. The `FarmToken` created here works only for one token, and the token has to be defined at build time. How does a BTC/ETH liquidity pool smart contract looks like? My preliminary thoughts are: maps to store what coins they have stored in the liquidity pool, pool token minted as proof of ownership. On redemption the owner gets to choose what coins to redeem at market price. When someone use the pool to exchange between BTC and ETH, service charge recieved will be credited to all stakers according to their ownership. There shall also be some entities to stake their coins initially when the smart contract are deployed. If ever anything error occurs those entities may risks their stakes perhaps?

## More on defi

1. liquidity pool (https://www.youtube.com/watch?v=cizLhxSKrAc)
2. borrowing/lending (https://www.youtube.com/watch?v=WwE3lUq51gQ)
3. Yeild Farming?
