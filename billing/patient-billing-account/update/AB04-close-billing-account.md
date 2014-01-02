#####Use Case ID: UC-AB04
#####Use Case Name: Close Billing Account

**Level:**                     User Level Goal

**Primary Actors:**            Admitting Clerk (AC)

**Stakeholders:**              Admitting Clerk, Patient, Healthcare Provider, Insurance Agency

**Purpose:**                   The main intent of this use case is to close patient’s billing account on the basis of inactivity for a specified amount of time.

**Pre Condition:**             AC must be identified and authenticated.

**Post Condition:**            Billing account will be closed successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Close Billing Account)**

1.	AC selects an option of closing billing account.
2.	System lists the available billing account and ask user to select a required one.
3.	AC selects an appropriate account.
4.	System displays account details as well as inactivity time span.
5.	AC changes the status of an account to “Closed”.
6.	System updates the billing account with updated status.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Accounting & Billing):**

FIAB_ST000100UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
