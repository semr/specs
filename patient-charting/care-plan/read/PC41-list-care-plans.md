#####Use Case ID: UC-PC41
#####Use Case Name: List Care Plans

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to display the list of care plans.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            List of care plans will be displayed successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (List Care Plans)**

1.	Physician requests to display list of care plans.
2.	System asks user to specify the filtering criteria(if any) such as patient, activities, participants, status and date.
3.	Physician enters the filtering criteria.
4.	System then displays the list of care plans as per criteria.

__________________________________________________________
**Alternate Flows:**

**Alt-1: List Procedures in a Patient Chart**

1.	Physician selects [find patients](../../../patient-administration/manage-patient-registry/find-patients.md) option.
2.	System displays the list of patients.
3.	Physician navigate to an appropriate patient and then selects view patient's chart option.
4.	System displays the full patient chart.
5.	Physician selectes the care plans tab.
6.	System then displays the patient's care plans list.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**
[More Details](https://www.cchit.org/cchit-certified)

AM 17.01


