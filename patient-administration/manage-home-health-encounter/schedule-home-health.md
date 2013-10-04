#####Use Case ID: UC-PAS63
#####Use Case Name: Schedule Home Health

**Level:**                     User Level Goal

**Primary Actors:**            Provider Coordinator (PC)

**Stakeholders:**              Provider Coordinator, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to schedule home health encounter.

**Pre Condition:**             Provider Coordinator must be identified and authenticated.

**Post Condition:**            Home Health encounter scheduled appropriately.

**Frequency of Occurrence:**   Low(Occasionally)
__________________________________________________________
**Main Success Scenario: (Schedule Home Health)**

1. PC selects schedule home health encounter option.
2. System asks user to specify patient.
3. Clerk selects appropriate patient information.
4. System ask user to enter home health encounter appointment details such as reason, physician and date of service.
5. PC specifies the required details.
6. System creates an appointment for home health encounter.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be added.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST404001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
