#####Use Case ID: UC-OES14
#####Use Case Name: Create Non-Stock Requisition Order

**Level:**                     User Level Goal

**Primary Actors:**            Surgeon, Clinician/Physician/Doctor

**Stakeholders:**              Order Entry User

**Purpose:**                   The main intent of this use case is to create non-stock requisition order.

**Pre Condition:**             User must be identified and authenticated.  

**Post Condition:**            Non-Stock Requisition order created successfully.

**Frequency of Occurrence:**   Medium

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Create Non-Stock Requisition Order)**

1.	User (like physician, surgeon) selects manage stock requisition order option.
2.	User fills/selects in the following information:
    * Anticipated Price
    * Manufacturer Identifier
    * Manufacturer's Catalog
    * Vendor Id
    * Vendor Catalog
    * Taxable (Yes/No)
    * Substitute Allowed (Yes/No)
3.	System will validate the entered information, will send non-stock requisition order to manufacturer and will set status of order active.
4.	Manufacturer system will receive order notification, will dispense the required item and will notify the ordering system.
5.	System will perform following actions:
    * It will update the hospital’s inventory.
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



