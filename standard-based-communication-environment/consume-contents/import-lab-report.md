#####Use Case ID: UC-SCE02
#####Use Case Name: Import Lab Report

**Level:**                     User Level Goal

**Primary Actors:**            Content Consumer (Provider(Hospital Physician, Family Doctor), Patient, Pathologist) 

**Stakeholders:**              Patient, Provider

**Purpose:**                   The main intent of this use case is to import the lab report.

**Pre Condition:**             Content Creator must be identified and authenticated.  

**Post Condition:**            Laboratory Report is imported successfully without any conflicts.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Import Lab Report)**

1.	Content consumer generate request to import patient test reports by feeding following information;
  * Patient MRN
  * Patient Encounter Date or
  * Lab Test Order Identifier
  * Intended Lab Test(s)
2.	SCE receives request from the Request Generated Application and perform the following actions;
  * Validate the request according to conformance profile
  * Authenticate the requesting application as an authorized entity
  * Search for the requested report with feed criteria.
  * Pick the requested lab report and respond to application

**Alternate Flows** 


If the report is not prepared in the format such as FHIR Document or FHIR DocumentReference then the steps discussed in UC-SCE01 in alternate options a and b will be followed exactly.

_______________________________________________________________
**FHIR Information and Exchange, IHE Laboratory Technical Framework**

Content Integration Profile: Sharing Laboratory Reports (XD-LAB)
_______________________________________________________________

**Reference Models:**

1. **Reference HL7 RMIM (CDA): Level-1**

![11](https://f.cloud.github.com/assets/5012182/1418557/45d9ef3c-3fb8-11e3-9438-f22327ec5528.png)

2. **Reference HL7 RMIM (CDA): Level-2**

![12](https://f.cloud.github.com/assets/5012182/1418580/d57ed8a0-3fb8-11e3-9af7-6bdbf9cca628.png)

3	**Reference HL7 RMIM (CDA): Level-3**

![13](https://f.cloud.github.com/assets/5012182/1418589/08c70bb0-3fb9-11e3-94d0-3fbca7476b29.png)

_______________________________________________________________

**FHIR Reference Model: Document Resources**

![14](https://f.cloud.github.com/assets/5012182/1418603/7a054fda-3fb9-11e3-9b91-a0b37faf616e.PNG)
_______________________________________________________________

**Reference CDA Template:**

**Content Modules for CDA Header (Level 1)**

* DOCUMENT-LEVEL TEMPLATES **"Participants and Header Relationships(recordTarget)"**
* DOCUMENT-LEVEL TEMPLATES **"Participants and Header Relationships(intendedRecipient)"** 
* DOCUMENT-LEVEL TEMPLATES **"Participants and Header Relationships(participant)"** 
* DOCUMENT-LEVEL TEMPLATES **"Participants and Header Relationships(performer)"** 

_______________________________________________________________

**Content Modules for CDA Sections (Level 2)**

* SECTION-LEVEL TEMPLATES **"Laboratory Speciality Section template"**
* SECTION-LEVEL TEMPLATES **"Laboratory Report Item Section template "** 

_______________________________________________________________

**Content Modules for CDA Entries  (Level 3)**

* ENTRY-LEVEL TEMPLATES **"Laboratory Data Processing Entry template "**
* ENTRY-LEVEL TEMPLATES **"Specimen Collection template "** 
* ENTRY-LEVEL TEMPLATES **"Specimen Received template  "**
* ENTRY-LEVEL TEMPLATES **"Notification Organizer template"** 
* ENTRY-LEVEL TEMPLATES **"Notifiable Condition template  "** 
* ENTRY-LEVEL TEMPLATES **"Case Identifier template"**
* ENTRY-LEVEL TEMPLATES **"Outbreak Identifier template "** 
* ENTRY-LEVEL TEMPLATES **"Laboratory Isolate Organizer template"** 
* ENTRY-LEVEL TEMPLATES **"Laboratory Battery Organizer template"** 
* ENTRY-LEVEL TEMPLATES **"Laboratory Observation template "**
* ENTRY-LEVEL TEMPLATES **"Annotation Comment "** 

______________________________________________________________


**Reference OpenEHR Archetypes:**

N/A
