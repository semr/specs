#####Use Case ID: UC-PRS05
#####Use Case Name: Get Provider Preformatted Report

**Level:**                     User Level Goal

**Primary Actors:**            Clerk

**Stakeholders:**              Clerk, Provider

**Purpose:**                   The main intent of this use case is to get print-ready provider report from the provider registry system.

**Pre Condition:**             Clerk must be identified and authenticated.

**Post Condition:**            Provider preformatted report will be accessed successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Get Provider Preformatted Report)**

1. Clerk requests provider preformatted report or “Summary” report.
2. System asks user to enter filtering criteria such as demographic information (name, role, designation).
3. Clerk specifies the filtering criteria.
4. System displays the list of providers ordered by name.
5. Clerk selects the appropriate provider for summary report.
6. System creates the document and sends a standard document transport message **Provider Report Query Response** containing the "Provider Summary" report as an attachment.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:Administrative Preformatted Report**

1. Clerk requests provider desired preformatted report or “Consumer Usage” report.
2. System displays the list of all providers ordered by name.
3. Clerk selects the appropriate provider for summary report.
4. System creates the document and sends a standard document transport message **Administrative Report Query Response** containing the "Provider Summary" report as an attachment.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Personnel Management):**

PRPM_ST305100UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
