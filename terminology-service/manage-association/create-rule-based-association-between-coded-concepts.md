#####Use Case ID: UC-TS44
#####Use Case Name: Create Rules based Association between Coded Concepts

**Level:**                     User Level Goal

**Primary Actors:**            Terminology User  

**Purpose:**                   The main intent of this use case is to Create Rule Based Association between Coded Concepts.

**Pre Condition:**             Terminology User must be identified and authenticated. 

**Post Condition:**            Rule Based association between coded concepts will be created successfully.

**Frequency of Occurrence:**   Medium

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  low
__________________________________________________________
**Main Success Scenario: (Create Rules based Association between Coded Concepts)**

1.	Terminology User requests to create rule based association between two coded concepts option.
2.	System asks user to enter the set of descriptive logic, inference rules and source search criteria for selecting subset of a code system.
3.	Terminology User fills the required fields and submits them.
4.	System creates associations between a coded concept from the source code system and a coded concept in the target code system.

**Sub-Flow:**

1. Unrecognized / Invalid inference rules. 
2. Unrecognized / Invalid search descriptive logic. 
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
