#####Use Case ID: UC-PAS73
#####Use Case Name: Manage Attending Practitioner

**Level:**                     User Level Goal

**Primary Actors:**            Clerk

**Stakeholders:**              Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to change or cancel change request for attending practitioner during an encounter.

**Pre Condition:**             Clerk must be identified and authenticated. 

**Post Condition:**            System will record the change of attending practitioner.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Change Attending Practitioner)**

1. Clerk requests to change attending practitioner.
2. System displays the list of available practitioners.
3. Clerk selects appropriate practitioner as a replacement.
4. System changes the attending practitioner and records the total time interval previous
practitioner gave to patient.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:Cancel Attending Practitioner Change**

1. Clerk selects cancel attending practitioner change option.
2. System displays the list of change attending practitioner actions.
3. Clerk selects appropriate change attending practitioner action.
4. System reverses the change in attending practitioner.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST301011UV02, PRPA_ST301012UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
