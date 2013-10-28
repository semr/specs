1. Module Scope
---------------

As a health information exchange module of SEMR, SCE enables users to electronically exchange healthcare resources, messages and documents at a minimum; the product scopes discuss in this document cover laboratory report sharing. For document sharing, the intended infrastructure will base on direct push method to support exchange among labs, hospital and physician offices. The contents of the report will follow FHIR base document exchange. Furthermore, some of report may be exchanged as HL7 CDA.

2. Module Perspective
---------------

SCE is component of SEMR that holds the sharable contents. Sharable contents include laboratory reports, discharge summaries and all sort of other clinical documents that are required by different stakeholders to consume for different purpose. The utilization of shared information may be at different times i.e. the Content Creation System generates the sharable information during the stage of patient discharge and saves to the SCE in shared repository. Later at some times, the Content Consuming System utilizes that information by requesting from SCE. 

![5](https://f.cloud.github.com/assets/5012182/1417636/52004180-3f95-11e3-8570-aa52177782e3.PNG)

3. Module Functions 
-------------------
The SCE is intended to get clinical documents from the Content Creation System (source system) and store in shared repository. Content Creation System includes systems; hospital information system, laboratory information system and practioner office system. Content Consuming System receives the clinical documents from SCE. Content Consuming System includes systems; care provider and personal health record.

![6](https://f.cloud.github.com/assets/5012182/1417639/853fb5ee-3f95-11e3-9d05-b4f6a3f94f2a.PNG)

|                 |  **Name**     | **Description**        |                        | 
|-----------------|---------------| -----------------------| -----------------------| 
| **Content Creation System ** | **Hospital Information System** | A system intended to support patient medical record (EMR) and is operating in hospital vicinity. | All these systems are intended to support the functionality of;	* creating sharable contents * storing the contents to the sharable repository of SCE component |
|  | **Laboratory Information System** | A system intended to support functions of laboratory report (test results) creation.  |
|  | **Practitioner Office System**| A system intended to support a clinician with basic information of patient health record.|
|**SCE** | **Communication Interface** | A system component that can receive the information from Content Creation System and send the information to Content Consuming System.| SCE is the information exchange infrastructure with the functions to hold and communicate the sharable contents between Content Creation System and Content Consuming System.| 
|| **Share Repository** | A system component intended to hold the sharable contents. | 
| **Content Consuming System** | **Care Provider Setting** | A system where care providers (physicians) are provided with the access to consume the sharable contents | Content Consuming System covers the systems with the patient information to provide to SCE pulling the sharable contents. | 
|| **Personal Health Record (PHR)** | A system intended to use by patients themselves with the functionality to use the sharable contents |
|| **Laboratory Information System** | 	Laboratory Information System	A system intended to support laboratory functions of collecting test order and specimens. |

4. User Classes and Characteristics 
-----------------------------------
The main actors involved in this system are Content Creator and Content Consumer that interact with SCE Service actor.  Further Specializations of Content Actor include hospital physician, doctor, clinician and nurse. While specializations of Content Consumer include patient, family doctor of a patient and hospital physician/doctor.
Content (i.e. a laboratory report) is created by a Content Creator and is to be consumed by a Content Consumer. 
These two actors are further specialized into different actors as shown below:

![7](https://f.cloud.github.com/assets/5012182/1417797/6adb015a-3f9e-11e3-8f8b-89d9259e3a32.PNG)

| **Name**        | **Description**               | **Responsibilities**                                         |      
|-----------------|-------------------------------|--------------------------------------------------------------|
|**Content Creator **| Creator of the laboratory documents and messages | An application responsible for the creation of content and transmission to a Content Consumer. This actor issues laboratory reports for sharing purpose.
|**SCE Service** | Standard based Communication Service | Responsible for receiving and sending the messages and documents.
|**Content Consumer** | Consumer of the messages and documents. | An application responsible for viewing, importing, or other processing of content created by a Content Creator Actor. 

6. Governance for sharing clinical document
---------------------
* **Document Format**
To enable interoperable transfer of document, agreement among communicating parties are needed to approve common format of document. Document can be unstructured such as PDF based patient summaries or more structured format such as CDA (Clinical Document Architecture) or FHIR based Document. The ultimate goal of this agreement is to ensure the receiving party should understand all semantics of the contents exchange.

* **Coding within document**
It enables to provide agreement on using common coding systems for exchanging structure documents. Specification for selecting and using common coding systems are described with detail in implementation guide of the structured document. Agreeing on common implementation guide for coding system is necessary to semantically understand the contents of documents.

* **Coding of Metadata**
It provides more aspects of the document during exchange. Most of the metadata is exchange as part of document exchange which self-describes the document intent. The metadata covers aspects of document such as identity, security, discovery, provenance, routing, privacy, authenticity and electronic pre-processing. 

7. Document sharing models
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

8. Laboratory Domain
-------------------
According to the IHE content integration profile, “a laboratory report as an electronic document to be published towards a document sharing resource such as an Electronic Health Record (EHR) or in Personal Health Record (PHR) shared by a community of care providers. Such an electronic document contains the set of releasable results produced by a clinical laboratory or by a public health laboratory in fulfillment of one or more test Orders for a patient. The report is shared in a human-readable format. In addition, this electronic laboratory report SHALL contain test results in a machine-readable format, to facilitate the integration of these observations in the database of a consumer system. The major functionalities of this domain are as follows;

* **Laboratory Report Exchange**
This is a set of functionality that provides the ability to exchange laboratory report between Content Creation System (source) and Content Consuming System (destination). Content Creation System is a system that generates the laboratory reports and save them in SCE. It can be a hospital, laboratory or practioner office. Content Consuming System is a system that uses the laboratory reports. It can be a Care Provider or PHR.
 
![4](https://f.cloud.github.com/assets/5012182/1417628/e30668cc-3f94-11e3-95a3-22976577082e.PNG)

* **Laboratory Report Contents**
With perspective of governance of sharing laboratory report, it is necessary to agree upon some common format of the contents of sharable report and align requirements to appropriate use cases. XD-LAB [1-2]  is IHE content integration profile that suggests detail use cases with definition of detail contents of report to be shared among different documents intended applications such as EHR, PHR and other healthcare systems. The intended document contains the set of releasable results produced by a clinical laboratory or by a public health laboratory in fulfillment of one or more test Orders for a patient.

9. System Features
------------------

![8](https://f.cloud.github.com/assets/5012182/1417874/4dd2e1a2-3fa0-11e3-819e-1519edc4a79a.PNG)
