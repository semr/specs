#####Use Case ID: UC-AB02
#####Use Case Name: Update Billing Account

**Level:**                     User Level Goal

**Primary Actors:**            Admitting Clerk (AC)

**Stakeholders:**              Admitting Clerk, Patient, Healthcare Provider, Insurance Agency

**Purpose:**                   The main intent of this use case is to update patient’s billing account.

**Pre Condition:**             AC must be identified and authenticated.

**Post Condition:**            Billing account will be updated successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Update Billing Account)**

1.	AC requests to update patient’s billing account information.
2.	System displays the list the accounts available.
3.	AC selects an appropriate account for update.
4.	System asks user to modify the specified account’s information such as credit information, updated balance, guarantor role or updated account status.
5.	AC modifies the fields of account and submits it.
6.	System validates the fields and updates the patient’s billing account.

______________________________________________________________________________
**Alternate Flows**

**Alt-1:** 

1.	Invalid information cannot be entered.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Accounting & Billing):**

FIAB_ST000100UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
