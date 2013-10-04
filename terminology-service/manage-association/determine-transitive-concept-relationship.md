#####Use Case ID: UC-TS46
#####Use Case Name: Determine Transitive Concept Relationship

**Level:**                     User Level Goal

**Primary Actors:**            Terminology User  

**Purpose:**                   The main intent of this use case is to Create Rule Based Association between Coded Concepts.

**Pre Condition:**             Terminology User must be identified and authenticated. 

**Post Condition:**            Rule Based association between coded concepts will be created successfully.

**Frequency of Occurrence:**   Medium

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  Low
__________________________________________________________
**Main Success Scenario: (Determine Transitive Concept Relationship)**

1.	Terminology User requests to determine transitive concept relationship option.
2.	System asks user to enter the parent node, child node Id and concept association type.
3.	Terminology User enters the required fields and submits them.
4.	System validates the input fields.
5.	System returns an edge graph necessary to traverse from parent node to child node using the given Concept association type.

**Sub-Flow:**

1. Invalid values in fields

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-
