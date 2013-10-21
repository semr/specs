####Description
--------------
The Scheduling Service module will allow user to revise physicians’ availability information such as availability hours in a day and working days in a week. The system will also revise the physician’s calendar as well.

####Fully Dressed Use Case
--------------------------

#####Use Case ID: UC-SS06
#####Use Case Name: Revise Physician Availability Info

**Level:**                     User Level Goal

**Primary Actors:**            Assistant

**Stakeholders:**              Assistant, Patient, Physician, Healthcare Provider

**Purpose:**                   The main intent of this use case is to revise physician availability information.

**Pre Condition:**             Assistant must be identified and authenticated.

**Post Condition:**            Physician availability information will be revised successfully.

**Frequency of Occurrence:**   Medium

**Priority**                   High
__________________________________________________________
**Main Success Scenario: (Revise Physician Availability Info)**

1. Assistant selects revise physician availability information option.
2. System displays the list of physicians.
3. Assistant selects an appropriate physician.
4. System displays the availability information of the selected physician and asks user to modify the desired information.
5. Assistant modifies the availability information and submits them.
6. System then perform the following actions:
  * Validates the provided information.
  * Revises the availability information.
  * Generates the revised physician’s calendar.
  
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
**Reference Hl7 RMIM (Domain: Patient Administration):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

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

