#####Use Case ID: UC-PA04
#####Use Case Name: Revise Patient Record

**Level:**                     User Level Goal

**Primary Actors:**            Registration Clerk (RC)

**Stakeholders:**              Registration Clerk, Physician, Patient , Healthcare Providers

**Purpose:**                   The main intent of this use case is to revise patient demographics.

**Pre Condition:**             RC must be identified and authenticated.

**Post Condition:**            Patient demographics will be revised in patient registry successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario:**

1. Invoke p03-get-patient-details use case.
2. User selects to modify patient record option.
3. System will generate a form filled with existing values.
4. User will modify the specified elements and submits the updated record.
5. System validates the values and either updates the patient’s record in person registry OR displays an error message.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST201302UV02
PRPA_ST201301UV02

**Reference CCHIT Criteria:**

AM 02.01, AM 02.02, AM 02.04, FN 01.01, FN 01.02
AM 01.01, AM 01.02, AM 01.03, AM 01.04, AM 01.05

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm201301uv patient](https://f.cloud.github.com/assets/5391320/1288158/4fa238f6-3006-11e3-9126-8c9c7eec474f.png)
_______________________________________________________________
**Reference FHIR Resource:**
Same as pa01-add-patient use case.

_______________________________________________________________
**Reference CDA Template:**
Same as pa01-add-patient use case.

_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**
Same as pa01-add-patient use case.
