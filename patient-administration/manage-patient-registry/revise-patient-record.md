#####Use Case ID: UC-PAS09
#####Use Case Name: Revise Patient Record

**Level:**                     User Level Goal

**Primary Actors:**            Registration Clerk (RC)

**Stakeholders:**              Registration Clerk, Physician, Patient , Healthcare Providers

**Purpose:**                   The main intent of this use case is to revise patient demographics.

**Pre Condition:**             RC must be identified and authenticated.

**Post Condition:**            Patient demographics will be revised in patient registry successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Revise Patient Record)**

1. RC requests to revise person’s record.
2. System displays the list of patients available.
3. RC selects a patient’s record to revise.
4. System asks user to modify the specified patient’s demographic elements like contact and guarantor information.
5. RC modifies the fields of patient’s demographics and submits it.
6. System validates the fields and updates the patient’s record in person registry.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be entered.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST201302UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 02.01, AM 02.02, AM 02.04, FN 01.01, FN 01.02
