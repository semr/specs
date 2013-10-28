#####Use Case ID: UC-SCE01
#####Use Case Name: Create Lab Report

**Level:**                     User Level Goal

**Primary Actors:**            Content Creator (Physician/ Clinician, Nurse Practioner, Pathologist) 

**Stakeholders:**              Patient, Provider

**Purpose:**                   The main intent of this use case is the creation of laboratory report.

**Pre Condition:**             Content Creator must be identified and authenticated.  

**Post Condition:**            Laboratory Report is created successfully without any conflicts.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Create Lab Report)**

1.	Content Creator selects a particular test order from the list of orders.
2.	System shows the contents (lab results report(s)) included in the order.
3.	Content creator selects the one or more lab result reports to create final lab report
4.	System displays the selected lab result reports and provides the user with document sharing methodology options. 
  a.	FHIR Document
  b.	FHIR DocumentReference (CDA, Pdf, FHIR Document)

**Alternate Flows** 

**Alt-1: Create FHIR Document**

1.	FHIR Document Manager (FDM) Initiate new document creation.
2.	FHIR Document Composer (FDC) creates bundle resource with assigning FHIR Document resource as root.
3.	FDC load FHIR documents specs (e.g. xsd) and map all given data elements mentioned in specs. Such as;
  i.	document identifier
 ii.	doc version
 iii.	doc creation time
 iv.	doc author
 v.	...

4.	FDC map the attester information such as time of attestation and mode of attestation.
5.	FDC may add the event information for which the document was initiated. 
6.	Finally, it maps sections of the document according to requirement of profile for particular business case.
7.	FDM generate appropriate instance of document based on FDC structure and proceed for sending via REST end point.


**Alt-2: Create FHIR DocumentReference**

1.	FHIR Reference Document Manager (FRDM) Initiate new reference document creation i.e. CDA/Pdf/FHIR Document.
2.	FHIR Reference Document Composer (FRDC) creates bundle resource with assigning FHIR Reference Document resource as root.
3.	FRDC load FHIR reference documents specs (e.g. xsd) and map all given data elements mentioned in specs. Such as;
 i.	Ref document identifier
 ii.	Ref doc version
 iii.	Ref doc location
 iv.	Ref doc author
 v.	Ref doc custodian

4.  FRDC may add service type and address with parameters.
5.	FRDC may add the contextual information such as period and facility type. 

**Open Issues**

1. Change in requirement from FHIR perspective is an issue

**FHIR Information and Exchange, XDS Profile**

FHIR Resources: DocumentReference, Patient, Practioner, Organization
XDS Profile: Sharing Laboratory Reports (XD-LAB)
