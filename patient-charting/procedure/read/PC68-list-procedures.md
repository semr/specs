#####Use Case ID: UC-PC68
#####Use Case Name: List Procedures

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to display the list of patients.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            List of procedures will be displayed successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (List Procedures)**

1.	Physician requests to display list of procedures.
2.	System asks user to specify the filtering criteria(if any) such as subject, performers, encounter, date and type.
3.	Physician enters the filtering criteria.
4.	System then displays the list of procedure records as per criteria.

__________________________________________________________
**Alternate Flows:**

**Alt-1: List Procedures in a Patient Chart**

1.	Physician selects [find patients](../../../patient-administration/manage-patient-registry/find-patients.md) option.
2.	System displays the list of patients.
3.	Physician navigate to an appropriate patient and then selects view patient's chart option.
4.	System displays the full patient chart.
5.	Physician selectes the procedures button.
6.	System then displays the patient's list of procedures.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**
[More Details](https://www.cchit.org/cchit-certified)

N/A


