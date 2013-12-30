#####Use Case ID: UC-PC74
#####Use Case Name: List Immunization Recommendations

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Nurse

**Purpose:**                   The main intent of this use case is to display a list of immunization recommendations for a patient condition.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            Immunization Recommendations listed uccessfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (List Immunization Recommendations)**

1.	Physician requests to display list of immunization recommendations.
2.	System asks user to specify the filtering criteria(if any) such as 
      * Immunization type
      * date and time of administration 
      * route and site
      * manufacturer
3.	Physician enters the filtering criteria.
4.	System then displays the list of immunization recommendations as per criteria.

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
