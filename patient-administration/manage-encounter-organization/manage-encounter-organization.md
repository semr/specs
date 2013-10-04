#####Use Case ID: UC-PAS75
#####Use Case Name: Manage Encounter Organization

**Level:**                     User Level Goal

**Primary Actors:**            Clerk

**Stakeholders:**              Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to change or cancel change request for encounter organization during an encounter.

**Pre Condition:**             Clerk must be identified and authenticated.

**Post Condition:**            System will record the change of encounter organization.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Change Responsible Organization)**

1. Clerk requests to change responsible organization.
2. System displays the list of available organizations for encounter.
3. Clerk selects appropriate organization as a replacement of current organization.
4. System changes the organization holding clinical responsibility during an encounter.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:Cancel Responsible Organization Change**

1. Clerk selects cancel responsible organization change option.
2. System displays the list of change responsible organization actions.
3. Clerk selects appropriate change responsible organization action.
4. System reverses the change in responsible organization.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST303011UV02, PRPA_ST303012UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
