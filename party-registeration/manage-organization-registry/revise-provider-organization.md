#####Use Case ID: UC-PRS08
#####Use Case Name: Revise Provider Organization

**Level:**                     User Level Goal

**Primary Actors:**            Clerk 

**Stakeholders:**              Clerk, Healthcare Organization

**Purpose:**                   The main intent of this use case is to update organization record in source (such as licensing and regulatory body) system.

**Pre Condition:**             Clerk must be identified and authenticated. 

**Post Condition:**            Provider organization will be revised in source system successfully.

**Frequency of Occurrence:**   Low
__________________________________________________________
**Main Success Scenario: (Revise Provider Organization)**

1. Clerk requests to send revise provider organization.
2. System asks for identifier of provider organization.
3. Clerk enters the organization identifier and submits it
4. System displays the organization info and asks user to modify it.
5. Clerk modifies the organization info such as contact information and submits it.
6. System validates the entered information and sends it to the JPORS (see glossary).
7. JPORS modifies the organization information and send confirmation message.
8. System acknowledges user about the confirmation.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be added.
2. Unable to connect licensing authority.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPM_ST406000UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
