#####Use Case ID: UC-PAS64
#####Use Case Name: Reschedule Home Health Encounter

**Level:**                     User Level Goal

**Primary Actors:**            Provider Coordinator (PC)

**Stakeholders:**              Provider Coordinator, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to reschedule home health encounter.

**Pre Condition:**             Provider Coordinator must be identified and authenticated.

**Post Condition:**            Home Health encounter rescheduled appropriately.

**Frequency of Occurrence:**   Low(Occasionally)
__________________________________________________________
**Main Success Scenario: (Reschedule Home Health Encounter)**

1. PC selects reschedule home health encounter option.
2. System displays the list of home health encounters.
3. PC selects an appropriate home health encounter.
4. System asks user to modify encounter appointment details such as time of service.
5. PC modifies the required details.
6. System reschedules an appointment for home health encounter.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid time for reschedule.
2. Physician may not be available for rescheduled date.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST404001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
