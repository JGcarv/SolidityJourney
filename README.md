# SolidityJourney
Series of notes and implementations with the journey of mastering solidity.



## Contracts

#### 1 Basic Will
That's the simplest implementation of a Will contract. It works based on a regular ping by the owner. If the owner
fails to interact with the contract for a specified amount of days, he's considered dead and his heirs can claim
all the contracts funding. It was developed in response to a issue on Open Zeppelin, but was substituted by a
more complete version.

#### 2 Dutch Auction Crowdsale
A contract that implements a dutch auction as an ICO model. It's a bit uncommon, but I find it particularly
interesting, because it really reflects market interest. It matches specially well with a mintable token,
as only the bought amount of tokens will be minted, avoiding a possibly big devaluation of the price right
after the sale.

#### 3 Underhanded solidity Contest Entry
Promoted by Nick Johnson, the first contest aims to explore exploits in solidity, focusing on ICO schemes.
I explored  a way to artificially inflate token price on a Dutch Auction ICO. I got 3rd place!


## Notes on Solidity

### Using `delegatecall`
It's a useful way of executing other contract's code, as if it's your own contract. That pattern is used
to make a project more modular, separating functionalities in many contracts but also keeping a consistent
address.   

### The danger of `this.balance`
Here's a interesting edge case. You can create a new contract with it's balance being greater than 0. How?
Turns out that contract addresses are deterministic, which mean that one can find out a contract address
before it's deployed. Another interesting feature is that anyone can forcibly send ether to another contract,
even without triggering the fallback function. I explored this caveat in my entry for USCC.
