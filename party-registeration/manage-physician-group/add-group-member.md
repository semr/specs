#####Use Case ID: UC-PRS18
#####Use Case Name: Add Group Member

**Level:**                     User Level Goal

**Primary Actors:**            Clerk

**Stakeholders:**              Clerk, Provider, Provider Organization

**Purpose:**                   The main intent of this use case is to add member to a physician group.

**Pre Condition:**             Clerk must be identified and authenticated.

**Post Condition:**            Member will be added to physician group successfully.

**Frequency of Occurrence:**   Medium

__________________________________________________________
**Main Success Scenario: (Add Group Member)**

1. Clerk selects update add member to physician group option.
2. System displays the list of physicians and asks user to select one or more physician to add to physician group.
3. Clerk selects an appropriate physician.
4. System adds the physician to physician group.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**
1. Invalid information cannot be added.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Personnel Management):**

PRPM_ST402000UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

IP 02.02

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Personnel Management):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![group-member](https://f.cloud.github.com/assets/5391320/1371564/13864af6-3a3d-11e3-87ba-db77e321ea6a.png)
_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![group fhir resource](https://f.cloud.github.com/assets/5391320/1371207/ba29d552-3a34-11e3-82d7-78c553ef2aae.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

N/A
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

N/A
