#####Use Case ID: UC-PAS12
#####Use Case Name: Find Patients

**Level:**                     User Level Goal

**Primary Actors:**            Receptionist

**Stakeholders:**              Receptionist, Physician, Patient , Healthcare Providers

**Purpose:**                   The main intent of this use case is to find patient records.

**Pre Condition:**             Receptionist must be identified and authenticated.

**Post Condition:**            Patient records will be found successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Find Patients)**

1. Receptionist selects find candidate demographics option.
2. System asks user to enter filtering criteria such as demographic information (last name, sex, approximate birth date, current GP code and family name).
3. Receptionist specifies the filtering criteria.
4. System displays the list of patient records.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid date.
2. No patient record exist against the filtering criteria.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST201305UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 02.01, FN 01.01, FN 02.01




