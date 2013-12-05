#####Use Case ID: UC-PA05
#####Use Case Name: Resolve Duplicate Patient Records

**Level:**                     User Level Goal

**Primary Actors:**            Medical Record Clerk (MRC)

**Stakeholders:**              Medical Record Clerk, Physician, Patient , Healthcare Providers

**Purpose:**                   The main intent of this use case is to resolve patient records.

**Pre Condition:**             MRC must be identified and authenticated. 

**Post Condition:**            Duplicate patient records will be resolved successfully.

**Frequency of Occurrence:**   Low
__________________________________________________________
**Main Success Scenario**

1. Invoke pa-03-get-patient-details use case.
2. User selects resolve duplicate option.
3. System will show the list of possible duplicate records and will highlight duplicated information.
4. User will select "resolve duplicate" option for indivual record and will specify the master record.
5. System will resolve the duplicate record.
6. Step 4 maybe repeated for all duplicate records retrieved in Step 3.

________________________________________________________________________
**Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST201304UV02
PRPA_ST201301UV02

**CCHIT Criteria:**

AM 01.01, AM 01.02, AM 01.03, AM 01.04, AM 01.05

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm201301uv patient](https://f.cloud.github.com/assets/5391320/1288158/4fa238f6-3006-11e3-9126-8c9c7eec474f.png)
_______________________________________________________________
**Reference FHIR Resource:**

Same as pa01-add-patient use case

_______________________________________________________________
**Reference CDA Template:**
Same as pa01-add-patient use case

_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**

Same as pa01-add-patient use case
