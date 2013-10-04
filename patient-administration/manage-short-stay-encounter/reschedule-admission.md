#####Use Case ID: UC-PAS32
#####Use Case Name: Reschedule Admission

**Level:**                     User Level Goal

**Primary Actors:**            Clerk

**Stakeholders:**              Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to reschedule admission.

**Pre Condition:**             Clerk must be identified and authenticated.

**Post Condition:**            Short stay encounter rescheduled successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Reschedule Admission)**

1. Clerk selects reschedule short stay encounter option.
2. System displays the list of short stay encounters.
3. Clerk selects appropriate an appropriate short stay encounter.
4. System ask user to modify encounter appointment details such time of service.
5. Clerk modifies the required details.
6. System reschedules an appointment for short stay encounter.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid time for reschedule.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST405001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A




