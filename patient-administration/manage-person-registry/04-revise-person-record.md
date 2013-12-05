#####Use Case ID: UC-PAS02
#####Use Case Name: Revise Person Record

**Level:**                     User Level Goal

**Primary Actors:**            Registration Clerk (RC)

**Stakeholders:**              Registration Clerk, Medical Record Clerk, Person, Healthcare Provider

**Purpose:**                   The main intent of this use case is to revise person demographics.

**Pre Condition:**             Registration Clerk must be identified and authenticated. 

**Post Condition:**           Person demographics will be revised in person registry successfully.

**Frequency of Occurrence:**   High(Per Minute)
__________________________________________________________
**Main Success Scenario: (Revise Person Record))**

1. User invokes [get person detail use case](03-get-person-details.md)
2. System asks user to modify the specified person’s information such as contact info, name, date of birth.
5. User modifies the fields of person information and submits it.
6. System validates the fields and updates the person’s record in person registry OR informs if the information is invalid.

________________________________________________________________________
**Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST101302UV02
_______________________________________________________________
**CCHIT Criteria:**

N/A
_______________________________________________________________
**Hl7 RMIM (Domain: Patient Administration):**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm101301uv person rim](https://f.cloud.github.com/assets/5391320/1287976/f8d5c644-3002-11e3-9e4d-304595102e26.png)
_______________________________________________________________
**FHIR Resource:**
Same as [find candidate use case](02-find-candidates.md)

_______________________________________________________________
**Reference CDA Template:**

N/A
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**
Same as [find candidate use case](02-find-candidates.md)
