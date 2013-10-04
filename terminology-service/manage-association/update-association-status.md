#####Use Case ID: UC-TS42
#####Use Case Name: Update Association Status

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Author  

**Purpose:**                   The main intent of this use case is to update the status of associations

**Pre Condition:**             Terminology Author must be identified and authenticated. 

**Post Condition:**            Association instances status will be updated successfully.

**Frequency of Occurrence:**   Medium

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  low
__________________________________________________________
**Main Success Scenario: (Update Association Status)**

1.	Terminology Author requests to update association status.
2.	System displays the list the associations in a code system.
3.	User selects the association to status update.
4.	System asks user to modify the specified association status.
5.	User modifies the association version status. 
6.	The steps 4 in main scenario of events are then executed.
7.	The system will also notify users who registered for content update notifications. 

**Sub-Flow:**

1. Association Identifier does not exist.
2. Invalid state change.

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-
