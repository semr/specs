#####Use Case ID: UC-AB05
#####Use Case Name: Merge Billing Accounts

**Level:**                     User Level Goal

**Primary Actors:**            Admitting Clerk (AC)

**Stakeholders:**              Admitting Clerk, Patient, Healthcare Provider, Insurance Agency

**Purpose:**                   The main intent of this use case is to merge two related billing accounts. Note that once charges for an encounter have been posted to an account, that account can no longer be merged to an account created for a continuation of that encounter.

**Pre Condition:**             AC must be identified and authenticated.

**Post Condition:**            Billing accounts will be merged successfully.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Merge Billing Account)**

1.	AC selects merge billing accounts option.
2.	System displays the list of available patient’s billing account. 
3.	AC selects two appropriate billing accounts for merging.
4.	System merges the two accounts.


________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Accounting & Billing):**

FIAB_ST000100UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
