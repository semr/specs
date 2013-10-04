#####Use Case ID: UC-PCS33
#####Use Case Name: Finalize Note

**Level:**                     User Level Goal

**Primary Actors:**            Physician, Nurse

**Stakeholders:**              Physician, Nurse, Healthcare Provider

**Purpose:**                   The main intent of this use case is to finalize the clinical note.

**Pre Condition:**             User must be identified and authenticated.

**Post Condition:**            Note will be finalized successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Finalize Note)**

1. Physician selects finalize clinical note.
2. System displays the list of available patients.
3. Physician selects an appropriate patient.
4. System displays the whole patient chart with different tabs such as problem list, vital signs and clinical notes.
5. Physician selects clinical note tab.
6. System displays the note full details and asks user to modify the required fields.
7. Physician modifies the required fields and change status of note from “in progress” to “finalize”.
8. System then performs the following actions:
  * Validates the modified fields.
  * Records the modified note.
  * Records the user identity and the date and the time of note finalization.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Note already finalized.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 08.04, AM 08.05
