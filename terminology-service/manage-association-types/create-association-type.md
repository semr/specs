#####Use Case ID: UC-TS37
#####Use Case Name: Create Association Type

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Author  

**Purpose:**                   The main intent of this use case is to create association types which may be used to link two concepts.

**Pre Condition:**             Terminology Author must be identified and authenticated. 

**Post Condition:**            Association Type will be created successfully.

**Frequency of Occurrence:**   High

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  low
__________________________________________________________
**Main Success Scenario: (Create Association Type)**

1.	Terminology Author selects a create association type option.
2.	System asks user to specify the Id, name, properties and code system Ids (for restricting association type to specific code systems) of the association type.
3.	User enters the required fields.
4.	System validates the specified fields.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Association type already exists.
2.	Invalid association type  properties
3.	Unrecognized Code System ID

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-
