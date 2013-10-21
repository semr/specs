#####Use Case ID: UC-PRS19
#####Use Case Name: Remove Physician from Group

**Level:**                     User Level Goal

**Primary Actors:**            Clerk

**Stakeholders:**              Clerk, Provider, Provider Organization

**Purpose:**                   The main intent of this use case is to remove physician from physician group.

**Pre Condition:**             Clerk must be identified and authenticated.

**Post Condition:**            Physicians will be removed successfully.

**Frequency of Occurrence:**   Medium

__________________________________________________________
**Main Success Scenario: (Remove Physician from Group)**

1. Clerk requests remove physician from group option.
2. System asks user to specify physician group.
3. Clerk specifies the group and submits it.
4. System displays the details of physician group including the list of members or physician in that group and asks user to select a member to remove.
5. Clerk selects an appropriate member to remove from the group.
6. System records the changes successfully.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Personnel Management):**

PRPM_ST402000UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A

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
