#####Use Case ID: UC-TS27
#####Use Case Name: Check Concept Value Set Membership

**Level:**                     User Level Goal

**Primary Actors:**            Terminology User  

**Purpose:**                   The main intent of this use case is to check that coded concept is member of a particular value set.

**Pre Condition:**             Terminology User must be identified and authenticated. 

**Post Condition:**            Concept value set membership checked successfully.

**Frequency of Occurrence:**   High

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  low
__________________________________________________________
**Main Success Scenario: (Check Concept Value Set Membership)**

1.	Terminology User selects check concept value set membership
2.	System asks user to select concept Id, code system Id, code system version, value set Id and value set version.
3.	Terminology User selects required fields and submits them.
4.	System returns ‘True’ if coded concept exists in value set otherwise returns false.

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-
