#####Use Case ID: UC-PAS05
#####Use Case Name: Find Candidates

**Level:**                     User Level Goal

**Primary Actors:**            Medical Record Clerk (MRC)

**Stakeholders:**              Medical Record Clerk, Person, Healthcare Provider

**Purpose:**                   The main intent of this use case is to find candidates from person registry.

**Pre Condition:**             MRC must be identified and authenticated.

**Post Condition:**            Appropriate candidate found successfully.

**Frequency of Occurrence:**   High(Per Minute)
__________________________________________________________
**Main Success Scenario: (Find Candidates)**

1. User selects find candidate option.
2. System asks user to enter filtering criteria such as demographic information (including last name, address, gender and approximate birth date).
3. User specifies the values for filtering criteria.
4. System displays the list of person records OR informs if no record is found.

________________________________________________________________________
**Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST101305UV02
_______________________________________________________________
**CCHIT Criteria:**

N/A

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm101306uv query by demographics](https://f.cloud.github.com/assets/5391320/1288047/1b29811c-3004-11e3-9f32-2748989fb2dc.png)
_______________________________________________________________
**Reference FHIR Resource:**
Same as [add person use case](01-add-person.md)

_______________________________________________________________
**Reference CDA Template:**

N/A
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**
Same as [add person use case](01-add-person.md)
