#####Use Case ID: UC-PAS18
#####Use Case Name: Resolve Duplicate Location Records

**Level:**                     User Level Goal

**Primary Actors:**            Medical Record Clerk(MRC)

**Stakeholders:**              Medical Record Clerk(MRC), Patient , Healthcare Providers

**Purpose:**                   The main intent of this use case is to resolve duplicate service delivery locations.

**Pre Condition:**             MRC must be identified and authenticated.

**Post Condition:**            Duplicate service delivery locations will be resolved successfully.

**Frequency of Occurrence:**   Low(Occasionally)
__________________________________________________________
**Main Success Scenario: (Resolve Duplicate Location Records)**

1. MRC selects resolve location duplicates option.
2. System asks user to specify two identical service delivery location records, mark incorrect record as “obsolete” and link it to the correct service delivery location.
3. MRC performs required actions.
4. System resolves the duplicate locations.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Selected location does not exist.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST202304UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

IP 01.02




