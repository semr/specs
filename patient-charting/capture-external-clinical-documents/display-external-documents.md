#####Use Case ID: UC-PCS65
####Use Case Name: Display External Document

**Level:**                     User Level Goal

**Primary Actors:**            Doctor/ Physician/ Clinician 

**Stakeholders:**              Patient Charting User

**Purpose:**                   The main intent of this use case is to display documents external documents.

**Pre Condition:**             Doctor/ Physician/ Clinician must be identified and authenticated.  

**Post Condition:**            External document displayed successfully. 

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Display Scanned Documents)**

1.	Physician selects the display scanned document option.
2.	System will respond with the list of indexed scanned documents.
3.	Physician will select the document from the list.
4.	System will display the selected scanned document labeled and date-time stamped.

__________________________________________________________
**Alternate Flows** 

1.	In-valid location
2.	Request cannot be processed

**Alt-1: Display Text-Base Reports**

1.	Physician selects the display text-based reports option.
2.	System will respond with the list of text-based reports.
3.	Physician will select the report from the list.
4.	System will display the selected report in structured way.

**Alt-2: Display CDA Documents**

1.	Physician selects the display CDA documents option.
2.	System will respond with the list of CDA documents.
3.	Physician will select the document from the list.
4.	System will display the selected document in a structured way.

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Pharmacy):**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 09.05.01, AM 09.01, AM 09.03, AM 09.04 
_______________________________________________________________
**EHR Functional Criteria:**

DC.1.1.3.1 

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Pharmacy):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

-NA-

_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![image](https://f.cloud.github.com/assets/4283040/1387825/68a4fc50-3ba8-11e3-8e9e-3c9b8ab3860f.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Document Level Template 

1. Care Plan
2. Consultation Note
3. Continuity of Care Document
4. Diagnostic Imaging Report
5. Discharge Summary
6. Operative Note
7. Procedure Note
8. Referral Note
9. Progress Note

_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

Procedure (openEhr Archetype)

-NA-
