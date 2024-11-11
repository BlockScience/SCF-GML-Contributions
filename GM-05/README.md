---
GM: GM-05
Title: "Osmotic Governance"
Status: "In-Development"
Category: "Signal"
Authors: "BlockScience <contact@block.science>"
Discussions: "https://github.com/BlockScience/SCF-GML-Contributions/tree/main/GM-XX"
Created: "2024-10-11"
License: tbd
---

# Title
Osmotic Governance

## Desire 

### Abstract
Osmotic Governance introduces a novel continuous resource allocation mechanism where funding flows to proposals proportionally based on their accumulated support, without discrete acceptance thresholds. Unlike traditional voting systems or threshold-based systems like Conviction Voting, Osmotic Governance enables real-time fund distribution that dynamically adjusts based on the community's expressed preferences. The mechanism creates a fluid, responsive system that naturally balances resource allocation across multiple initiatives while maintaining community alignment. This mechanism could allow for projects to receive sustainance grants in small increments, allowing for a more dynamic and responsive funding system.

### Motivation
Current governance systems, including continuous voting mechanisms like Conviction Voting, still rely on discrete funding decisions based on threshold crossing. This creates several challenges:
- Binary outcomes (funded/not funded) don't reflect nuanced community preferences
- Resources can be inefficiently allocated when multiple valuable proposals compete
- Threshold-based systems can create artificial scarcity and competition
- Communities struggle to maintain dynamic resource allocation that reflects changing priorities

Osmotic Governance addresses these challenges by implementing a continuous funding flow mechanism that:
- Enables proportional resource allocation based on community support
- Allows for dynamic reallocation as preferences shift
- Creates natural balance between competing proposals
- Reduces the impact of threshold gaming and coordination attacks

### Problem Statement
An acceptable solution must provide a mechanism that enables:
1. Continuous fund distribution without discrete thresholds
2. Dynamic reallocation based on changing support
3. Efficient multi-proposal funding
4. Protection against manipulation and depletion
5. Clear parameter tuning guidelines

Non-acceptable solutions would:
- Rely on threshold-based activation
- Require discrete funding decisions
- Fail to handle multiple simultaneous proposals efficiently
- Lack protection against rapid support changes
- Be tied to specific blockchain implementations

### Potential Applications
1. Continuous Public Goods Funding
   - Open source development funding
   - Community project support
   - Research and development allocation

2. Dynamic Resource Management
   - DAO treasury management
   - Community pool distribution
   - Protocol reward systems

3. Adaptive Grant Programs
   - Continuous hackathon funding
   - Educational program support

### Copyright
tbd


## R&D

### Requirements
1. Modified Conviction Mechanism
   - Time-weighted support accumulation (similar to Conviction Voting GM-04)
   - Configurable decay rate for support
   - Continuous funding rate based on accumulated support
   - No threshold requirements for fund distribution
   - Multi-proposal support distribution

2. Distribution Function Requirements
   - Convert accumulated support directly into funding rates
   - Dynamic adjustment based on:
     * Total available funds
     * Relative support levels between proposals
     * System parameters
   - Smooth, continuous fund distribution
   - Support for minimum and maximum flow rates

3. Integration Requirements
   - Chain-agnostic implementation
   - Standard interfaces extending Conviction Voting:
     * Support expression and updates
     * Flow rate monitoring
     * Fund distribution tracking
   - Parameter configuration options

### Decision on acceptable solution (space) with rationale
The solution space must encompass:

1. Core Mechanism
   - Conviction Voting-style support accumulation
   - Direct conversion of conviction to funding rate
   - No threshold requirements
   - Continuous distribution model

2. Mathematical Framework
   - Support accumulation formula from Conviction Voting:
     ```
     y(t) = α * y(t-1) + x(t)
     ```
   - New funding rate formula:
     ```
     rate(t) = f(y(t), total_funds, competing_proposals)
     ```
   - Stability constraints
   - Bounded allocation guarantees

3. Design Requirements
   - Platform agnostic implementation
   - Extension of Conviction Voting interfaces
   - Clear upgrade path from threshold-based systems

Rationale:

1. Conviction Voting Base
   - Proven support accumulation mechanism
   - Well-understood security properties
   - Existing implementations to build upon
   - Community familiarity

2. Threshold Removal
   - Enables truly continuous funding
   - Allows for immediate support to community preferences
   - Gives proposals continous opportunity for funding which might be crucial for early-stage projects

3. Practical Considerations
   - Builds on existing knowledge
   - Easier adoption path
   - Familiar parameter space

Non-acceptable solutions would:
- Implement any form of threshold mechanism
- Deviate from Conviction Voting's support accumulation
- Require discrete funding decisions
- Add unnecessary complexity beyond threshold removal
- Break compatibility with existing Conviction Voting tools