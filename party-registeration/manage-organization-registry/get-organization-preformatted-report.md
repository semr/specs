#####Use Case ID: UC-PRS15
#####Use Case Name: Get Organization Preformatted Report

**Level:**                     User Level Goal

**Primary Actors:**            Clerk 

**Stakeholders:**              Clerk, Provider, Provider Organization

**Purpose:**                   The main intent of this use case is to get print-ready organization report from the organization registry system (JPORS).

**Pre Condition:**             Clerk must be identified and authenticated. 

**Post Condition:**            Organization preformatted report will be accessed successfully.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Get Organization Preformatted Report)**

1. Clerk requests organization preformatted report or “Summary” report.
2. System asks user to enter filtering criteria such as demographic information (name, role, address).
3. Clerk specifies the filtering criteria.
4. System then sends the query with specified criteria and report identifier as being “Summary report” to the JPORS.
5. JPORS sends the acknowledgement that the query has been received and later that evening it sends the report.
6. System receives the report and sends a standard document transport message **Organization Report Query Response** containing the "Organization Summary" report as an attachment.


_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:Administrative Preformatted Report**

1. Clerk requests organization preformatted report or “Consumer Usage” report.
2. System asks user to enter filtering criteria such as demographic information (name, role, address).
3. Clerk specifies the filtering criteria and submits it.
4. System then sends the query with specified criteria and report identifier as being “Consumer Usage” report to the JPORS.
5. JPORS sends the acknowledgement that the query has been received and later that evening it sends the report.
6. System receives the report and sends a standard document transport message Organization **Administrative Report Query Response** containing the "Consumer Usage" report as an attachment.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPM_ST408000UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
