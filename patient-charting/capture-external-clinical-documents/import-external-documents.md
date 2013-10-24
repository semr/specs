#####Use Case ID: UC-PCS64
####Use Case Name: Import External Document

**Level:**                     User Level Goal

**Primary Actors:**            Doctor/ Physician/ Clinician 

**Stakeholders:**              Patient Charting User

**Purpose:**                   The main intent of this use case is to import documents from external sources.

**Pre Condition:**             Doctor/ Physician/ Clinician must be identified and authenticated.  

**Post Condition:**            Documents imported successfully.   

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Import Scanned Documents)**

1.	Physician selects the import scanned document option and will specify the location.
2.	System will perform following actions:
    * It will fetch scanned document from the mentioned source.
    * It will attach label to image.
    * It will index the scanned image along with date.
    * It will record the time stamp of the imported document.
3.	Physician will save the imported document.
4.	System will save it in the particular patient record.

__________________________________________________________
**Alternate Flows** 

1.	In-valid location
2.	Request cannot be processed

**Alt-1: Import Text Base Reports**

1.	Physician selects the import text-based reports option and will specify the location.
2.	System will perform following actions:
    * It will fetch the reports from the mentioned source.
    * It will attach label to the text-based report.
    * It will record the time stamp of the imported document.
3.	Physician will save the imported text-based report.
4.	System will save it in the particular patient record.

**Alt-2: Import CDA Documents**

1.	Physician selects the import CDA documents option and will specify the location.
2.	System will perform following actions:
    * It will fetch the documents from the mentioned source.
    * It will record the time stamp of the imported document.
3.	Physician will save the imported CDA document.
4.	System will save it in the particular patient record.

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
