#####Use Case ID: UC-OES02
#####Use Case Name: Update Medication Order

**Level:**                     User Level Goal

**Primary Actors:**            Doctor/ Physician/ Clinician 

**Stakeholders:**              Order Entry User

**Purpose:**                   The main intent of this use case is the updating of new medication order.

**Pre Condition:**             Doctor/ Physician/ Clinician must be identified and authenticated.  

**Post Condition:**            Medication order is updated successfully without any conflicts.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Update Medication Order)**

1.	Physician will select the medication order and then selects update medication order option.
2.	System will show the list of ordered medications.
3.	Physician will select the order from list and will update the required fields of order.
4.	System will perform the following actions;
  * Validate information 
  * Investigate for any drug or allergy interactions.
5.	Physician will save the updated order.
6.	System will perform following actions
  * It will record the time stamp of ordered medication.
  * It will set medication status to active.
  * It will send order to pharmacy along with order ID.

_______________________________________________________________
**Open Issues**


_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Pharmacy):**

DORX_ST000300UV01, DORX_ST060020UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

IP 08.02, IP 10.03, IP 10.04, IP 10.08, IP 10.11, IP 10.14, IP 10.15, IP 10.26, IP 10.27, FN 07.03, FN 07.04, FN 07.06
