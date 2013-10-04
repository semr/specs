#####Use Case ID: UC-TS09
#####Use Case Name: Maintain Code System Version

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Author  

**Purpose:**                   The main intent of this use case is to maintain code system in a terminology service.

**Pre Condition:**             Terminology Author must be identified and authenticated. 

**Post Condition:**            Code System will be updated successfully.

**Frequency of Occurrence:**   low

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  Low
__________________________________________________________
**Main Success Scenario: (Maintain Code System Version)**

1.	Terminology Author requests to update code system.
2.	System displays the list the code systems available.
3.	Terminology Author selects the code system to update.
4.	System asks user to modify the specified code system metadata( Id, version and description).
5.	Terminology Author modifies the meta-data of code system and submit it 
6.	System validates the specified fields and records code system successfully.
7.	The system will also notify users who registered for content update notifications.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Code System does not exist. 
2.	Code System version does not exist. 

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-
