#####Use Case ID: UC-PAS33
#####Use Case Name: Admission

**Level:**                     User Level Goal

**Primary Actors:**            Admitting Clerk

**Stakeholders:**              Admitting Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to record admission information

**Pre Condition:**             Admitting Clerk must be identified and authenticated.

**Post Condition:**            Short stay admission information recorded successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Admission)**

1. Admitting Clerk selects patient admission for short stay encounter.
2. System displays the list of appointment for short stay encounters.
3. Admitting Clerk reviews appointment details and requests system to create short stay encounter.
4. System asks user to enter encounter details such as patient stay details (floor, ward, room), admission type (such as “elective”), consulting physician, admitting diagnosis and emergency contact information (name, contact number).
5. Admitting Clerk enters the required information and submits it.
6. System successfully records short stay encounter information.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST405001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 31.02,AM 31.03, AM 31.04, AM 28.01




