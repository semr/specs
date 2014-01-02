#####Use Case ID: UC-AB07
#####Use Case Name: Post Patient Billing

**Level:**                     User Level Goal

**Primary Actors:**            Admitting Clerk (AC)

**Stakeholders:**              Admitting Clerk, Patient, Healthcare Provider, Insurance Agency

**Purpose:**                   The main intent of this use case is to post financial transactions against the billing accounts.

**Pre Condition:**             AC must be identified and authenticated.

**Post Condition:**            Financial transactions will be posted to patient’s billing account successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Post Patient Billing)**

1.	AC selects an option to post financial transaction to patient’s account.
2.	System displays list of available patient billing accounts.
3.	AC selects an appropriate billing account.
4.	System asks user to specify transaction details such as amount, account payer, reason, unit quantity, unit price etc  
5.	AC specifies the required details and submits it.
6.	System validates the information entered and posts financial transaction to the account. 

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Accounting & Billing):**

FIAB_ST000200UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
