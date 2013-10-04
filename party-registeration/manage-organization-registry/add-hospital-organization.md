#####Use Case ID: UC-PRS10
#####Use Case Name: Add Hospital Organization

**Level:**                     User Level Goal

**Primary Actors:**            Clerk

**Stakeholders:**              Clerk, Provider, Provider Organization

**Purpose:**                   The main intent of this use case is to add hospital organization within a hospital where the organization information is maintained in a central system.

**Pre Condition:**             Clerk must be identified and authenticated. 

**Post Condition:**            Organization will be added to internal central system successfully.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Add Hospital Organization)**

1. Clerk selects add hospital organization option.
2. System asks to enter the organization details such as name, description and role.
3. Clerk enters the required information and submits it.
4. System then perform the following actions:
  * Validates the organization details.
  * Records organization details in an internal central system.
  * Notifies the heads of organization about organization being added.


_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be added.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPM_ST403000UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

IP 02.02
