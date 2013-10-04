#####Use Case ID: UC-OES18
#####Use Case Name: Check Home IV-Drug Interaction

**Level:**                     User Level Goal

**Primary Actors:**            Doctor/ Physician/ Clinician 

**Stakeholders:**              Order Entry User

**Purpose:**                   The main intent of this use case is to perform interaction checking during medication order process.

**Pre Condition:**             Doctor/ Physician/ Clinician must be identified and authenticated.  

**Post Condition:**            There is no Home IV-drug interaction.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Check Home IV-Drug Interaction)**

1.	Physician selects the new medication order option and selects MRNO (or any other identification criteria) from the list.
2.	System shows the relevant data including weight of the patient, allergies and history.
3.	Physician after observing the status of patient fill in prescription for home IV.
4.	Physician specifies the dosage of the home IV.
5.	System will check for invalid and missing information.
6.	System checks if the prescribed medications have some drug-drug interactions among them.
7.	System responds with no interaction.
8.	Physicians save the order
9.	System will perform following actions.
    * It will record the time stamp of the ordered medication.
    * It will set the medication status to active.
    * It will send the prescription to pharmacy and will respond with non-medication order ID.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Repeat step 1 to 7 from the main scenario.
2.	System responds with interaction among prescribed home IV with the drug list of patient.
3.	Physician prescribes some alternative home IV.
4.	The steps 5-11 in main scenario of events are then executed.

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Pharmacy):**

COCT_RM260003UV
_______________________________________________________________
**Reference CCHIT Criteria:**

FN 07.01
