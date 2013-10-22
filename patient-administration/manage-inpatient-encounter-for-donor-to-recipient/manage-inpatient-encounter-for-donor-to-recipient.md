#####Use Case ID: UC-PAS53
#####Use Case Name: Manage Inpatient Encounter for Donor to Recipient

**Level:**                     User Level Goal

**Primary Actors:**            Admitting Clerk

**Stakeholders:**              Admitting Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to maintain a relationship between inpatient encounter for organ donor and inpatient encounter for organ receiver.

**Pre Condition:**             Admitting Clerk must be identified and authenticated.

**Post Condition:**           A relationship between inpatient encounter for organ donor and inpatient encounter for organ receiver will be maintained.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Link Inpatient Encounter for Donor to Recipient)**

1. Admitting Clerk requests to link inpatient encounter for Donor to Recipient
2. System displays the list of both inpatient encounters for Donor and inpatient encounters for recipient.
3. Clerk selects appropriate inpatient encounters and links them.
4. System links the inpatient encounter for donor to recipient successfully.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:Unlink Inpatient Encounter for Donor to Recipient**

1. Admitting Clerk requests to unlink inpatient encounter for donor to recipient.
2. System displays the list of linked inpatient encounters.
3. Clerk selects appropriate linked inpatient encounters and unlinks them.
4. System unlinks the inpatient encounter for donor to recipient successfully.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST402010UV02, PRPA_ST402010UV02
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
