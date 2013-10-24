#####Use Case ID: UC-TS07
#####Use Case Name: Change Code System Status

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Administrator  

**Stakeholders:**              Terminology User

**Purpose:**                   The main intent of this use case is to inactivate or activate terminology content for subsequent use by the other service functions.

**Pre Condition:**             Terminology Administrator must be identified and authenticated. Code System available on terminology server.

**Post Condition:**            The code system source state is changed to the requested value.

**Frequency of Occurrence:**   low

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Change Code System Status)**

1.	Terminology Admin requests to change code system status. (Includes activation, inactivation etc)
2.	System displays the form to specify code system Id, version and its status.
3.	Terminology Admin fills the form and submits it.
4.	System validates the specified details and changes the status of specified code system

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Code System state transition not allowed.
2.	Input parameter does not match.

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
