#####Use Case ID: UC-PAS31
#####Use Case Name: Schedule Admission

**Level:**                     User Level Goal

**Primary Actors:**            Clerk

**Stakeholders:**              Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to schedule admission.

**Pre Condition:**             Clerk must be identified and authenticated.

**Post Condition:**            Short stay encounter scheduled successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Schedule Admission)**

1. Clerk selects schedule short stay encounter option.
2. System asks user to specify patient.
3. Clerk selects appropriate patient information.
4. System ask user to enter encounter appointment details such as reason, physician and date of service.
5. Clerk specifies the required details.
6. System creates an appointment for short stay encounter.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be added.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST405001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

FN 03.01




