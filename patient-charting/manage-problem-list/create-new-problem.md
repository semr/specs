#####Use Case ID: UC-PCS01
#####Use Case Name: Create New Problem

**Level:**                     User Level Goal

**Primary Actors:**            Doctor/ Physician/ Clinician 

**Stakeholders:**              Patient Charting User

**Purpose:**                   The main intent of this use case is the creation of new problem in the list.

**Pre Condition:**             Doctor/ Physician/ Clinician must be identified and authenticated.  

**Post Condition:**            New problem created successfully without any conflicts.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Create New Problem)**

1.	Physician selects the new problem option for the particular patient
2.	Physician will select the coded problem from the list and will specify its source and duration (e.g. chronic, acute, and self-limiting). Information recorded will be as follows:
    * Problem begin date
    * Diagnosis for the problem (if any)
    * Occurrence
    * Comments/Remarks/Note (if any)
3.	System performs following actions;
    * It will validate the information.
    * It will associate order with created problem. (if any)
4.	Physician will save the new problem.
5.	System will perform following actions:
    * It will record the date and time of the problem creation.
    * It will set problem status to active.

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Pharmacy):**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

FN 04.05, IP 04.09, AM 03.08.01, AM 03.09, FN 04.02, AM 03.05, AM 03.03, AM 03.06, AM 03.07

_______________________________________________________________
**EHR Functional Criteria:**

DC 1.4.3

