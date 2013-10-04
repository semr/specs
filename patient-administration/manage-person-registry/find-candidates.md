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

1. MRC selects find candidate demographics option.
2. System asks user to enter filtering criteria like demographic information (last name, sex and approximate birth date).
3. MRC specifies the filtering criteria.
4. System displays the list of person records.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid date.
2. No person record exist against the filtering criteria

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST101305UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A




