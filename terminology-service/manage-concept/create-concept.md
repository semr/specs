#####Use Case ID: UC-TS15
#####Use Case Name: Create Concept

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Author  

**Purpose:**                   The main intent of this use case is to create concept in a code system.

**Pre Condition:**             Terminology Author must be identified and authenticated.

**Post Condition:**            Concepts will be created and made available for access via Terminology Service

**Frequency of Occurrence:**   low

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  low
__________________________________________________________
**Main Success Scenario: (Create Concept)**

1.	Terminology Author selects a create concept option.
2.	System asks user to specify the following fields of meta-data of a concept:
    *	Code System ID
    * Code System Version
    * Concept Code
    * Concept Id or Concept Code 
    * Concept Properties
    * Concept Relationships
    * Concept Designations
3.	User enters the required fields.
4.	System validates the specified fields and records concept successfully.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Code System does not exist.
2.	Code System version does not exist.
3.	Concept already exists. 

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


