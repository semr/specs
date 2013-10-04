#####Use Case ID: UC-PAS42
#####Use Case Name: Reschedule Admission

**Level:**                     User Level Goal

**Primary Actors:**            Clerk

**Stakeholders:**              Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to reschedule inpatient admission.

**Pre Condition:**             Clerk must be identified and authenticated.

**Post Condition:**            Inpatient admission rescheduled successfully.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Reschedule Admission)**

1. Clerk selects reschedule inpatient encounter option.
2. System displays the list of inpatient encounters.
3. Clerk selects an appropriate inpatient encounter.
4. System asks user to modify encounter appointment details such as time of service.
5. Clerk modifies the required details.
6. System reschedules an appointment for inpatient encounter.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid time for reschedule.
2. Physician not available for rescheduled date.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST402001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A




