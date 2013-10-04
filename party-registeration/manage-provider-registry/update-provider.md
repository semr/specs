#####Use Case ID: UC-PRS02
#####Use Case Name: Update Provider

**Level:**                     User Level Goal

**Primary Actors:**            Registration Clerk (RC)

**Stakeholders:**              Registration Clerk, Healthcare Provider

**Purpose:**                   The main intent of this use case is to update healthcare provider demographics.

**Pre Condition:**             RC must be identified and authenticated.

**Post Condition:**            Provider demographics will be updated in provider registry successfully.

**Frequency of Occurrence:**   High

__________________________________________________________
**Main Success Scenario: (Update Provider)**

1. RC requests to revise provider’s record.
2. System displays the list of providers available.
3. RC selects a provider’s record to revise.
4. System asks user to modify the specified provider’s demographic elements like contact and certification documentation.
5. RC modifies the fields of provider’s demographics and submits it.
6. System validates the fields and updates the provider’s record in provider registry.
  

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be entered.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Personnel Management):**

PRPM_ST304000UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 27.03

