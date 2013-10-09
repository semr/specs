#####Use Case ID: UC-PAS17
#####Use Case Name: Nullify Location

**Level:**                     User Level Goal

**Primary Actors:**            Medical Record Clerk(MRC)

**Stakeholders:**              Medical Record Clerk(MRC), Patient , Healthcare Providers

**Purpose:**                   The main intent of this use case is to nullify service delivery locations.

**Pre Condition:**             MRC must be identified and authenticated.

**Post Condition:**            Service Delivery locations will be nullified successfully.

**Frequency of Occurrence:**   Low(Occasionally)
__________________________________________________________
**Main Success Scenario: (Nullify Location)**

1. MRC requests system to nullify a service delivery location record.
2. System displays a list of service delivery location records.
3. MRC specifies the service delivery location record “entered in error”.
4. System nullifies the service delivery location record.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST202303UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST201301UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 01.01, AM 01.02, AM 01.03, AM 01.04, AM 01.05

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**

![prpa_rm202305uv location nullify](https://f.cloud.github.com/assets/5391320/1295202/255dc4ba-30a7-11e3-9c1a-6e7fc18db5b1.png)
_______________________________________________________________
**Reference FHIR Resource:**

![location fhir resource](https://f.cloud.github.com/assets/5391320/1295189/b51b8674-30a6-11e3-8883-30c0c9cb1534.png)
_______________________________________________________________
**Reference CDA Template:**

N/A
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**

N/A




