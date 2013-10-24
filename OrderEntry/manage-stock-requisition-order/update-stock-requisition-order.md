#####Use Case ID: UC-OES13
#####Use Case Name: Update Stock Requisition Order

**Level:**                     User Level Goal

**Primary Actors:**            Surgeon, Clinician/Physician/Doctor

**Stakeholders:**              Order Entry User

**Purpose:**                   The main intent of this use case is to update new order stock requisition order.

**Pre Condition:**             User must be identified and authenticated.  

**Post Condition:**            Stock Requisition order updated successfully.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Update Stock Requisition Order)**

1.	User selects update stock requisition order option and will specify the supply order id.
2.	System will respond with the details of stock requisition order.
3.	User will perform the required changes.
4.	System will validate the entered information, will send stock requisition order to mentioned department (like warehouse, CentralSupply, Nursing floors, or Operating Room) and will set status of order active.
5.	Department system will receive order notification and will perform the following actions:
    * It will check the availability of ordered item.
    * If available, it will dispense the required item. 
    * It will notify the ordering user.
6.	System will perform following actions:
    * It will update the hospital inventory.
    * It will set order status to complete. 

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
