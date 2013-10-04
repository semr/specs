#####Use Case ID: UC-OES07
#####Use Case Name: Dispense Medication

**Level:**                     User Level Goal

**Primary Actors:**            Doctor/ Physician/ Clinician 

**Stakeholders:**              Order Entry User

**Purpose:**                   The main intent of this use case is to dispense the medication if available in pharmacy.

**Pre Condition:**             Doctor/ Physician/ Clinician must be identified and authenticated.  

**Post Condition:**            Ordered medication has been dispensed successfully.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Dispense Medication-Ambulatory)**

1.	Pharmacist selects the dispense medication option.
2.	System responds with the ordered medication list.
3.	Pharmacist selects the MRNO specified by the patient.
4.	System Responds with the full prescription of the patient.
5.	Pharmacist verifies the medication availability and dispenses the medication to patient.
6.

__________________________________________________________
**Alternate Flows** 

**Alt-1: In-Patient**

1.	Repeat step 1 to 5 from the main scenario.
2.	Pharmacist dispenses medication to nurse/ patient agent.
3.	System will notify the ordering physician, will attach time stamp and quantity to the order and will respond with dispense order ID.

**Alt-2: Medication Unavailability**

1.	Repeat step 1 to 4 from the main scenario.
2.	System responds that medication is not available in pharmacy.
3.	Pharmacist notifies the un-availability of medication and asks for the alternative medication.
4.	Physician after receiving notification prescribe new medication, while renewing the old medication order.
5.	System sends renewed prescription to pharmacist.
6.	The steps 5-7 in main scenario of events are then executed.


_______________________________________________________________
**Open Issues**


_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Pharmacy):**

DORX_ST000020UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

IO-IP 01.01, IO-IP 03.05
