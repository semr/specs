#####Use Case ID: UC-PRS09
#####Use Case Name: Get Provider Organization

**Level:**                     User Level Goal

**Primary Actors:**            Clerk (RC)

**Stakeholders:**              Clerk, Healthcare Organization

**Purpose:**                  The main intent of this use case is to retrieve all registry information about an organization. Details for multiple organizations can retrieved with one query request.

**Pre Condition:**             Clerk must be identified and authenticated. 

**Post Condition:**            Organization details will be retrieved successfully.

**Frequency of Occurrence:**   Low
__________________________________________________________
**Main Success Scenario: (Get Provider Organization)**

1. MRC requests to send “get provider organization” request to JPORS
2. System asks for filtering criteria such as time interval.
3. Clerk enters the criteria and submits it.
4. System sends a request with filtering criteria to JPORS.
5. JPORS returns the list of provider organizations.
6. System displays the list of provider organizations.
7. Clerk selects an appropriate organization for details.
8. System displays the full details of provider organization.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPM_ST407000UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
