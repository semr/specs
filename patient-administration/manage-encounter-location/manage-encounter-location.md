#####Use Case ID: UC-PAS74
#####Use Case Name: Manage Encounter Location

**Level:**                     User Level Goal

**Primary Actors:**            Clerk

**Stakeholders:**              Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to change or cancel change request forinpatient location during an encounter.

**Pre Condition:**             Clerk must be identified and authenticated. 

**Post Condition:**            System will record the change of patient encounter.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Change Patient Location)**

1. Clerk requests to change patient location.
2. System displays the list of available locations for encounter.
3. Clerk selects appropriate location as a replacement.
4. System changes the patient location to a new location.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:Cancel Patient Location Change**

1. Clerk selects cancel patient location change option.
2. System displays the list of change patient location actions.
3. Clerk selects appropriate change patient location action.
4. System reverses the change in patient location.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST302011UV02, PRPA_ST302012UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![t-prpa_rm302011uv encounter location](https://f.cloud.github.com/assets/5391320/1370586/8d3e367e-3a24-11e3-8b7e-0c162739976b.png)
_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![encounter fhir resource](https://f.cloud.github.com/assets/5391320/1369999/74cb4914-3a0c-11e3-8d49-1317a89cc65d.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Entry Level Template **"Service Delivery Location"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

N/A

