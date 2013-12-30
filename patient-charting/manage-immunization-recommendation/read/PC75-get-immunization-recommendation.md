#####Use Case ID: UC-PC75
#####Use Case Name: Get Immunization Recommendations

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Nurse

**Purpose:**                   The main intent of this use case is to display the details of immunization recommendation of a patient condition.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            Immunization Recommendations details displayed uccessfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Get Immunization Recommendations)**

1.  User performs the actions in [list immunization recommendations usecase](PC74-list-immunization-recommendation.md).
2.	System displays the list of immunization recommendations.
3.	User selects an appropriate immunization recommendation and selects view details option.
4.	System displays the details of selected immunization recommendations.

__________________________________________________________
**Alternate Flows:**

**Alt-1: List Immunization Recommendations in a Patient Chart**

1.	Physician selects [find patients](../../../patient-administration/manage-patient-registry/find-patients.md) option.
2.	System displays the list of patients.
3.	Physician navigate to an appropriate patient and then selects view patient's chart option.
4.	System displays the full patient chart.
5.	Physician selectes the immunization recommendation tab.
6.	System then displays the patient's immunization recommendation list.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**
[More Details](https://www.cchit.org/cchit-certified)

FN 16.03
