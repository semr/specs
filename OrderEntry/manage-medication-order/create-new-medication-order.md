#####Use Case ID: UC-OES01
#####Use Case Name: Create Medication Order

**Level:**                     User Level Goal

**Primary Actors:**            Doctor/ Physician/ Clinician 

**Stakeholders:**              Order Entry User

**Purpose:**                   The main intent of this use case is the creation of new medication order.

**Pre Condition:**             Doctor/ Physician/ Clinician must be identified and authenticated.  

**Post Condition:**            New medication order is created successfully without any conflicts.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Create Medication Order)**

1.	Physician selects the new medication order option and selects MRNO (or any other identification criteria) from the list.
2.	System shows the relevant data including weight of the patient, allergies and history.
3.	Physician specifies symptoms, signs, and investigations.
4.	System will perform the following action:  
  * It will show the list of medication,  
  * It will calculate the dosage of medication based on body mass index, age or defined medication protocols.
5.	Physician selects the medication from the specified list and specifies the frequency and route of medication.
6.	System performs following actions:  
  * validate information,  
  * Investigate for any drug or allergy interactions.
7.	Physician will save the medication order.
8.	System will perform following actions:  
  * It will record the time stamp of ordered medication,  
  * It will set medication status to active,  
  * It will send order to pharmacy along with order ID.

__________________________________________________________
**Alternate Flows** 

**Alt-1: If medication not exist in list**

1.	Physician will search medication by its name, code or brand name.
2.	System will show the list of medications.
3.	Physician will select required medication
4.	The steps 6 to 8 in main scenario of events are then executed.

**Alt-2: Verbal Order**

1.	Repeat step 1 and 2 from the main scenario.
2.	Physician prescribes medication verbally and system records it.
3.	System identifies medication keywords out of recorded order.
4.	Physician performs verification read back.
5.	The steps 6 to 8 in main scenario of events are then executed.

**Alt-3: Co-Signature Configuration**

1.	Repeat step 1 to 6 from the main scenario.
2.	Physician configures the medication order for verification from another physician.
3.	System notifies the physician who has to co-sign the order.
4.	Physician verifies and signs the medication order.
5.	System responds back to initiating physician.
6.	The step 7 and 8 in main scenario of events are then executed.

**Alt-4: Interaction Checking**

1.	Repeat step 1 to 6 from the main scenario.
2.	Physician review the system response of interaction checking and take actions as: 
  * In case any drug or allergy interaction reveals, it sort some other alternate medication and proceed with normal order flow if find no drug to drug or drug to allergy interaction, 
  * In case absence of any drug to drug or drug to allergy interaction, the physician proceeds with normal flow of medication order, 
  * System will set the medication status to active.
3.	The step 7 and 8 in main scenario of events are then executed.

_______________________________________________________________
**Open Issues**

Verbal Language Supprt
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Pharmacy):**

DORX_ST000300UV01, DORX_ST060020UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

IP 08.02, IP 10.03, IP 10.04, IP 10.08, IP 10.11, IP 10.14, IP 10.15, IP 10.26, IP 10.27, FN 07.03, FN 07.04, FN 07.06
