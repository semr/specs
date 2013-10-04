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

1. MRC selects resolve duplicates option.
2. System asks user to specify two identical person registrations, mark incorrect record as “obsolete” and link it to the correct registration.
3. MRC performs required actions.
4. System resolves the duplicate registrations.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Selected registration does not exist.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST101304UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A




