#####Use Case ID: UC-PRS17
#####Use Case Name: Add Physician Group

**Level:**                     User Level Goal

**Primary Actors:**            Clerk

**Stakeholders:**              Clerk, Provider, Provider Organization

**Purpose:**                   The main intent of this use case is to establish new physician group.

**Pre Condition:**             Clerk must be identified and authenticated.

**Post Condition:**            Physician group will be added successfully.

**Frequency of Occurrence:**   Medium

__________________________________________________________
**Main Success Scenario: (Add Physician Group)**

1. Clerk selects add physician group option.
2. System asks to enter the physician group details such as id, name, description and list of physicians.
3. Clerk enters the required information and submits it.
4. System then perform the following actions:
  * Validates the organization details.
  * Records physician group details.
  

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be added.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Personnel Management):**

PRPM_ST402000UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Personnel Management):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![org-memebers](https://f.cloud.github.com/assets/5391320/1371523/4760ebf2-3a3c-11e3-93fd-6ceb539b7ca2.png)
_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![group fhir resource](https://f.cloud.github.com/assets/5391320/1371207/ba29d552-3a34-11e3-82d7-78c553ef2aae.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

N/A
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

N/A
