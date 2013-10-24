#####Use Case ID: UC-TS14
#####Use Case Name: Maintain Code System Supplement 

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Author  

**Purpose:**                   The main intent of this use case is to maintain code system supplement in a terminology service.

**Pre Condition:**             Terminology Administrator must be identified and authenticated. 

**Post Condition:**            Code System supplements will be maintained successfully.

**Frequency of Occurrence:**   low

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  low
__________________________________________________________
**Main Success Scenario: (Maintain Code System Supplement )**

1.	Terminology Author requests to update code system supplements.
2.	System displays the list the code system supplements available.
3.	Terminology Author selects the code system supplement to update.
4.	System asks user to modify the specified code system supplement meta-data, set of concepts and set of concept properties.
5.	Terminology Author modifies the desired fields of code system supplement and submits it. 
6.	System validates the specified fields and records code system supplement successfully.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Code System Supplement not found. 
2.	Code System version does not exist.
3.	Concept not found.
4.	Invalid Concept Properties.

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


