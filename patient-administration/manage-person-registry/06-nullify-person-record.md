#####Use Case ID: UC-PAS03
#####Use Case Name: Nullify Person Record

**Level:**                     User Level Goal

**Primary Actors:**            Medical Record Clerk (MRC)

**Stakeholders:**              Medical Record Clerk, Person, Healthcare Provider

**Purpose:**                   The main intent of this use case is to nullify person record.

**Pre Condition:**             MRC must be identified and authenticated. 

**Post Condition:**            Person record nullified successfully.

**Frequency of Occurrence:**   High(Per Minute)
__________________________________________________________
**Main Success Scenario: (Nullify Person Record)**

1. User invokes [get person details](03-get-person-details.md) use case.
2. User selects to nullify the person record.
4. System confirms the user action and nullifies the person record.

________________________________________________________________________
**Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST101303UV02
_______________________________________________________________
**CCHIT Criteria:**

N/A

_______________________________________________________________
**Hl7 RMIM (Domain: Patient Administration):**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm101305uv nullify person](https://f.cloud.github.com/assets/5391320/1287988/61dbb806-3003-11e3-85ca-f1d0303dab4f.png)
_______________________________________________________________
**FHIR Resource:**
Same as [add person](01-add-person.md) use case.


_______________________________________________________________
**Reference CDA Template:**

N/A
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**
Same as [add person](01-add-person.md) use case.
