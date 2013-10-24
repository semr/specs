#####Use Case ID: UC-TS41
#####Use Case Name: Create Association

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Author  

**Purpose:**                   The main intent of this use case is to create association instance.

**Pre Condition:**             Terminology Author must be identified and authenticated. 

**Post Condition:**            Association instance will be created successfully.

**Frequency of Occurrence:**   Medium

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  low
__________________________________________________________
**Main Success Scenario: (Create Association)**

1.	Terminology Author selects a create association option.
2.	System asks user to specify the following meta-data fields of the association:
    * Source code system Id
    * Target Code system Id
    * Source Concept code/Id
    * Target Concept code/Id
    * Association Type
    * Association Properties
3.	User enters the required fields.
4.	System validates the specified field and records association type successfully.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Association already exists.
2.	Invalid association properties.
3.	Target Coded concept not found.
4.	Source Coded concept not found.
5.	Unrecognized Association Type.

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


