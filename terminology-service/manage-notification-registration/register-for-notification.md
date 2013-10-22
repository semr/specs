#####Use Case ID: UC-TS47
#####Use Case Name: Register for Notification

**Level:**                     User Level Goal

**Primary Actors:**            Terminology User  

**Purpose:**                   The main intent of this use case is to register a user for the notification.

**Pre Condition:**             Terminology User must be identified and authenticated.

**Post Condition:**            User will be registered successfully.

**Frequency of Occurrence:**   low

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  low
__________________________________________________________
**Main Success Scenario: (Register for Notification)**

1.	User selects a register for notification option.
2.	System asks user to specify the electronic address, notification target type (such as code system, value set, concept and association), notification target Id, notification target version and notification direction (such immediate or delayed).
3.	User enters the required fields.
4.	System validates the specified fields and records notification registration successfully.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Identified element / version do not exist.
2.	Notification Directions not recognized.

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-
