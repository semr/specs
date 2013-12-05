#####Use Case ID: UC-PA02
#####Use Case Name: Find Patients

**Level:**                     User Level Goal

**Primary Actors:**            Receptionist

**Stakeholders:**              Receptionist, Physician, Patient, Healthcare Providers

**Purpose:**                   The main intent of this use case is to find patient records.

**Pre Condition:**             Receptionist must be identified and authenticated.

**Post Condition:**            Patient records will be found successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario**

1. User selects find patient option.
2. System asks user to enter filtering criteria such as demographic information (last name, gender, approximate birth date, or contact information).
3. User specifies values for filtering criteria.
4. System displays the list of patient records OR informs if no record is found

________________________________________________________________________
**Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST201305UV02
PRPA_ST201301UV02

**CCHIT Criteria:**

AM 02.01, FN 01.01, FN 02.01
AM 01.01, AM 01.02, AM 01.03, AM 01.04, AM 01.05

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm201306uv query by demographics](https://f.cloud.github.com/assets/5391320/1288166/69cab60e-3006-11e3-8c4a-90e203ab02cb.png)
_______________________________________________________________
**Reference FHIR Resource:**
Same as "pa01-add-patient" use case.

_______________________________________________________________
**Reference CDA Template:**
Same as "pa01-add-patient" use case.

_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**

Same as "pa01-add-patient" use case.
