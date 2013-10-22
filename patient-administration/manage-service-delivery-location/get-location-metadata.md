#####Use Case ID: UC-PAS20
#####Use Case Name: Get Location Metadata

**Level:**                     User Level Goal

**Primary Actors:**            Clerk

**Stakeholders:**              Clerk, Patient , Healthcare Providers

**Purpose:**                   The main intent of this use case is to get location metadata.

**Pre Condition:**             Clerk must be identified and authenticated.

**Post Condition:**            Location metadata will be displayed successfully.

**Frequency of Occurrence:**   Low(Occasionally)
__________________________________________________________
**Main Success Scenario: (Get Location Metadata))**

1. Clerk selects find service delivery location option.
2. System asks user to enter filtering criteria such as location metadata (name, zip code, type, status code).
3. Clerk specifies the filtering criteria.
4. System displays the list of service delivery location records.
5. Clerk selects the appropriate location for metadata.
6. System displays the service delivery location metadata.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST202307UV02
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
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm202303uv location details](https://f.cloud.github.com/assets/5391320/1295192/c612b858-30a6-11e3-8293-8eda1836623a.png)
_______________________________________________________________
**Reference FHIR Resource:**
[More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![location fhir resource](https://f.cloud.github.com/assets/5391320/1295189/b51b8674-30a6-11e3-8883-30c0c9cb1534.png)
_______________________________________________________________
**Reference CDA Template:**
[More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Entry Level Template **"Service Delivery Location"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**
[More Details](http://www.openehr.org/ckm/)

N/A




