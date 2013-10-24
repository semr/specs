#####Use Case ID: UC-OES09
#####Use Case Name: Create Medication Order

**Level:**                     User Level Goal

**Primary Actors:**            Doctor/ Physician/ Clinician / Nurse/ Patient 

**Stakeholders:**              Order Entry User

**Purpose:**                   The main intent of this use case is to create new dietary order.

**Pre Condition:**             Doctor/ Physician/ Clinician / Nurse/ Patient must be identified and authenticated.   

**Post Condition:**            Dietary order created successfully.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Create Dietary Order)**

1.	User selects the new dietary order option and selects patient MRNO to retrieve patient’s data.
2.	System responds with the relevant data.
3.	User will prescribe the diet plan by filling/selecting the following information:
    * Type ( Diet, Supplement, Preference )
    * ServicePeriod (Example: Service1: breakfast, Service2: mid-morning snack, Service3: lunch etc )
    * DietTypeCode ( code for diet, supplement and preference )
    * Instructions ( diet instructions )
    * Diet Tray Order
    * Diet Tray Instructions
4.	System then performs the following actions:
    * Executes the dietary order.
    * Notifies the prescribed diet plan to patient and Nurse (in patient). 
    * Responds with dietary order ID. 

__________________________________________________________
**Alternate Flows** 

**Alt-1: Verbal Order**

1.	Repeat step 1 to 3 from the main scenario.
2.	Physician prescribes dietary order verbally and system records it.
3.	System identifies dietary keywords out of recorded order.
4.	Physician performs verification read back.
5.	The step 5 in main scenario of events is then executed.

**Alt-2: Co-Signature Configuration**

1.	Repeat step 1 to 4 from the main scenario.
2.	Physician configures the dietary order for verification from another physician.
3.	System notifies the physician who has to co-sign the order.
4.	Physician verifies and signs the dietary order.
5.	System responds back to initiating physician.
6.	The steps 6-8 in main scenario of events are then executed.

_______________________________________________________________
**Open Issues**

Verbal Language Support
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Dietary and Nutrition Order):**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Dietary and Nutrition Order):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

-NA-

_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

-NA-
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Section Level Template : **"Nutrition Section"**

______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

-NA-

