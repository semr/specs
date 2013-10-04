#####Use Case ID: UC-OES15
#####Use Case Name: Update Non-Stock Requisition Order

**Level:**                     User Level Goal

**Primary Actors:**            Surgeon, Clinician/Physician/Doctor

**Stakeholders:**              Order Entry User

**Purpose:**                   The main intent of this use case is to update non-stock requisition order.

**Pre Condition:**             User must be identified and authenticated. Order can be only updateable (for cancel) before items dispatched. 

**Post Condition:**            Non-Stock Requisition order updated successfully.

**Frequency of Occurrence:**   Medium

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Update Non-Stock Requisition Order)**

1.	User (like physician, surgeon) selects update non-stock requisition order option and will specify the supply order id.
2.	System will respond with the details of stock requisition order.
3.	User will perform the required changes.
4.	System will validate the entered information, will send non-stock requisition order to manufacturer and will set status of order active.
5.	Manufacturer system will receive order notification, will dispense the required item and will notify the ordering system.
6.	System will perform following actions:
    * It will update the hospital’s inventory.
7.	It will set order status to complete.

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-
