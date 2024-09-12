---
GM: GM-03
Title: Trustful - Verifiable Reputation Aggregator
Status: In-R&D
Category: `Reputation`  
Authors: Leonardo Vieira, Daniela Zschaber
Discussions: tbd
Created: 2024-09-11
License: tbd
---

# Title
Trustful - Verifiable Reputation Aggregator

## Abstract
A reputation system that values effort over economic power, fostering collaboration and neutral credibility.

## Motivation
The current approach of relying on token ownership for voting and participation has led to decreased community engagement among members who are passionate about their communities. Additionally, individuals are less motivated to join new communities, fearing the time and effort it would take to establish their reputation from the ground up.

Introducing Trustful, a verifiable and interoperable reputation layer that addresses these challenges by establishing a framework where your contributions are acknowledged across different organizations and ecosystems. This system empowers you to influence the community you are dedicated to, not based on economic power or tokens you possess but on the level of your commitment and efforts towards the community's future (Valocracy).

## Problem Statement
1. Impactless Resource Allocation
* Unfair resource allocation: In many current ecosystems, resource allocation is often based on economic power, influence, or superficial metrics rather than actual contribution or commitment to the community. This can result in funding being directed towards projects that are either not completed or do not deliver meaningful value. Furthermore, it creates an environment where those with more financial resources have disproportionate control over which projects receive support, leading to potential bias and inefficiencies.
* Reputation and participation-based allocation: By shifting resource allocation towards a system that values verifiable reputation and active participation, the process becomes inherently more equitable and aligned with the true interests of the community. When resources are allocated based on a participant's proven track record and level of engagement, it not only ensures that funding goes to those who are more likely to deliver results, but also encourages more members to actively contribute to the ecosystem.
* Positive impact on the ecosystem: This approach fosters a virtuous cycle where increased participation and contributions lead to enhanced reputations, which in turn attract more resources and support. As a result, the overall quality and success rate of funded projects improve, driving further innovation and growth within the ecosystem. By promoting a more fair and transparent allocation of resources, the community benefits from a more diverse range of voices and ideas, reducing the concentration of power and enhancing collective decision-making.
* Encouraging sustained engagement: When participants know that their efforts and contributions are recognized and rewarded, they are more likely to remain engaged and committed to the community's long-term success. This not only strengthens the community but also ensures a steady pipeline of innovative projects and solutions. The reputation-based allocation model thus feeds back into itself, continuously building and reinforcing a culture of active participation, collaboration, and mutual support within the ecosystem.

2. Lack of a verifiable track record of past contributions and Valocracy
* Absence of a history: Make your story count and enhance your on-chain reputation with all past collaborations.
* Arbitrariness in role selection decisions: Assign roles to those with more knowledge and building experience in specific areas, basing decisions on verifiable reputation – contribution-based role assignment.

3. Coordination, Interoperability, and Modularity
* Lack of interoperability between ecosystems: Portability matters, so take your reputation forward, participate in other communities, and show them what you've built in one ecosystem.
* Plutocracy and voting turnout: Value valocracy, making your participation and contributions valuable and important; currently, governance tokens lead this front and are still based on monetary power and not always on contribution.
* Bribery: When we have a non-transferable reputation based on our verifiable contributions, bribery becomes harder.
Absence of an equitable community currency: A community coin can be created by taking reputation into account; economic value may be considered, but reputation can be part of the governance equation.
* Voting system based only on token holdings: Reputational systems, combined with delegate and time-stamp systems, can lead to a better equitative model for voting systems in digital organizations by weighting the voting power based on who is fit by reputation in the ecosystem, not only the amount of holdings.

4. High-quality community engagement and recognition
* Lack of engagement: The ease of tracking progress stimulates increased engagement and optimal decision-making based on a unit with high reputation in a specific area.

## Potential Applications
1. Reputation as Data for Decision-Making Reputation data can be integrated into decision-making processes, such as grant applications, to improve the impact and fairness of resource allocation. For example, consider the user flow within the Stellar Community Fund. Applicants can include their wallets and the wallets of team members involved in the project. These wallets would reflect the cumulative reputation within the Stellar ecosystem, showcasing the quality, participation, and expertise of the team members. This reputation data would help ensure that resource allocation is more aligned with the potential impact and growth of the ecosystem.

Similarly, voters in the grant process can have reputation badges. Community voters with higher reputation and active participation in the ecosystem can better recognize the ecosystem's needs and thus wield more voting power when making decisions.

This approach not only ensures a fairer resource allocation but also generates additional benefits:
* Incentives for active and high-quality participation in the Stellar ecosystem: By tying reputation to both applicants and voters, there is a strong motivation for all members to contribute meaningfully to the ecosystem.
* Enhanced features for the community funding dashboard: Encouraging team members to create accounts, be properly included in projects, and interact within the Stellar ecosystem will contribute to the collective reputation of the team, fostering a collaborative environment focused on ecosystem growth.

2. Reputation as a Voting Multiplier In governance systems that operate on a "1 token 1 vote", users with more tokens naturally have more voting power. However, in a reputation-based system, users with less capital can still exert significant influence through their accumulated reputation.

For example, a user with 400 tokens would typically have more voting power than someone with fewer tokens. However, if another user with only 200 tokens has earned multiple reputation badges, the modular system could allow the DAO to define a reputation multiplier. For instance, if the DAO sets a multiplier of 5% for users with more than 50 reputation points, the voting power would increase accordingly.

Calculation Example:
* User A: 400 tokens, no reputation badges.
* User B: 200 tokens, with reputation badges that qualify for a 5% multiplier.
For User B, the reputation multiplier would add 10 tokens worth of voting power (5% of 200 tokens), resulting in a total of 210 tokens in voting power.

In this scenario, while User A has a higher base token count, User B's accumulated reputation allows them to close the gap, ensuring that their contributions and commitment to the ecosystem are recognized and rewarded in the governance process. This approach promotes a more equitable and inclusive decision-making process within the DAO.

## Copyright
tbd

## R&D
### Requirements
Add Requirements here. Requirements are concrete needs and constraints that the proposed GM needs to fulfill to be considered succesful. 

### List of prior implementations and links to prior research
This reputation aggregator also has an EVM version that aims to be cross-organization, providing seamless interoperability across various chains and different DAOs or/and organizations.

The Trustful contract created initially for ZuVillage Georgia allows users to receive and manage attestations (using EAS), contributing to a verifiable reputation system. The contract integrates with various on-chain and off-chain data sources to ensure accurate and trustworthy reputation metrics.

**Key Features**
* Reputation Aggregation: Collects and aggregates reputation data from multiple sources.
* Attestations Management: Enables users to receive, store, and manage attestations.
* Interoperability: Designed to work seamlessly across different platforms and communities.
* Security: Ensures that all reputation data is verifiable and tamper-proof.

### Decision on acceptable solution (space) with rationale
Describe the what an acceptable (or non-acceptable) solution looks like and why this decision was made. Closely related to requirements, this section argues for a particular solution space. 


## Development
### Specification
Provide a specification for the GM. The specification describes the GM, how it functions and how it fulfills its objectives and requirements. 

### Implementation Instructions
Describe the steps needed to implement the GM, such as decisions that need to be made (parameters, parts, etc) or any related interfaces or data sources the GM might need. 

### Tuning Guidelines (list of tuneable params and associated understanding)
Describe the various parameters that can be set for the GM and describe what they do. 

### Description for simulations (or reference implementation, for example in python)
Describe how the GM can be validated, such as through a provided reference implementation, a toy model, or similar. 