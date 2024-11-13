---
GM: GM-04
Title: "Conviction Voting Mechanism"
Status: "In-Development"
Category: "Signal"
Authors: "BlockScience <contact@block.science>"
Discussions: https://github.com/BlockScience/SCF-GML-Contributions/discussions/7
Created: "2024-09-11"
License: tbd
---

# Title
Conviction Voting Mechanism
## Abstract
Conviction Voting introduces a novel continuous decision-making mechanism that determines resource allocation based on the aggregated preferences of community members expressed over time. Unlike traditional discrete voting systems, participants can modify their preferences at any time, with their voting power ("conviction") accumulating the longer they maintain consistent support for proposals. The mechanism incorporates a mathematically rigorous trigger function that determines proposal activation thresholds based on requested resources and available funds, creating a robust framework for decentralized resource allocation that naturally resists manipulation and encourages long-term community alignment.

## Motivation
Traditional voting mechanisms in decentralized systems face several critical challenges:
1. Vulnerability to last-minute vote switching and coordination attacks
2. Lack of temporal dimensions in preference expression
3. Difficulty in maintaining consistent community engagement
4. Inefficient resource allocation due to discrete voting periods

Conviction Voting addresses these challenges by introducing time as a core dimension of the voting process. As described by Jeff Emmett: "Conviction Voting offers a novel decision making process that funds proposals based on the aggregated preference of community members, expressed continuously... This added conviction gives long standing community members with consistent preferences more influence than short term participants merely trying to influence a vote."

The mechanism provides natural resistance against sybil attacks, collusion resistance, and mitigates many of the attack vectors present in time-boxed voting mechanisms, making it a valuable addition to the Governance Module Library.

The concept of Conviction Voting is designed from mathematical first principles specifically for the allocation of funds. It was derived from the paper on ‘Social Sensor Fusion’ by Dr. Michael Zargham (https://github.com/BlockScience/conviction/blob/master/social-sensorfusion.pdf), where humans are the “social sensors” reacting to proposals in their communities, each broadcasting continuously evolving preferences that are “fused” into an aggregated social signal. The design and functionality of our Conviction Voting module draws on decades of research on multi agent coordination problems and behavioral economics, with all the mathematical rigor that BlockScience is well known for.

## Problem Statement
An acceptable solution must provide a chain-agnostic, reproducible design specification for conviction voting that allows other users to integrate the mechanism into their applications or test it under their specific contexts and conditions. The solution must include:

Essential Components:
1. Mathematical specification of the conviction accumulation function
2. Definition and implementation of the trigger function (https://github.com/1Hive/conviction-voting-cadcad/blob/master/models/v3/Trigger_Function_Explanation.ipynb)
3. Parameter tuning guidelines for:
   - Conviction decay rate (α)
   - Maximum fund allocation per proposal (β)
   - Trigger function scaling (ρ)
   - Minimum support thresholds
4. Clear interfaces for system integration
5. Behavioral analysis tools and simulation frameworks

Non-acceptable solutions would:
- Rely on discrete voting periods
- Lack conviction accumulation mechanics
- Be tied to specific blockchain implementations
- Fail to provide parameter tuning guidelines

## Potential Applications
1. Grant Distribution Systems
   - Continuous funding allocation for community projects
   - Research and development funding decisions
   - Public goods funding

2. Resource Allocation in DAOs
   - Treasury management
   - Protocol parameter adjustments

3. Community-Driven Development
   - Feature prioritization in software projects
   - Resource allocation for development tasks
   - Community proposal management

4. Public Policy Decision Making
   - Participatory budgeting
   - Community resource allocation

## R&D

### Requirements
1. Conviction Mechanism Requirements
   - Time-weighted voting power accumulation system
   - Configurable decay rate for conviction
   - Support for dynamic vote updates
   - Multiple proposal handling capability

2. Trigger Function Requirements
   - Mathematical formula for activation threshold calculation
   - Protection against large fund withdrawals
   - Dynamic adjustment based on:
     * Total available funds
     * Requested amount
     * System parameters

3. Integration Requirements
   - Chain-agnostic implementation
   - Standard interfaces for:
     * Vote submission and updates
     * Proposal management
     * State queries
   - System parameter configuration options

4. Security Requirements
   - Resistance to vote manipulation
   - Protection against last-minute changes
   - Safeguards for fund allocation

### List of prior implementations and links to prior research
1. Theoretical Foundation
   - ["Conviction Voting: A Novel Continuous Decision Making Alternative to Governance"](https://medium.com/giveth/conviction-voting-a-novel-continuous-decision-making-alternative-to-governance-aa746cfb9475) by Jeff Emmett
     * Original concept introduction
     * Mathematical framework development
     * Core mechanism design

2. Production Implementations
   - [1Hive Gardens](https://github.com/1Hive/conviction-voting-app)
     * Complete DAO implementation
     * Production-tested system
   - [Aragon Conviction Voting App](https://github.com/aragon/conviction-voting-app)
     * Integration with Aragon framework

3. Analysis & Research
   - [BlockScience Engineering Analysis](https://github.com/BlockScience/Aragon_Conviction_Voting)
     * Mathematical modeling
     * Parameter analysis
     * Simulation frameworks

### Decision on acceptable solution (space) with rationale
The solution space must encompass:

1. Core Mechanism
   - Continuous voting operation
   - Time-weighted support accumulation
   - Configurable decay rates

2. Design Philosophy
   - Platform/chain agnostic
   - Modular architecture
   - Clear interfaces
   - Configurable parameters

Rationale:
1. Continuous Operation
   - Eliminates gaming around voting periods
   - Provides natural resistance to manipulation
   - Enables dynamic community response

2. Agnostic Implementation
   - Maximizes adoption potential
   - Enables cross-platform usage
   - Supports diverse applications

3. Modular Design
   - Facilitates integration
   - Enables customization
   - Supports future extensions and testing

## Development

### Specification
1. Conviction Accumulation
   ```
   y(t) = α * y(t-1) + x(t)
   ```
   where:
   - y(t): total conviction at time t
   - α: decay factor (0 < α < 1)
   - x(t): current vote weight
   
2. Trigger Function
   ```
   y*(r) = (ρ * S) / ((1-α)(β - r/R)²)
   ```
   where:
   - ρ: trigger function parameter
   - S: total token supply
   - β: maximum share of funds
   - R: total funds available
   - r: requested funds

3. System States
   - Proposal Status: {candidate, active, completed, failed}
   - Vote Registry: {participant → proposal → weight}
   - Conviction Tracker: {proposal → current_conviction}

### Implementation Instructions
1. System Setup
   a. Initialize Parameters
      - Set decay rate (α)
      - Configure maximum fund share (β)
      - Set trigger scaling (ρ)
      
   b. State Management
      - Create proposal registry
      - Initialize vote tracking
      - Set up conviction calculation
      
   c. Interface Design
      - Vote submission API
      - Proposal management endpoints
      - Query interfaces

2. Core Logic Implementation
   a. Vote Processing
      - Handle new votes
      - Update existing votes
      - Calculate conviction changes
      
   b. Trigger Evaluation
      - Monitor conviction levels
      - Check funding conditions
      - Execute proposal activation

3. System Integration
   - Event notification system
   - State query interface
   - Parameter update mechanism

### Tuning Guidelines
1. α (Alpha) - Decay Factor
   - Range: (0,1)
   - Purpose: Controls conviction decay rate
   - Impact: Higher values = longer memory
   - Recommended starting value: 0.9
   - Tuning tips:
     * 0.99: Very long memory
     * 0.9: Moderate decay
     * 0.7: Rapid decay

2. β (Beta) - Maximum Fund Share
   - Range: (0,1)
   - Purpose: Limits single proposal allocation
   - Impact: Lower values = more conservative
   - Recommended starting value: 0.2
   - Tuning tips:
     * 0.1: Very conservative
     * 0.2: Balanced
     * 0.3: More aggressive

3. ρ (Rho) - Trigger Scaling
   - Range: (0,β²)
   - Purpose: Controls activation threshold
   - Impact: Higher values = easier activation
   - Recommended starting value: 0.01
   - Tuning tips:
     * 0.005: Conservative
     * 0.01: Balanced
     * 0.02: Aggressive

### Description for simulations
Reference implementation pseudo code:

1. System State Structure:
```
STATE = {
    funds: Total available funds,
    proposals: Map of proposal_id to proposal details,
    votes: Map of participant_id to vote allocations,
    conviction: Map of proposal_id to current conviction
}

PARAMS = {
    alpha: Decay rate,
    beta: Maximum fund share,
    rho: Trigger scaling,
    min_support: Minimum required support,
    max_proposal_size: Maximum proposal size
}
```

2. Core Functions:
```
FUNCTION update_conviction(proposal_id):
    old_conviction = get_conviction(proposal_id)
    current_votes = sum_all_votes_for_proposal(proposal_id)
    new_conviction = alpha * old_conviction + current_votes
    return new_conviction

FUNCTION check_trigger(proposal_id):
    current_conviction = get_conviction(proposal_id)
    proposal = get_proposal(proposal_id)
    IF proposal.status == "candidate":
        threshold = calculate_threshold(proposal.requested_amount)
        IF current_conviction >= threshold:
            activate_proposal(proposal_id)

FUNCTION calculate_threshold(requested_amount):
    return (rho * total_supply) / 
           ((1 - alpha) * (beta - requested_amount/total_funds)²)
```

3. System Update Process:
```
FOR EACH time_step:
    Process new votes
    Update all conviction levels
    Check trigger conditions
    Update proposal statuses
    Update system state including balances and funds
```

4. Simulation Scenarios:
   - Basic operation flow:
     * Create proposals
     * Submit votes
     * Track conviction
     * Monitor activations
   
   - Trigger Threshold Testing:
        * Vary ρ and β parameters
        * Observe activation thresholds
        * Graph results for parameter tuning
