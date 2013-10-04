#####Use Case ID: UC-PAS08
#####Use Case Name: Add Patient

**Level:**                     User Level Goal

**Primary Actors:**            Registration Clerk (RC)

**Stakeholders:**              Registration Clerk, Physician, Patient , Healthcare Providers

**Purpose:**                   The main intent of this use case is to add patient full demographics.

**Pre Condition:**             RC must be identified and authenticated. 

**Post Condition:**            Patient identifiers and demographics will be added in patient registry successfully.

**Frequency of Occurrence:**   High(Per Minute)
__________________________________________________________
**Main Success Scenario: (Add Patient)**

1. RC requests the system to add patient’s registry.
2. System asks user to enter patient’s full information including name, date of birth, address telephone number, email address, multiple identifiers (like master patient index, insurance subscriber ID, health plan Id, national patient Id), exempt from reporting function (like transferred, deceased, moved).
3. RC enters the required information.
4. System then performs following steps: **a)** Validates the entered information. **b)** Associates key identifiers information (i.e system Id, medical record number) with patient record. **c)** Stores patient record in separate discrete data fields successfully.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be added.
2. Invalid identifier.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST201301UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 01.01, AM 01.02, AM 01.03, AM 01.04, AM 01.05
