---
layout: default
title: "Blockchain"
parent: Challenges
nav_order: 11
permalink: /challenges/blockchain/
---

# Blockchain Challenges

Writeups for HTB Blockchain/Smart Contract challenges.

## Challenge Index

| Challenge | Difficulty | Techniques | Key Takeaway |
|-----------|-----------|------------|--------------|
| [Survival of the Richest](survival-of-richest/) | Very Easy | Solidity, Send/Transfer | Basic Ethereum transaction |
| [Distract and Destroy](distract-destroy/) | Easy | Reentrancy, Fallback | Classic reentrancy attack |
| [Token Bank](token-bank/) | Easy | ERC20, Transfer Logic | Token contract exploitation |
| [Unknown](unknown/) | Easy | Bytecode Analysis | Reading EVM storage slots |
| [ShootingTheRange](shooting-the-range/) | Medium | Integer Overflow, SafeMath | Integer overflow in Solidity |
| [HoneyPot](honeypot/) | Medium | Hidden Functions, Proxy | Smart contract honeypot analysis |
| [DeFi Oracle](defi-oracle/) | Hard | Price Oracle Manipulation | Flash loan + oracle attack |
| [CPAMM](cpamm/) | Hard | AMM, Liquidity Pool | Automated market maker exploitation |

## Key Concepts

### Common Smart Contract Vulnerabilities
| Vulnerability | Description | Example |
|--------------|-------------|---------|
| Reentrancy | External call before state update | The DAO hack |
| Integer Overflow/Underflow | Arithmetic without SafeMath | Old ERC20 tokens |
| Access Control | Missing function modifiers | Unprotected admin functions |
| Front-running | Transaction ordering manipulation | DEX sandwich attacks |
| Oracle Manipulation | Price feed manipulation | Flash loan attacks |
| Delegatecall | Context-preserving external call | Proxy pattern bugs |
| Self-destruct | Forced ETH transfer | Balance check bypass |

### Setup
```bash
# Foundry (recommended)
curl -L https://foundry.paradigm.xyz | bash
foundryup

# Interact with contract
cast call <contract> "functionName()" --rpc-url http://challenge:8545
cast send <contract> "functionName(uint256)" 123 --rpc-url http://challenge:8545 --private-key <key>

# Deploy exploit contract
forge create src/Exploit.sol:Exploit --rpc-url http://challenge:8545 --private-key <key>
```

## Tools

| Tool | Purpose |
|------|---------|
| [Foundry](https://github.com/foundry-rs/foundry) (forge/cast) | Solidity development and interaction |
| [Hardhat](https://github.com/NomicFoundation/hardhat) | JavaScript-based development environment |
| [Remix IDE](https://remix.ethereum.org/) | Browser-based Solidity IDE |
| [Etherscan](https://etherscan.io/) | Block explorer |
| [Slither](https://github.com/crytic/slither) | Static analysis for Solidity |
| [Mythril](https://github.com/Consensys/mythril) | Symbolic execution for smart contracts |
| [Echidna](https://github.com/crytic/echidna) | Fuzzing for smart contracts |
