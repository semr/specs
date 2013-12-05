#####Use Case ID: UC-PAS06
#####Use Case Name: Get Person Details

**Level:**                     User Level Goal

**Primary Actors:**            Registration Clerk (RC)

**Stakeholders:**              Registration Clerk, Person, Healthcare Provider

**Purpose:**                   The main intent of this use case is to get person demographics.

**Pre Condition:**             Registration Clerk must be identified and authenticated. 

**Post Condition:**            Person demographics displayed successfully.

**Frequency of Occurrence:**   High(Per Minute)
__________________________________________________________
**Main Success Scenario: (Get Person Demographics)**

1. User invokes [find candidates use case](02-find-candidates.md).
2. User selects the appropriate person for view its details.
3. System displays the person’s detailed information.

________________________________________________________________________
**Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST101307UV02
_______________________________________________________________
**CCHIT Criteria:**

N/A

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm101303uv demographics](https://f.cloud.github.com/assets/5391320/1288063/64262c4e-3004-11e3-97ac-b73a7902fde1.png)
_______________________________________________________________
**Reference FHIR Resource:**
Same as [add person use case](01-add-person.md)

_______________________________________________________________
**Reference CDA Template:**

N/A
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**
Same as [add person use case](01-add-person.md)
