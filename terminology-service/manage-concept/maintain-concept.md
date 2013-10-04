#####Use Case ID: UC-TS16
#####Use Case Name: Maintain Concept

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Author  

**Purpose:**                   The main intent of this use case is to maintain concept in a code system.

**Pre Condition:**             Terminology Author must be identified and authenticated.

**Post Condition:**            Concepts will be updated successfully.

**Frequency of Occurrence:**   low

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  low
__________________________________________________________
**Main Success Scenario: (Maintain Concept)**

1.	Terminology Author requests to update concept.
2.	System displays the list the concepts available in a code system.
3.	Terminology Author selects the concept to update.
4.	System asks user to modify the specified concept meta-data.
5.	Terminology Author modifies the meta-data of concept and submit it 
6.	System validates the specified fields and records concept successfully.
7.	 The system will also notify users who registered for content update notifications.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Code System does not exist. 
2.	Unrecognized Jurisdictional Domain 
3.	Invalid Concept Properties
4.	Invalid Concept Designation

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-
