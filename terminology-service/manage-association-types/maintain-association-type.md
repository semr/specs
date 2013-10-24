#####Use Case ID: UC-TS38
#####Use Case Name: Maintain Association Type

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Author  

**Purpose:**                   The main intent of this use case is to maintain association types which may be used to link two concepts.

**Pre Condition:**             Terminology Author must be identified and authenticated. 

**Post Condition:**            Association Type will be maintained successfully.

**Frequency of Occurrence:**   Medium

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  low
__________________________________________________________
**Main Success Scenario: (Maintain Association Type)**

1.	Terminology Author requests to association type option.
2.	System displays the list the association type available.
3.	Terminology Author selects the association type to update.
4.	System asks user to modify the specified association type fields like Id, name, properties, code system Ids and status.
5.	Terminology Author modifies the meta-data of association type and submit it 
6.	System validates the specified fields.
7.	System records association type successfully.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid state transition.
2. Invalid association type.
3. Unrecognized Code System ID.

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


