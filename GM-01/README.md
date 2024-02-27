---
GM: 1
Title: Governance Module Library
Status: Exploring
Category: Meta
Authors: 
- Frederic Johnson <frederic@advanceweb3.com>
- Jakob Hakel <jhackel@block.science>
Implementors: Block.Science
Discussions:
- (forum?Twitter?)
- ?
Created: 2024-02-27
License: ?CC-By-4.0
---

## Abstract

A Governance Module (GM) is a formal design document for the greater Crypto community. A GM is meant to be used to assist in Governance for Crypto communities, possibly in conjunction with other modules. 

## Motivation: Why is this GM necessary?

GMs aim to facilitate a multi-party collaboration, and this GM intends to provide a formalized process by which the collaboration can take place. 

## Specification

### Structure

A GM is a living document of a governance concept, from inception and basis towards a sample implementation of the module in Python. A GM is a Mardown file, that lives in the GM repository, with pre-defined sections. GM authors must adhere to the general structure to facilitate browsing and adding new GMs. 

A GM should be stored in its specific folder, named after its number (2-digit, padded with a `0` - e.g. `GM-01`). The GM itself should be described in `README.md` as defined in this document. The GM's sample implementation should be included in `implementation.py` in that folder.   

Please see the below table for the varied sections expected in each GM's `README.md`:

Name										| Description
----										| ----
Header									| Header containing the GM's Metadata 
Abstract								| A short description of the GM itself
Motivation							| What is the basis behind publishing this GM?
Specification						| Technical details about the GM 
Rationale								| Explains design choices in the Specification
Implementation Path			| The current path towards an active module
Copyright								| The GM's copyright license

##### Header
Each GM should have a YAML-style header section at the top to facilatate browsing 

Field 		        | Description
----		  	      | ----
`GM`			        | The GM number. for new proposals, please use "\?"
`Title`		        | Succinct title for the GM
`Status`	        | Desire \| In R&D \| In-Development \| Implemented
`Category`      	| Distinguishing between the multiple kinds of GMs
`Authors`		      | List the Author's real names and email addresses (e.g. John Doe <john@site.dom>)
`Implementors`  	| Who is currently working on the GM, and which part (e.g. Implementation vs. Research)
`Discussions` 	  | A list of the places where relevant conversations took place around this GM or that GM's focus - a link to this GM's PR should always be included. 
`Created` 	    	| Date the GM was created, in IS) 8601 format (YYYY-MM-DD)
`License`		      | Abbreviated License 

#### Status
A GM can have four statuses: `Desire`, `In R&D`, `In-Development` or `Implemented`. The process by which a GM is progressed through the statuses is described in the [Flow](#flow) section. 

##### Status: Desire
Add Description for the Desire Status. 
A Desire is a call for a governance module supporting an existing concept. It might not be fully fleshed out, there might not be an implementation ready, but there is a desire to build out that module.

##### Status: In R&D
Add Description for the `In R&D` Status. 
A GM that is Exploring is a serious consideration for a Desire. It could involve academics, R&D, and should focus on the feasibility of the GM. 

##### Status: In-Development
Add Description for the In-Development Status. 
A GM that is In-Development is being worked on actively: There is an expectation that it will be implemented with a reference implementation in the near future. 

##### Status: Implemented
Add Description for the Implemented Status. 
A GM that is Implemented is a GM ready to use by others: the public should be able to explore the GM and it should have a reference implementation available.

#### Category
A GM can have multiple categories. `Meta` is a category dealing with meta processes to the GML. `Power` deals with GMs that adjust (voting) power. `Signal` deals with surfacing or adjusting. `Identity` deals with Identity and proposals. `History` looks at adjustments from Priors. Categories are still being defined, and some GMs may get moved accross the categories as they evolve and get better defined with time.

##### Abstract
Add description of Abstract section here. Abstract is a short summary of the GM. This helps for clarity. 

##### Motivation 
Add description of Motivation here. The Motivation is the why of the GM, as in why it is being proposed, as a request or other. 

##### Specification
Add description of Specification here. The Specification is intent as the heart of the GM, where the flows for that GM are explained, and how it currently functions.

##### Rationale 
Add description of Rationale here. The Rationale for the GM is the reason why it is being proposed, as well as relevant Specification choices that were made.

##### Specification 
Add description of Specification here. The Specification should describe the GM in details possibly including links to ongoing research groups or documentation.

##### Implementation Path
Add description of the Implementation Path here. The Implementation Path should be focusing on the path towards a workable module with a Python implementation available. For an implemented GM, Implementation Path should be replaced by "Implementation notes", describing how to run the implementation.

##### Copyright
Add Description of the Copyright here

#### Flow
(NEEDED) Description of how a GM goes from Request to Exploring to In-Development and towards Implemented. Consider other statuses to add (ex: Closed). This process is assumed to require a team of GM'ers, or curators to the Library repository. The process could be a monthly, public two hour review of the existing PR's to the repository, and a look into new PRs. GM'ers could be Governance specialist aiming to grow the set of existing modules. 
(NEEDED) Description of how to submit a new GM.
i.e. GM must be submitted as a pull request to this repository in the specified format, with the pull request named after the GM's title. Once submitted, GM'ers will review the GM and merge or request changes. A conversation is expected to live within the pull request. Someone might propose a GM for a kind of module, implemented or being researched.   

## Rationale
This GM is needed as a Meta-GM, to enable the general process by which other GMs might be added to the Library.

## Implementation Path
This Meta-GM is currently being `Explored` but can be considered as `Implemented`. External contributors to the Repo can validate the process described in this GM. 

## Copyright
There is no Copyright setup for this GM yet, this is to be added/considered soon. 

