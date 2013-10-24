#####Use Case ID: UC-TS43
#####Use Case Name: Create Lexical Association between Coded Concepts

**Level:**                     User Level Goal

**Primary Actors:**            Terminology User  

**Purpose:**                   The main intent of this use case is to Create Lexical Association between Coded Concepts.

**Pre Condition:**             Terminology User must be identified and authenticated. 

**Post Condition:**            Lexical association between coded concepts will be created successfully.

**Frequency of Occurrence:**   Medium

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  low
__________________________________________________________
**Main Success Scenario: (Create Lexical Association between Coded Concepts)**

1.	Terminology User requests to create lexical association option.
2.	System asks user to enter the set of lexical rules (matching algorithm) and source search criteria for selecting subset of a code system.
3.	Terminology User fills the required fields and submits them.
4.	System creates associations between a coded concept from the source code system and a coded concept in the target code system.

**Sub-Flow:**

1. Unrecognized / Invalid algorithm. 
2. Unrecognized / Invalid search criteria 
3. No Associations matched the input algorithm.
4. Target Code System does not exist.
5. Source Code System does not exist. 

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-

_______________________________________________________________
**Reference Hl7 RMIM (Domain: CTS):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

-NA-

_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

-NA-
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

-NA-
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

-NA-


