#####Use Case ID: UC-OES11
#####Use Case Name: Renew Dietary Order

**Level:**                     User Level Goal

**Primary Actors:**            Doctor/ Physician/ Clinician

**Stakeholders:**              Order Entry User

**Purpose:**                   The main intent of this use case is to renew dietary order.

**Pre Condition:**             Doctor/ Physician/ Clinician must be identified and authenticated.   

**Post Condition:**            Dietary order renewed successfully.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Renew Dietary Order)**

1.	Physician selects the Renew Dietary Order option.
2.	System displays the list of dietary orders.
3.	Physician selects an appropriate dietary order.
4.	System asks user to modify selected order.
5.	Physician adds one or more diet, supplement or preferences.
6.	System notifies the patient, nurse and pharmacist about the updated dietary order.

__________________________________________________________
**Alternate Flows** 

**Alt-1: Remove specified diet, supplement or preferences while updating**

1.	Repeat 1-4 Steps of main scenario.
2.	Physician removes one or more diets or supplements from specified order.
3.	System notifies the patient, nurse and pharmacist about the updated dietary order.

**Alt-2: Update specified diet, supplement or preferences while updating**

1.	Repeat 1-4 Steps of main scenario.
2.	Physician updates the specific diet’s or supplement’s quantity from specified order.
3.	System notifies the patient, nurse and pharmacist about the updated dietary order.

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Pharmacy):**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-
