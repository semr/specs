#####Use Case ID: UC-PAS60
#####Use Case Name: Nullify Emergency Encounter

**Level:**                     User Level Goal

**Primary Actors:**            Emergency Room Clerk (ER Clerk)

**Stakeholders:**              Emergency Room Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to nullify emergency encounter.

**Pre Condition:**             Emergency Room Clerk must be identified and authenticated. 

**Post Condition:**            Emergency encounter nullified successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Nullify Emergency Encounter)**

1. ER Clerk requests system to nullify emergency encounter information.
2. System displays a list of emergency encounters.
3. ER Clerk specifies the appropriate encounter information “entered in error”.
4. System nullifies the encounter information.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST403999UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A
_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![encounter fhir resource](https://f.cloud.github.com/assets/5391320/1295268/cb11790e-30a9-11e3-8af5-6e7bb9dfdbda.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

N/A

_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

N/A
