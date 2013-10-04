#####Use Case ID: UC-OES20
#####Use Case Name: Dispense Non-Medication Order

**Level:**                     User Level Goal

**Primary Actors:**            Doctor/ Physician/ Clinician 

**Stakeholders:**              Order Entry User

**Purpose:**                   The main intent of this use case is to dispense the order if available in the concerned department.

**Pre Condition:**             Doctor/ Physician/ Clinician must be identified and authenticated.  

**Post Condition:**            Non-medication order has been dispensed successfully.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Dispense Non-Medication Order)**

1.	User selects the check dispense medication option.
2.	System responds with the non-medication order list.
3.	User verifies the availability of ordered item and dispenses it if available.
4.	System notifies that ordered item has been dispensed to the user and responds with the dispense order ID.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Repeat step 1 to 4 from the main scenario.
2.	System responds that ordered item is not available.
3.	User notifies the un-availability of ordered item.

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

IO-IP 01.01, IO-IP 03.05
