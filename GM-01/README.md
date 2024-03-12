---
GM: 1
Title: Governance Module Library
Status: Exploring
Category: Meta
Authors: 
- Frederic Johnson <frederic@advanceweb3.com>
- Jakob Hackel <jhackel@block.science>
Discussions:
- (forum?Twitter?)
- ?
Created: 2024-02-27
License: ?CC-By-4.0
---

## Abstract

A Governance Module (GM) is a formal design document. A GM is used in development of new and implementable governance modules for the Stellar community, but describes the module agnostically towards underlying ledgers. 

## Motivation: Why is this GM necessary?

GMs aim to facilitate a multi-party collaboration, and this GM intends to provide a formalized process by which the collaboration can take place. If succesfull, this process results in GMs being included in the Governance Modules Library (GML).  

## Specification

### Structure

A GM is a living document of a governance concept, from ideation to a sample implementation, which allows it to be included in the Governance Modules Library. A GM is a Markdown file, that lives in the GM repository, with pre-defined sections. GM authors must adhere to the general structure to facilitate browsing and collaborative development of new GMs. 

A GM should be stored in its specific folder, named after its number (2-digit, padded with a `0` - e.g. `GM-01`). The GM itself should be described in `README.md` as defined in this document. The GM's sample implementation should be included in `implementation.py` in that folder.   

Please see the below table for the varied sections expected in each GM's `README.md`:


Name										| Description
----										| ----
Header									| Header containing the GM's Metadata [Check]
Abstract								| A short summary of the GM 
Motivation							| What is the "why" for publishing this GM?
Problem Statement				| Describes what an acceptable solution should look like 
Potential Applications	| Potential applications for the GM 
Copyright								| The GM's copyright license 

##### Header
Each GM should have a YAML-style header section at the top to facilatate browsing 

Field 		        | Description
----		  	      | ----
`GM`			        | The GM number. for new proposals, please use "\?"
`Title`		        | Succinct title for the GM
`Status`	        | In-Desire \| In-R&D \| In-Development \| Implemented
`Category`      	| Distinguishing between the multiple kinds of GMs
`Authors`		      | List the Author's real names/pseudonyms and email addresses (e.g. John Doe <john@site.dom>)
`Discussions` 	  | A list of the places where relevant conversations took place around this GM or that GM's focus - a link to this GM's PR should always be included. 
`Created` 	    	| Date the GM was created, in IS) 8601 format (YYYY-MM-DD)
`License`		      | Abbreviated License 

#### Status
A GM always has one status label attached: `In-Desire`, `In-R&D`, `In-Development` or `Implemented`. The process by which a GM is progressed through the statuses is described in the [Flow](#flow) section. 

##### Status: In-Desire
`In-Desire` is a call for a governance module to be eventually included in the GML. It might still be in ideation phase, there might not be an implementation ready, but there is a desire to build out that module. Anyone can suggest a new module, either through the google form (maintained by the community), the discussion tab, or directly through a PR. 
To move out of `In-Desire` it needs fully described: 
1) Title, Proposer, Date
2) Brief Summary and "why" 
3) Problem Statement: Description of acceptable solution (what is [non-]allowable)
4) Potential Applications (at least one) 

##### Status: In-R&D
A GM that is `In-R&D` is a serious consideration for a Desire. Anyone can contribute, either through suggestions in the relevant discussion or through PRs. 
To move out of `In-R&D` it needs fully described: 
1) Requirements
2) List of prior implementations and links to prior research
3) Decision on acceptable solution (space) with rationale

##### Status: In-Development
A GM that is `In-Development` is being worked on actively: There is an expectation that it will be implemented with a reference implementation in the near future. 
To move out of `In-Development` it needs fully described: 
1) Specification
2) Implementation Instructions
3) Tuning Guidelines (list of tuneable params and associated understanding)
4) Description for simulations (or reference implementation, for example in python) 

##### Status: Implemented
A GM that is `Implemented` is moved into the GML. It is ready for use and further iterations by others: the public should be able to explore the GM and it should have a reference implementation available.

#### Category
A GM can have multiple categories. We define a first set of categories, but expect these to be changed and added to according to the expectations of the community that uses and maintains these GMs. 
`Meta` is a category dealing with meta processes to the GML. 
`Power` deals with GMs that provide mechanisms to attribute (voting) power. 
`Signal` deals with GMs that signal voting choice. 
`Identity` deals with GMs that govern identity and proposals. 
`Reputation` deals with GMs that assign reputation or credentials to identities.  
Categories are still being defined, and some GMs may get moved accross the categories as they evolve and get better defined with time.

#### Flow
Description of how a GM goes from `In-Desire` to `In-R&D` to `In-Development` to `Implemented`. GMs move from rough desires, expressed with a PR or the form, through a cycle of more detailed descriptions, until they have reached a level of specificity that qualifies them for inclusion in the GML.
A GM is labelled as per the current status, from `In-Desire` to `In-R&D` to `In-Development` to `Implemented`. 
This process requires a team of maintainers to the Library Contributions repository. 
The process could be a monthly, public, one-to-two hour review of the existing PR's to the repository, and a look into new PRs. 
GM'ers could be Governance specialist aiming to grow the set of existing modules, or community members interested in contributing to a richer governance landscape. 
Each status label has certain conditions needed to be fulfilled to progress to the next. These conditions are listed in: GM-01. 
Maintainers are further split into three roles, corresponding to the labels `In-Desire`, `In-R&D`, `In-Development`. These maintainers can accept PRs relevant for their status, move items out of their status (into the next, or back to the prior if needed) and open/close discussions relevant to their status. Since not all contributions will be provided through PRs, maintainers also create PRs from accepted community suggestions (such as in the discussions). 

The Flow of items through the backlogs can be seen in this diagram: ![flow_diagram](https://github.com/BlockScience/SCF-GML-Contributions/blob/main/Diagrams/Stellar%20GML%20-%20Flow.png)

##### Description of how to submit a new GM.
A new GM can be submitted either through a pull request to this repository (conforming to the template and naming convention) or through the google form (in which case a maintainer must capture and format the request, if applicable). Once submitted through a PR, maintainers will review the GM and merge or request changes. A conversation is expected to live within the pull request. Throughout the lifecycle of status labels, each GM will have a corresponding discussion where contributions can be made.  

#### Maintainers
We separate functions that need fulfilling into roles. Our intention is to onboard community participants to fulfill these roles. This allows the community to gradually extend governance possibilities as a public good, facilitating a richer governance landscape. While initially there is a strong likelihood of several roles being fulfilled by few real users, this is expected to further decentralize over time. The currently proposed maintainer roles are:
* Desire Moderator
* R&D Moderator
* Dev Moderator

Each Moderator is in charge while an item is in their respective backlog. They can decide to move the item back (effectively asking for more information to be provided) or forward (effectively deciding that the conditions of the current backlog have been fulfilled) one backlog. Ideally, a discussion in the respective category is started (by the moderator) when an item moves into a backlog, and either moved or closed when moving out of a backlog. This allows any user willing to contribute to efficiently see which GMs they can currently contribute to (with their expertise and work). Additionally, this gives two options for contributions: Either directly through PRs, or simple forum-style text-based input at the respective discussion. Moderators can then capture any text-based input into a PR to formalize the contribution. An additional option for community members to express ideas for new GMs exists through this google form (link). This form serves as an easy entry point for suggesting new GMs for community members that have less experience with github processes. Desire Moderators see these form inputs, and if conforming to the rules, can formalize them through PRs on the repo.


## Rationale
This GM is needed as a Meta-GM, to describe the general process by which other GMs might be added to the Library.

## Copyright
There is no Copyright setup for this GM yet, this is to be added/considered soon. 

