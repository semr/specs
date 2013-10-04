#####Use Case ID: UC-PAS03
#####Use Case Name: Nullify Person Record

**Level:**                     User Level Goal

**Primary Actors:**            Medical Record Clerk (MRC)

**Stakeholders:**              Medical Record Clerk, Person, Healthcare Provider

**Purpose:**                   The main intent of this use case is to nullify person record.

**Pre Condition:**             MRC must be identified and authenticated. 

**Post Condition:**            Person record nullified successfully.

**Frequency of Occurrence:**   High(Per Minute)
__________________________________________________________
**Main Success Scenario: (Nullify Person Record)**

1. MRC requests system to nullify a person record.
2. System displays a list of person records.
3. MRC specifies the person record “enter in error”.
4. System nullifies the person record.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be added.
2. Specified parent does not exist.
3. Invalid relationship.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST101303UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A




