#####Use Case ID: UC-OES12
#####Use Case Name: Create Stock Requisition Order

**Level:**                     User Level Goal

**Primary Actors:**            Surgeon, Clinician/Physician/Doctor

**Stakeholders:**              Order Entry User

**Purpose:**                   The main intent of this use case is to create new order stock requisition order.

**Pre Condition:**             User must be identified and authenticated.  

**Post Condition:**            Stock Requisition order created successfully.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Create Stock Requisition Order)**

1.	User (like physician, surgeon) selects manage stock requisition order option.
2.	User fills/selects in the following information:
    * Requisition Line Number 
    * Item Code ( Internal or External or both )
    * Hospital Item Code
    * Requisition Quantity
    * Requisition Measure of Unit
    * Dept. Cost Center ( It is valued as accounting code that identify the ordering department and this code can be used for charging for the Item ordered)
    * Item natural account code ( Account code of item for charging purpose )
    * Deliver to Id
    * Date Needed
3.	System will validate the entered information, will send stock requisition order to mentioned department (like warehouse, CentralSupply, Nursing floors, or Operating Room) and will set status of order active.
4.	Department system will receive order notification and will perform the following actions:
    * It will check the availability of ordered item.
    * If available, it will dispense the required item. 
    * It will notify the ordering user.
5.	System will perform following actions:
    * It will update the hospital inventory.
    * It will set order status to complete. 

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Location of manufacturer not responding.
2.	Request cannot be processed further.

**Alt-2:**

1.	Repeat step 1-3 from the main scenario.
2.	Department system will receive order notification and will perform the following actions:
    * It will check the availability of ordered item.
    * If Not Available, it will notify the ordering user about unavailability. 
3.	User after receiving notification will create non-stock requisition order.
4.	The steps of UC-OES16 create new non-stock requisition order will be executed.

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-

______________________________________________________________
**Reference Hl7 RMIM (Domain: Pharmacy):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

-NA-

_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

-NA-
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Section Level Template **"Medical Equipment Section (V2)"**

Entry Level Template **"Non-Medicinal Supply Activity"**

Entry Level Template **"Non-Medicinal Supply Activity (V2)"**

_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

-NA-
