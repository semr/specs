#####Use Case ID: UC-PC83
#####Use Case Name: Update Adverse Reaction

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Nurse

**Purpose:**                   The main intent of this use case is to update adverse reaction of a patient.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            Adverse Reaction updated successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Update Adverse Reaction)**

1.  User performs the actions in [list adverse reactions usecase](../read/PC81-list-adverse-reactions.md).
2.	System displays the list of adverse reactions.
3.	User selects an appropriate adverse reaction.
4.	System displays the adverse reactions details and asks user to modify desired fields.
5.	User modifies the reaction details such as type, date/time and severity.
6.	System validates the changes, creates a modified version of adverse reaction and records the time and user of committed changes.

__________________________________________________________
**Alternate Flows:**

**Alt-1: Update Adverse Reaction Status**

1.	Repeat step 1 to 5 from the main scenario.
2.	User modifies the status of the adverse reaction such as activate or de-activate.
3.	The step 6 in main scenario of events are then executed.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**
[More Details](https://www.cchit.org/cchit-certified)

FN 05.01, FN 05.05, FN 05.07, FN 05.12, FN 05.13
