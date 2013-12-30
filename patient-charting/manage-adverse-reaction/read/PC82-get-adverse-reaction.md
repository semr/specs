#####Use Case ID: UC-PC82
#####Use Case Name: Get Adverse Reaction

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Nurse

**Purpose:**                   The main intent of this use case is to display the details of adverse reaction of a patient condition.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            Adverse Reaction details displayed successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Get Adverse Reaction)**

1.  User performs the actions in [list adverse reactions usecase](PC81-list-adverse-reactions.md).
2.	System displays the list of adverse reactions.
3.	User selects an appropriate adverse reaction and selects view details option.
4.	System displays the details including the associated agents such as medication of selected adverse reactions.

__________________________________________________________
**Alternate Flows:**

**Alt-1: Get Adverse Reaction in a Patient Chart**

1.	Physician selects [find patients](../../../patient-administration/manage-patient-registry/find-patients.md) option.
2.	System displays the list of patients.
3.	Physician navigate to an appropriate patient and then selects view patient's chart option.
4.	System displays the full patient chart.
5.	Physician selectes the adverse reaction tab.
6.	System then displays the patient's adverse reactions list.
7.	Repeat step 3 and 4 from the success scenario.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**
[More Details](https://www.cchit.org/cchit-certified)

FN 05.12, FN 05.13
