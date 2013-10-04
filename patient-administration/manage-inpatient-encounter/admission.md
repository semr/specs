#####Use Case ID: UC-PAS43
#####Use Case Name: Admission

**Level:**                     User Level Goal

**Primary Actors:**            Admitting Clerk

**Stakeholders:**              Admitting Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to capture inpatient admission information.

**Pre Condition:**             Admitting Clerk must be identified and authenticated.

**Post Condition:**            Patient admitted successfully.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Admission)**

1. Admitting Clerk selects patient admission for inpatient encounter.
2. System displays the list of appointment for inpatient encounters.
3. Admitting Clerk reviews appointment details and requests system to create inpatient encounter.
4. System asks user to enter encounter details such as patient stay details (floor, ward, room), admission type (such as “elective”), consulting physician, admitting diagnosis and emergency contact information (name, contact number).
5. Admitting Clerk enters the required information and submits it.
6. System successfully records inpatient encounter information.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST402001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

IP 15.12, FN 03.01, IP 01.01, IP 01.02, IP 01.03




