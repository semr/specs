#####Use Case ID: UC-PC71
#####Use Case Name: Print Procedure Details

**Level:**                     User Level Goal

**Primary Actors:**            Physician, Nurse, Patient

**Stakeholders:**              Physician, Nurse, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to update the procedure details in case entered in error. Note that the system will maintain the snapshots of procedure instances to allow user to track changes in details.

**Pre Condition:**             User must be identified and authenticated.

**Post Condition:**            Procedure details will be updated successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Print Procedure Details)**

1.	User performs the actions in [list procedures usecase](../read/PC68-list-procedures.md).
2.	System displays the list of procedures.
3.	User selects an appropriate procedure.
4.	System displays the procedure details and asks user to modify desired fields.
5.	User modifies the required fields such as date, bodysite, diagnosis, medication etc.
6.	System validates the changes and creates a modified version of procedure record.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**
[More Details](https://www.cchit.org/cchit-certified)

N/A




