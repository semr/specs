1. Module Scope
---------------

ABS covers the creation and management of patient billing accounts, primarily for the purpose of collecting charges and credits (financial transactions) to support the submission of a claim or invoice for reimbursement. A billing account will be associated with patient but it will be used for administrative purposes by the healthcare provider. ABS provides a consistent specification for accessing and managing billing repository, independent of the underlying technology stack. The following thematic areas are considered in scope for.

* **Patient Billing Account:** 
This is a set of functionality that provides the ability to manage patient billing accounts. Its functions include create a new billing account, updating and deleting an existing billing account, merging and unmerging accounts, closing inactive accounts and posting transaction into the selected account. These functions are generally protected and accessible by admitting clerk and patient with appropriate authorization.


2. Module Perspective
---------------------
ABS is a subsystem of the SEMR which provides functionality of creation and management of patient billing accounts.  In addition, the ABS has interfaces to the external systems such PAS (Patient Administration Service), Insurance Agency and ABS enabled applications. Any details of an external system are out of scope of this document. The figure below shows decomposition of ABS (Accounts and billing service) on the functionality areas and the supported external systems.

![proposed-architecture-for ABS](https://f.cloud.github.com/assets/5391320/1781332/ec2c8622-6891-11e3-90e5-b358d84cbc9d.png)

3. Module Functions 
-------------------
The ABS is intended to allow the creation and management of a wide variety of functions related patient’s billing accounts, including, but not limited to, creation, deletion, updating and closing a billing account. This includes merging two related accounts and unmerging an account if merged accounts found unrelated as well as posting of financial transactions against a billing account for	 all the billable charges. At the functional level, the service interface will explicitly allow the query, creation and modification of the different accounts.

4. User Classes and Characteristics 
-----------------------------------
Actors will use the billing service for different purposes. These different actors can be generalized into a basic ABS User an Actor that is simply an individual, organization, or application that requires access to content for some purpose. Specializations of the ABS User actor participate in additional operational specific scenarios. Actors described in this section are not necessarily human actors, but also include organizations and systems. Figure #3 outlines the specializations and composition of the different actors used in this specification. These actors are described below.

![abs-user-classes](https://f.cloud.github.com/assets/5391320/1781339/3b1d4d8e-6892-11e3-826a-c095b1cd9d0a.png)

The following actors take a role in the ABS actors:

| **Name**        | **Description**               | **Responsibilities**                                         |      
|-----------------|-------------------------------|--------------------------------------------------------------|
|**ABS Service**  |ABS Server Instance            |The ABS Service is a specific implementation of the ABS Server.
|**Admitting Clerk**|Primary Actor                |Admitting Clerk is an actor who is responsible for managing and accessing billing accounts as well as posting transitions to accounts.
|**Patient**      |Secondary Actor                |Users belonging to this category are responsible for accessing his/her billing account’s full details.  
|**Insurance  Agency**|Offstage Actor             |Insurance agency is an offstage actor who is interested in appropriate recording of billing information of relevant patients.

5. System Features
------------------
Following are the system features of the ABS:

![abs-use-case-diagram](https://f.cloud.github.com/assets/5391320/1781382/f467e79a-6892-11e3-9812-9afde3d69f59.png)

###Appendix A: Analysis Models                                                                                      
-----------------------
Following is the Accounting and Billing DMIM from Hl-7:

![abs-DMIM](https://f.cloud.github.com/assets/5391320/1781396/7aea1bf8-6893-11e3-9f01-0a349828c2e9.png)

**Description:** The Patient Billing Account domain model encompasses all messages in the FIAB domain. This includes the setup and management of accounts (e.g. patient billing accounts) and the posting of financial transactions against those accounts (e.g. lab charge).
 
Central to the domain model is the concept of an account, with attributes such as identifier, type (code), balance and the currency (e.g. US $) of the account. Associations to the account include patient identification (if the account is a patient billing account), insurance policy, encounter, and the optional specification of a guarantor for any outstanding balance in the account. 

A Billing Account is an accumulator of financial and administrative information for the main purpose of supporting claims and reimbursement. Secondarily, the billing account may contribute significant information to cost accounting and financial decision support systems. A billing account is simply that entity that captures the elements reflecting the cost and price of services provided and supplies consumed for a healthcare activity. The focus for which an account accumulates information will vary. (For example: In a realm where billing is based on periodically collecting financial transactions for a patient, the accumulator might be the patient.) A billing account might also include links to insurance and benefit information, and relevant responsible parties. 

Posting of charges is supplied through a financial transaction. In strictest accounting terms, the financial transaction would have a debit and credit association to 2 accounts (the debit account and the credit account). In this model, only 1 is specified, with a positive financial transaction amount used to add a charge, and a negative financial transaction amount used to negate (remove) a charge. The financial transaction is supported by a costing component (invoice element), which is further supported by the actual service that was performed or the product that was supplied (billable). To add to the balance of a patient billing account, the ActFinancialTransactionCode should be "CHRG" with a positive amount. To reduce this balance, the code would be "REV", again with a positive amount. 

