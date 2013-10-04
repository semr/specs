####Description
--------------
The Scheduling Service module will allow user to add physicians’ availability information such as availability hours in a day and working days in a week. The system will also generate the calendar according to entered availability information.

####Fully Dressed Use Case
--------------------------

#####Use Case ID: UC-SS05
#####Use Case Name: Add Physician Availability Info

**Level:**                     User Level Goal

**Primary Actors:**            Assistant

**Stakeholders:**              Assistant, Patient, Physician, Healthcare Provider

**Purpose:**                   The main intent of this use case is to add physician availability information.

**Pre Condition:**             Assistant must be identified and authenticated.

**Post Condition:**            Physician availability information will be added successfully.

**Frequency of Occurrence:**   Medium

**Priority**                   High
__________________________________________________________
**Main Success Scenario: (Add Physician Availability Info)**

1. Assistant selects add physician availability information option.
2. System asks user to enter availability information such as available days in a week and available hours in a day.
3. Assistant enters the required information and submits them.
4. System then perform the following actions:
  * Validates the provided information.
  * Records the enter availability information.
  * Generates the physician’s calendar as per entered information.
  
_______________________________________________________________________________
**Alternate Flows** 

**Alt-1**

1. Invalid availability timings.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Scheduling):**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A

