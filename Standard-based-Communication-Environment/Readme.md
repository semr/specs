1. Module Scope
---------------

As a health information exchange module of SEMR, SCE enables users to electronically exchange healthcare resources, messages and documents at a minimum; the product scopes discuss in this document cover laboratory report sharing. For document sharing, the intended infrastructure will base on direct push method to support exchange among labs, hospital and physician offices. The contents of the report will follow FHIR base document exchange. Furthermore, some of report may be exchanged as HL7 CDA.

2. Governance for sharing clinical document
---------------------
* **Document Format**
To enable interoperable transfer of document, agreement among communicating parties are needed to approve common format of document. Document can be unstructured such as PDF based patient summaries or more structured format such as CDA (Clinical Document Architecture) or FHIR based Document. The ultimate goal of this agreement is to ensure the receiving party should understand all semantics of the contents exchange.

* **Coding within document**
It enables to provide agreement on using common coding systems for exchanging structure documents. Specification for selecting and using common coding systems are described with detail in implementation guide of the structured document. Agreeing on common implementation guide for coding system is necessary to semantically understand the contents of documents.

* **Coding of Metadata**
It provides more aspects of the document during exchange. Most of the metadata is exchange as part of document exchange which self-describes the document intent. The metadata covers aspects of document such as identity, security, discovery, provenance, routing, privacy, authenticity and electronic pre-processing. 

3. Document sharing models
---------------------
* **Direct push**
Direct push model transfers the contents in form of documents along with associated metadata to intended known recipient. The document can also be delivered via some offline media. From IHE reference profile, IHE XDR and IHE XDM can best describe this model of document exchange.

![capture](https://f.cloud.github.com/assets/5012182/1417558/730ad614-3f91-11e3-95cf-920bc3631aaf.PNG)

* **Centralized discovery and retrieve**
A community of sharing partners agrees to use common infrastructure to publish, discover and exchange the document. This infrastructure allow document source to publish intended document to location accessible to all partners. The document consumer discovers the document location and pulls a copy of the intended document. 
An example of such model is IHE XDS affinity model which allow managing document via various stakeholders through common infrastructure.

![2](https://f.cloud.github.com/assets/5012182/1417584/e83bb10a-3f92-11e3-81eb-0332b48a8efb.PNG)

* **Federated discovery and retrieve**
This model allow document consumer to found the intended document by manual means or directory search and retrieve its contents. 
IHE XCA profile provides guidelines and specification for sharing document in federated way.

![3](https://f.cloud.github.com/assets/5012182/1417586/2a02a72e-3f93-11e3-8557-e50874ae825f.PNG)

3. Laboratory Domain
-------------------
According to the IHE content integration profile, “a laboratory report as an electronic document to be published towards a document sharing resource such as an Electronic Health Record (EHR) or in Personal Health Record (PHR) shared by a community of care providers. Such an electronic document contains the set of releasable results produced by a clinical laboratory or by a public health laboratory in fulfillment of one or more test Orders for a patient. The report is shared in a human-readable format. In addition, this electronic laboratory report SHALL contain test results in a machine-readable format, to facilitate the integration of these observations in the database of a consumer system. The major functionalities of this domain are as follows;



3. Module Functions 
-------------------
The SOE is intended to allow look up and management of wide variety of order entry components. This includes the ability to resolve content bound to a specific Concept Domain. At the functional level, SOE will allow the management of medication order, status of the order, dispensing medication order and administering medication order in case of in patient. The scope of this SOE covers support of multiple standards like CCHIT and HL7. Figure shows the level-1 DFD of order entry of medication.

![orderentry-dfd](https://f.cloud.github.com/assets/4283040/1224707/3c9a26ee-2753-11e3-9409-baf16f7de7d6.PNG)

| **Name**        | **Description**               |  
|-----------------|-------------------------------|
|**Prescribing System **| A system intended to support a clinician with prescribing authority.|
|**ePrescribingHub** | The CTS 2 Service is a specific implementation of the CTS 2 Terminology Server.|
|**Dispensing System** | A system intended to support a clinician with dispensing authority.|
|**Administration System** | A system intended to support a clinician in the recording or updating of medication administrations.
|**Drug Knowledge Base** | A system intended to provide information (knowledge) about medications including, but not limited to, monographs and drug-to-drug interactions.

4. User Classes and Characteristics 
-----------------------------------
Actors will use the order entry service for different purposes. These different actors can be generalized into a basic Order Entry User an Actor that is simply an individual, organization, or application that requires access to terminology content for some purpose. Specializations of the Order Entry User actor participate in additional operational specific scenarios. Actors described in this section are not necessarily human actors, but also include organizations and systems. Figure outlines the specializations and composition of the different actors used in this specification. These actors are described below.

![user-categories-of-oes](https://f.cloud.github.com/assets/4283040/1224758/b0393cc4-2754-11e3-81a7-e935d6606d36.PNG)

The following actors take a role in the Scheduling service actors:

| **Name**        | **Description**               | **Responsibilities**                                         |      
|-----------------|-------------------------------|--------------------------------------------------------------|
|**Order Entry User **| End User of Service| An order entry User is an actor such as pharmacist, doctor and Nurse. Terminology User activities include, new order, order dispensing, search/query order and order administration. Specializations of the Terminology User actor follow below.
|**SOE Service** | Order Entry Server| Responsible for delivering the order entry services
|**Doctor/ Physician/ Clinician** | End User of the Service| The Doctor is an actor responsible for creating new medication order, update medication order and creating prescription of the patient.
|**Pharmacist** | End User of the Service | The Pharmacist is the actor responsible for receiving the prescription, verification of prescription and dispensing of medications listed in prescription.
|**Nurse/ patient agent** | End User of the Service| A Nurse/Patient Agent is an actor responsible for administering the medication with specified dosage (in case of inpatient) and updating the data in SEO service.
|**Surgeon** | End User of the Service | The surgeon is an actor responsible for creating new non-medication order, update non-medication order for the operation purpose.

5. System Features
------------------
Following are the system features of the STS:

![system-features-oes](https://f.cloud.github.com/assets/4283040/1224826/66d2b1f8-2756-11e3-9cbc-fc70611697d3.png)
