#####Use Case ID: UC-PAS16
#####Use Case Name: Revise Service Delivery Location

**Level:**                     User Level Goal

**Primary Actors:**            Data Entry Clerk(DEC)

**Stakeholders:**              Data Entry Clerk(DEO), Patient , Healthcare Providers

**Purpose:**                   The main intent of this use case is to revise service delivery locations.

**Pre Condition:**             Data Entry Clerk must be identified and authenticated.

**Post Condition:**            Service Delivery locations will be revised successfully.

**Frequency of Occurrence:**   Low(Occasionally)
__________________________________________________________
**Main Success Scenario: (Revise Service Delivery Location)**

1. DEC requests to revise service delivery location’s record.
2. System displays the list of service delivery location s available.
3. DEC selects a service delivery location’s record to revise.
4. System asks user to modify the specified location’s metadata elements like name, description, zip code, type and status code.
5. DEC modifies the fields of service delivery location and submits it.
6. System validates the fields and updates the service delivery location’s record in location registry.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be added.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST202302UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

IP 01.02




