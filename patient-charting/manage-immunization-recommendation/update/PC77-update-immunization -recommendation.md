#####Use Case ID: UC-PC77
#####Use Case Name: Update Immunization Recommendation

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Nurse

**Purpose:**                   The main intent of this use case is to update a immunization recommendation for a patient condition.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            Immunization Recommendation updated successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Update Immunization Recommendation)**

1.  User performs the actions in [list immunization recommendations usecase](../read/PC74-list-immunization-recommendation.md).
2.	System displays the list of immunization recommendations.
3.	User selects an appropriate immunization recommendation.
4.	System displays the immunization recommendation details and asks user to modify desired fields.
5.	User modifies the immunization details such as immunizatio type, date/time, route, site and manufacturer.
6.	System validates the changes, creates a modified version of immunization recommendation and records the time of changes commited.

__________________________________________________________
**Alternate Flows:**

**Alt-1: Interaction Checking**

1.	Repeat step 1 to 5 from the main scenario.
2.	Physician review the system response of interaction checking and take actions as: 
  * In case any allergy interaction reveals, it sort some other alternate immunization and proceed with normal order flow if find no allergy interaction, 
  * In case absence of any allergy interaction, the physician proceeds with normal flow of immunization recommendation process, 
  * System will set the immunization recommendation status to active.
3.	The step 6 in main scenario of events are then executed.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**
[More Details](https://www.cchit.org/cchit-certified)

FN 16.02, FN 16.03, IP 15.07
