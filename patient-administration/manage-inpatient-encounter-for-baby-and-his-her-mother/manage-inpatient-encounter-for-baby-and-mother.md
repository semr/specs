#####Use Case ID: UC-PAS53
#####Use Case Name: Manage Inpatient Encounter for Baby and Mother

**Level:**                     User Level Goal

**Primary Actors:**            Admitting Clerk

**Stakeholders:**              Admitting Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to maintain a relationship between
inpatient encounter for baby and inpatient encounter for Mother.

**Pre Condition:**             Admitting Clerk must be identified and authenticated.

**Post Condition:**            A relationship between inpatient encounter for baby and inpatient encounter for Mother will be maintained.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Link Inpatient Encounter for Baby to Mother))**

1. Admitting Clerk requests to link inpatient encounter for baby to mother
2. System displays the list of inpatient encounter for mothers.
3. Clerk selects appropriate inpatient encounter for mother and link it to baby’s inpatient encounter.
4. System links the inpatient encounter for baby to mother successfully.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:Unlink Inpatient Encounter for Baby to Mother**

1. Admitting Clerk requests to unlink inpatient encounter for baby to mother
2. System displays the list of inpatient encounter for mothers.
3. Clerk selects appropriate inpatient encounter for mother and link it to baby’s inpatient encounter.
4. System unlinks the inpatient encounter for baby to mother successfully.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST402008UV02, PRPA_ST402009UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm402008uv linking inpatient](https://f.cloud.github.com/assets/5391320/1370014/ba2432a0-3a0c-11e3-80de-dda7a69d7b52.png)

_______________________________________________________________
**Reference FHIR Resource:**
[More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

N/A
_______________________________________________________________
**Reference CDA Template:**
[More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

N/A
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**
[More Details](http://www.openehr.org/ckm/) 

N/A
