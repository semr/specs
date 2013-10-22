#####Use Case ID: UC-PCS45
#####Use Case Name: Modify Guideline

**Level:**                     User Level Goal

**Primary Actors:**            Domain Expert

**Stakeholders:**              Domain Expert, Patient, Healthcare Provider

**Purpose:**                   The main intent of this use case is to modify disease management, preventive services and wellness guidelines. Updates to support changes in best practice guidelines. Associated reference material can be within the system or accessed through links to external sources.

**Pre Condition:**             Domain Expert must be identified and authenticated.

**Post Condition:**            Guideline will be modified successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Modify Guideline)**

1. DE selects edit guideline option.
2. System displays the list of guideline.
3. DE selects an appropriate guideline.
4. System displays the guideline asks user to modify the guideline, any reference material and reasons to override.
5. DE modifies the guideline and submits it.
6. System then performs the following actions:
  * Validates the fields.
  * Records the modified guideline.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 22.04, AM 22.05, AM 22.06, AM 22.07
_______________________________________________________________
**Reference Hl7 RMIM :** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A

_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

Yet to be defined.
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

N/A
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

N/A
