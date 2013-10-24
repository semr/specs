#####Use Case ID: UC-TS20
#####Use Case Name: Create Code System Supplement 

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Author  

**Purpose:**                   The main intent of this use case is to create value sets appropriately.

**Pre Condition:**             Terminology Author must be identified and authenticated. 

**Post Condition:**            Value Set will be created successfully.

**Frequency of Occurrence:**   Medium

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  low
__________________________________________________________
**Main Success Scenario: (Create Code System Supplement )**

1.	Terminology Author selects a create value set option.
2.	System asks user to specify the value set properties, Id, version, rule set (expressions such as SNOMED CT concepts that are children of the SNOMED CT concept “Diabetes Mellitus”), date lock and value override (for extensional definitions ).
3.	User enters the required fields.
4.	System validates the specified fields and records value set successfully.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Value Set already exists.
2.	Invalid Value Set properties.
3.	Unrecognized/invalid rule set. 

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


