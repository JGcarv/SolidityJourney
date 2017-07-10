# SolidityJourney
Series of small contracts and implementations I'm doing with the goal of improving my solidity skills.



## Contracts

#### 1 Basic Will
That's the simplest implementation of a Will contract. It works based on a regular ping by the owner. If the owner
fails to interact with the contract for a specified amount of days, he's considered dead and his heirs can claim
all the contracts funding. It was developed in response to a issue on Open Zeppelin, but was substituted by a
more complete version.
