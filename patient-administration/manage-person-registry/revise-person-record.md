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

1. RC requests to revise person’s record.
2. System displays the list the persons available.
3. RC selects a person’s record to revise.
4. System asks user to modify the specified person’s demographic elements like contact info, name, date of birth etc
5. RC modifies the fields of person demographics and submits it.
6. System validates the fields and updates the person’s record in person registry.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be entered.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST101302UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A




