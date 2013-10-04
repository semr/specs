#####Use Case ID: UC-PCS32
#####Use Case Name: Create Clinical Note

**Level:**                     User Level Goal

**Primary Actors:**            Physician, Nurse

**Stakeholders:**              Physician, Nurse, Healthcare Provider

**Purpose:**                   The main intent of this use case is to create a new clinical note.

**Pre Condition:**             User must be identified and authenticated.

**Post Condition:**            Note will be created successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Create Clinical Note)**

1. Physician requests to list patient encounters.
2. System displays the list of encounters with status. (such as active, discharged etc)
3. Physician selects a create note option.
4. System asks user to specify the title, notes content (either in free text or structured form),
note type(such as operative note, progress note, procedure note, referral note), note status,
patient, associated diagnosis, user signatures and vital signs (including blood pressure,heart rate, respiratory rate, weight and height)
5. Physician enters the required fields.
6. System then performs the following actions:
  * Validates the fields.
  * Records the identity of user creating note and the date and time of finalization.
  * Records the clinical note details.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Patient does not exist.

**Alt-2:Note content in structured format**

1. Repeat 1-2 steps of main scenario.
2. Physician enters the required fields and selects a template for inputting data in a structured format.
3. System displays the list of available note templates.
4. Physician selects an appropriate note template.
5. System displays the form according to the selected template and asks user to enter data into template fields.
6. Repeat 3-4 steps of main scenario.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 08.01, AM 08.02, AM 08.03, AM 08.04, AM 08.05, AM 08.09, AM 08.10, AM 08.13, AM 08.14, AM 08.16
