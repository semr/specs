#####Use Case ID: UC-PAS04
#####Use Case Name: Resolve Duplicate Records

**Level:**                     User Level Goal

**Primary Actors:**            Medical Record Clerk (MRC)

**Stakeholders:**              Medical Record Clerk, Person, Healthcare Provider

**Purpose:**                   The main intent of this use case is to resolve person’s duplicate records.

**Pre Condition:**             MRC must be identified and authenticated. 

**Post Condition:**            Duplicate records resolved successfully.

**Frequency of Occurrence:**   Low
__________________________________________________________
**Main Success Scenario: (Resolve Duplicate Records)**

1. User invokes [find person details use case](03-get-person-details.md).
2. User selects find duplicate option.
3. System will show the list of possible duplicate records and will highlight duplicated information.
4. User will select "resolve duplicate" option for individual record and will specify the master record.
5. System will resolve the duplicate record.
6. Step 4 maybe repeated for all duplicate records retrieved in Step 3.

________________________________________________________________________
**Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST101304UV02
_______________________________________________________________
**CCHIT Criteria:**

N/A

_______________________________________________________________
**Hl7 RMIM (Domain: Patient Administration):**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![resolve-duplicate](https://f.cloud.github.com/assets/5391320/1288015/d4456892-3003-11e3-8c86-54d1927a4b2c.png)
_______________________________________________________________
**Reference FHIR Resource:**
Same as [add person use case](01-add-person.md)

_______________________________________________________________
**Reference CDA Template:**

N/A
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**
Same as [add person use case](01-add-person.md)
