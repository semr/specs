#####Use Case ID: UC-PAS010
#####Use Case Name: Nullify Patient Record

**Level:**                     User Level Goal

**Primary Actors:**            Medical Record Clerk (MRC)

**Stakeholders:**              Medical Record Clerk, Physician, Patient , Healthcare Providers

**Purpose:**                   The main intent of this use case is to nullify patient record.

**Pre Condition:**             MRC must be identified and authenticated. 

**Post Condition:**            Patient record will be nullified successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Nullify Patient Record)**

1. MRC requests system to nullify a patient record.
2. System displays a list of patient records.
3. MRC specifies the person record “entered in error”.
4. System nullifies the patient record. 

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be added.
2. Specified parent does not exist.
3. Invalid relationship.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST201303UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
