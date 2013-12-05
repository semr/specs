#####Use Case ID: UC-PA03
#####Use Case Name: Get Patient Details

**Level:**                     User Level Goal

**Primary Actors:**            Receptionist

**Stakeholders:**              Receptionist, Physician, Patient, Healthcare Providers

**Purpose:**                   The main intent of this use case is to get patient demographics.

**Pre Condition:**             Receptionist must be identified and authenticated. 

**Post Condition:**            Patient demographics will be displayed successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario:**

1. Invoke pa02-find-patient use case
2. User selects the appropriate patient for displaying details.
6. System displays the patient information.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST201307UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 02.01, FN 01.01, FN 02.01
________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST201301UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 01.01, AM 01.02, AM 01.03, AM 01.04, AM 01.05

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm201303uv patient demographics](https://f.cloud.github.com/assets/5391320/1288161/55b8e064-3006-11e3-8aa6-8c7d1492d211.png)
_______________________________________________________________
**Reference FHIR Resource:**
Same as pa01-add-patient use case

_______________________________________________________________
**Reference CDA Template:**
Same as pa01-add-patient use case

_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**
Same as pa01-add-patient use case



