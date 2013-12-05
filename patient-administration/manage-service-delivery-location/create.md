#####Use Case ID: UC-PAS15
#####Use Case Name: Add Service Delivery Location

**Level:**                     User Level Goal

**Primary Actors:**            Data Entry Clerk (DEC)

**Stakeholders:**              Data Entry Clerk(DEO), Patient , Healthcare Providers

**Purpose:**                   The main intent of this use case is to add service delivery locations.

**Pre Condition:**             Data Entry Clerk must be identified and authenticated.

**Post Condition:**            Service Delivery locations will be added successfully.

**Frequency of Occurrence:**   Low (Occasionally)
__________________________________________________________
**Main Success Scenario: (Add Service Delivery Location)**

1. User requests the system to add service delivery location.
2. System asks user to specify service delivery location metadata such as name and description.
3. User enters the required information.
4. System validates the enter information, assigns an identifier to the location and stores the record successfully.

________________________________________________________________________
**Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST202301UV02
_______________________________________________________________
**CCHIT Criteria:**

IP 01.02

________________________________________________________________________
**Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST201301UV02
_______________________________________________________________
**CCHIT Criteria:**

AM 01.01, AM 01.02, AM 01.03, AM 01.04, AM 01.05

_______________________________________________________________
**Hl7 RMIM (Domain: Patient Administration):**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm202301uv location activate](https://f.cloud.github.com/assets/5391320/1295190/b9b5512e-30a6-11e3-919a-38532a33d80f.png)
