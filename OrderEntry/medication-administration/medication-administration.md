#####Use Case ID: UC-OES08
#####Use Case Name: Medication Administration

**Level:**                     User Level Goal

**Primary Actors:**            Nurse / Patient Agent

**Stakeholders:**              Order Entry User

**Purpose:**                   The main intent of this use case is to administer ordered medication.

**Pre Condition:**             Nurse/Patient Agent must be identified and authenticated. 

**Post Condition:**            Ordered medication has been administered successfully.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Medication Administration)**

1.	Nurse/Patient Agent selects the medication administration option.
2.	System responds with the dispensed medication list.
3.	Nurse/Patient Agent selects the MRNO of the patient.
4.	System responds with medication administration details as discrete data, including : 
    * the medication name, strength and dose
    * date and time of administration
    * route and site
    * user name and credentials 
5.  Nurse/Patient Agent provides the medication to the patient and updates the status of medication.
6. 	System notifies the ordering physician.

__________________________________________________________
**Alternate Flows** 

**Alt-1**

1.	Repeat step 1 to 4 from the main scenario.
2.	Nurse/Patient Agent provides the medication to the patient and adds comment to the administered medication.
3.	 Nurse/Patient Agent updates the status of medication.
4.	System notifies the ordering physician.

_______________________________________________________________
**Open Issues**


_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Pharmacy):**

DORX_ST000300UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

IP 14.02, IP 14.01, IP 14.03, IP 14.03, IP 14.13
