#####Use Case ID: UC-TS17
#####Use Case Name: Update Concept Status

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Author  

**Purpose:**                   The main intent of this use case is to maintain concept status.

**Pre Condition:**             Terminology Author must be identified and authenticated.

**Post Condition:**            Concept’s status will be updated successfully.

**Frequency of Occurrence:**   low

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  low
__________________________________________________________
**Main Success Scenario: (Update Concept Status)**

1.	Terminology Author requests to update concept status.
2.	System displays the list the concepts in a code system.
3.	User selects the concept to status update.
4.	System asks user to modify the specified concept status.
5.	User modifies the concept version status.
6.	 System validates the specified fields and records concept successfully.
7.	 The system will also notify users who registered for content update notifications.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Code System Identifier does not exist.
2.	Invalid state change.

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

