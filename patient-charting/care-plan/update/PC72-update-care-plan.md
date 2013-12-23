#####Use Case ID: UC-PC72
#####Use Case Name: Update Care Plan

**Level:**                     User Level Goal

**Primary Actors:**            Physician, Nurse, Patient

**Stakeholders:**              Physician, Nurse, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to update the care plan as per requiements or interventions. Note that the system will maintain the snapshots of care plane instances to allow user to fall back to the previous care plan or revert the changes made to a plan.

**Pre Condition:**             User must be identified and authenticated.

**Post Condition:**            Care Plan details will be updated successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Update Care Plan)**

1.	User performs the actions in [list care plans usecase](../read/PC41-list-care-plans.md).
2.	System displays the list of care plans.
3.	User selects an appropriate care plan.
4.	System displays the care plan details and asks user to modify desired fields.
5.	User modifies the plan details such as goals, activities, status, notes and summary details etc.
6.	System validates the changes, creates a modified version of care plan and records the time of changes commited.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**
[More Details](https://www.cchit.org/cchit-certified)

AM 17.03




