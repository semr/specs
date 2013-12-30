#####Use Case ID: UC-PC73
#####Use Case Name: Create Immunization Recommendation

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Nurse

**Purpose:**                   The main intent of this use case is to create a immunization recommendation for a patient condition.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            Immunization Recommendation recorded successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Create Immunization Recommendation)**

1. Physician selects a immunization recommendation option.
2. System asks user to specify the following information:
    * Immunization type and dose 
    * date and time of administration 
    * route and site
    * manufacturer
    * user ID.
3. Physician enters the required fields and specifies the clinical assesments required for immunization if required.
4. System validates the fields and records the immunization recommendation.

__________________________________________________________
**Alternate Flows:**

**Alt-1: Interaction Checking**

1.	Repeat step 1 to 3 from the main scenario.
2.	Physician review the system response of interaction checking and take actions as: 
  * In case any allergy interaction reveals, it sort some other alternate immunization and proceed with normal order flow if find no allergy interaction, 
  * In case absence of any allergy interaction, the physician proceeds with normal flow of immunization recommendation process, 
  * System will set the immunization recommendation status to active.
3.	The step 4 in main scenario of events are then executed.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**
[More Details](https://www.cchit.org/cchit-certified)

FN 16.02, FN 16.03, IP 15.07
