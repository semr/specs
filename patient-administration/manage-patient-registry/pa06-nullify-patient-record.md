#####Use Case ID: UC-PA06
#####Use Case Name: Nullify Patient Record

**Level:**                     User Level Goal

**Primary Actors:**            Medical Record Clerk (MRC)

**Stakeholders:**              Medical Record Clerk, Physician, Patient , Healthcare Providers

**Purpose:**                   The main intent of this use case is to nullify patient record.

**Pre Condition:**             MRC must be identified and authenticated. 

**Post Condition:**            Patient record will be nullified successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario**

1. Invoke pa03-get-patient-details use case
2. User selects to nullify the patient record.
3. System cofirms the user action and nullifies the patient record.

________________________________________________________________________
**Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST201303UV02

PRPA_ST201301UV02
_______________________________________________________________
**CCHIT Criteria:**

AM 01.01, AM 01.02, AM 01.03, AM 01.04, AM 01.05

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm201305uv patient nullify](https://f.cloud.github.com/assets/5391320/1288164/658935ac-3006-11e3-88b1-082eae7c831b.png)
_______________________________________________________________
**Reference FHIR Resource:**
Same as pa01-add-patient use case

_______________________________________________________________
**Reference CDA Template:**
Same as pa01-add-patient use case

_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**
Same as pa01-add-patient use case
