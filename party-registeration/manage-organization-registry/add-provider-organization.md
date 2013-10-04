#####Use Case ID: UC-PRS07
#####Use Case Name: Add Provider Organization

**Level:**                     User Level Goal

**Primary Actors:**            Clerk 

**Stakeholders:**              Clerk, Provider Organization

**Purpose:**                   The main intent of this use case is to send add provider organization request to register organization to a source (such licensing or regulatory body) system.

**Pre Condition:**             Clerk must be identified and authenticated. 

**Post Condition:**            Provider organization will be added to licensing body successfully.

**Frequency of Occurrence:**   Low
__________________________________________________________
**Main Success Scenario: (Add Provider Organization)**

1. Clerk selects to send add provider organization request option.
2. System asks user to enter provider organization details name, description, address, contact info and role.
3. Clerk enters the organization detail.
4. System adds identifiers (organization id, role id, work location id) to the organization details and sends the add organization request to a licensing body (such as College of Pharmacists) with entered details.
5. Source system responses with confirmation message.
6. System acknowledges that organization is added successfully.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be added.
2. Unable to connect licensing authority.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPM_ST405000UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
