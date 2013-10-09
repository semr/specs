#####Use Case ID: UC-PAS15
#####Use Case Name: Add Service Delivery Location

**Level:**                     User Level Goal

**Primary Actors:**            Data Entry Clerk(DEC)

**Stakeholders:**              Data Entry Clerk(DEO), Patient , Healthcare Providers

**Purpose:**                   The main intent of this use case is to add service delivery locations.

**Pre Condition:**             Data Entry Clerk must be identified and authenticated.

**Post Condition:**            Service Delivery locations will be added successfully.

**Frequency of Occurrence:**   Low(Occasionally)
__________________________________________________________
**Main Success Scenario: (Add Service Delivery Location)**

1. DEC requests the system to add service delivery location.
2. System asks user to specify service delivery location metadata such as name and description.
3. DEC enters the required information.
4. System validates the enter information, assigns an identifier to the location and stores the record successfully.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be added.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST202301UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

IP 01.02

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST201301UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 01.01, AM 01.02, AM 01.03, AM 01.04, AM 01.05

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**

![prpa_rm202303uv location details](https://f.cloud.github.com/assets/5391320/1295192/c612b858-30a6-11e3-8293-8eda1836623a.png)
_______________________________________________________________
**Reference FHIR Resource:**

![location fhir resource](https://f.cloud.github.com/assets/5391320/1295189/b51b8674-30a6-11e3-8883-30c0c9cb1534.png)
_______________________________________________________________
**Reference CDA Template:**

Entry Level Template **"Service Delivery Location"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**

N/A




