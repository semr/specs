#####Use Case ID: UC-PCS34
#####Use Case Name: Modify Finalized Note

**Level:**                     User Level Goal

**Primary Actors:**            Physician, Nurse

**Stakeholders:**              Physician, Nurse, Healthcare Provider

**Purpose:**                   The main intent of this use case is to addend and/or correct finalized note.

**Pre Condition:**             User must be identified and authenticated.

**Post Condition:**            Finalized note will be modified successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Modify Finalized Note)**

1. Physician requests to modify finalized note.
2. System displays the list of available patients.
3. Physician selects an appropriate patient.
4. System displays the whole patient chart with different tabs such as problem list, vital signs and clinical notes.
5. Physician selects clinical note tab.
6. System displays the finalized note full details and asks user to modify the required fields.
7. Physician modifies the required fields and submits.
8. System asks for the reason to modify finalized note.
9. Physician enters the clarification and submits it.
10. System then performs the following actions:
  * Validates the modified fields.
  * Records the modified note.
  * Records the user identity and the date and the time of modifying finalized note.
  
________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 08.07
