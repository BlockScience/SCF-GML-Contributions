---
GM: GM-02
Title: Vote Checkpoints
Status: In-Desire
Category: `Power`  
Authors: mootz12
Discussions: tbd
Created: 2024-04-11
License: CC-By-4.0
---

# Title
Vote Checkpoints

## Abstract
Voting Checkpoints provide a historical record of voting power for governance members.

## Motivation
Governance proposal based voting systems commonly some form of "liquid" voting power. That is, voting power can be bought via tokens, transferred to others via tokens or delegation, or moved by some other means.

This opens up the door for proposal votes to be double counted. That is, I can vote on my account, move my voting power to another address, and vote again during the voting window. This can be prevented by the governance system checking some historical time (often the start of the voting window, or 1 block before) for all votes cast.

## Problem Statement
An acceptable solution is one that safely tracks voting checkpoints such that a governance system can use it to grab historical voting power for use in voting.

We designed a solution that is functional, but likely could be significantly improved: https://github.com/script3/soroban-governor/blob/main/contracts/votes/src/checkpoints.rs

An example solution on EVM: https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/structs/Checkpoints.sol

Soroban introduces a couple difficulties when implementing a solution for this. Namely, ledger entry size limits and ledger entry read limits. If storing vote history in one ledger entry, the first becomes an issue, and if splitting checkpoints it individual solutions.

If another user can create checkpoints for someone, they might be able to force their vote checkpoint history to exceed limits. 

## Potential Applications
Any token based DAO
Any DAO with the ability to delegate voting powers

## Copyright
CC-By-4.0 	
