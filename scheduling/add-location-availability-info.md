####Description
--------------
The Scheduling Service module will allow user to add service delivery location’s availability information such as availability days in a week. The system will also generate the calendar according to entered availability information.

####Fully Dressed Use Case
--------------------------

#####Use Case ID: UC-SS07
#####Use Case Name: Add Location Availability Info

**Level:**                     User Level Goal

**Primary Actors:**            Assistant

**Stakeholders:**              Assistant, Patient, Physician, Healthcare Provider

**Purpose:**                   The main intent of this use case is to add location availability information.

**Pre Condition:**             Assistant must be identified and authenticated.

**Post Condition:**            Location availability information will be added successfully.

**Frequency of Occurrence:**   Medium

**Priority**                   High
__________________________________________________________
**Main Success Scenario: (Add Location Availability Info)**

1. Assistant selects add location availability information option.
2. System asks user to enter availability information such as available days in a week and available hours in a day.
3. Assistant enters the required information and submits them.
4. System then perform the following actions:
  * Validates the provided information.
  * Records the entered location availability information.
  * Generates the location’s calendar as per entered information.

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
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Scheduling):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A
_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

Yet to be defined.
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

N/A
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

N/A

