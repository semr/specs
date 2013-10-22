#####Use Case ID: UC-PCS02
#####Use Case Name: Update Problem

**Level:**                     User Level Goal

**Primary Actors:**            Doctor/ Physician/ Clinician 

**Stakeholders:**              Patient Charting User

**Purpose:**                   The main intent of this use case is to update problem in the list.

**Pre Condition:**             Doctor/ Physician/ Clinician must be identified and authenticated.  

**Post Condition:**            Problem updated successfully without any conflicts.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Update Problem)**

1.	Physician selects the update problem option.
2.	System shows the list of the problems of particular patient.
3.	Physician will select the problem from the list.
4.	System will display the history of changes made to a specific problem / diagnosis, including clinician, date, and time.
5.	Physician will modify the required information.
6.	System will perform following actions:
    * It will validate the information.
b.	It will associate order with created problem.
7.	Physician will save the updated problem.
8.	System will perform following actions:
    * It will record the date and time of the problem creation.
    * It will set problem status to active.

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Problem List):**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

FN 04.05, IP 04.09, IP 04.02, FN 04.02, AM 03.05, AM 03.03, AM 03.06, AM 03.07

_______________________________________________________________
**EHR Functional Criteria:**

DC 1.4.3
