#####Use Case ID: UC-PCS38
#####Use Case Name: Search Note

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Healthcare Provider

**Purpose:**                   The main intent of this use case is to search note by physician who finalized note or by associated diagnosis.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            Notes will be searched successfully on the basis of given criteria.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Search Note By Physician who finalized note)**

1. Physician requests to search a note by physician who finalized the notes.
2. System asks user to specify physician’s name.
3. Physician enters the physician’s name who finalized the note.
4. System displays the list of notes.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:Search Note By Associated Diagnosis**

1. Physician requests to search a note by associated diagnosis.
2. System asks user to specify the one or more associated diagnosis.
3. Physician enters the required information and click on search.
4. System displays the list of notes.  
________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 08.11, AM 08.12
