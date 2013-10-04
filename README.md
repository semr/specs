System Modules:
==============

The proposed architecture is based on Service Oriented Architecture (SOA). The main functionalities and features of the system are provided as services. The adoption of SOA approach makes a base for deploying EMR system as services on cloud servers. The architecture is divided into three layers of services, i.e., Data Services, Business Services and Application Interface Services (see Figure 3). The Data layer is responsible for managing the storage and retrieval of medical information, demographics and related metadata. The EMR functionalities, including some supporting features, are provided by the Business layer. The top most Application Interface layer generates messages and reports and provides interfaces for data entry to the system. 


![alt text](https://f.cloud.github.com/assets/5391320/1217482/55293214-26a8-11e3-997a-8536abf010df.png "Architecture Diagram")

Business Logic or Service Layer
-------------------------------
The business logic layer will contain all business use cases or functionalities provided by the SEMR. Following are the components that will be covered in business layer: 


###1.	Terminology Service

This component of the proposed system will provide user with interface to bind clinical terms with clinical data. Its functions will include create, maintain, localize and map terminologies. It will also include mapping terminology elements between different components as well as applications. 

###2.	Device Integration

This component include functionality to integrate external medical devices (such as Urine analyzer, blood analyzer, digital X-ray supporting DICOM protocol and Cannon RKFI auto refract keratometer) to the system. It will automate the process of entering results into an MIS instead of manually reading them from a printed paper or from the machine display. 

###3.	Patient Administration

This will cover all the administrative workflows of a hospital from patient registration to his/her discharge. Its functions include patient registration, capturing patient identification documents, recording encounter lifecycles, linking related encounters, managing changes during encounter and storing patient demographics.

###4.	Personnel Management

This component will provide user with the facility to register, access and maintain personnel and organization registries. It will also include managing physician groups and internal organizations of a healthcare facility.

###5.	Patient Charting

Patient charting component is one of integral part of SEMR. It contains the complete medical record of a patient (patient chart). It starts right after patient enters (check in) into the healthcare facility and ends at patient discharge. From start till end, it records everything in the patient medical record, including problem list, allergies, immunizations, vital signs, progress notes discharge notes, medications, patient encounter history, family history, clinical documents (such as lab reports), consents and authorizations, referrals, procedures, guidelines and alerts. 

###6.	Order Entry

Order Entry module is responsible for managing the orders such as medication and non medication order of particular patient. Its functions include creating new order, update order, delete order and manage status of order. It will provide an interface to communicate with pharmacy system.

###7.	 Lab Order

This component of the proposed system will enable user to electronically record, store, retrieve and manage Lab test orders.

###8.	EHR Extract

The EHR Extraction is used to communicate with other health information systems or EHR repository. This component will convert the data stored in SEMR repository into an EHR Extract of EN13606. The EHR Extract generated can then be communicated with other HIS or can be stored in a regional EHR repository. 
The components will also follow the openEHR methodology of using predefined archetypes for order entry, results and EHR extracts. In cases, we don't have required archetypes available; they will be designed and created at that time. 

###9.	Scheduling 

This component will allow the look up and management of a wide variety of appointment types, including, but not limited to, outpatient appointments, inpatient appointments, and short stay appointments. This includes procedures, observations, food and transportation service appointments as well.

###10.	Medical Billing

his component will record all financial activities of the SEMR. Billing will get the input data from order entry and lab order components. The system will enable the patient to deposit advance payments which can be withdrawn according to the service used. The payment system is linked with the database to store the records of transactions. 

###11.	Practitioner Collaboration 

This component covers business scenarios involved in inter-professional collaboration. It includes two types of collaboration; a) Practitioner-Physician collaboration where it covers communication between nurse practitioner. b) Physician-Physician collaboration where it covers the junior physician communication with senior physician in order to ensure good care.

###12.	Hl7 Messaging

This component of the proposed system will provide user with the facility to generate and parse HL7 messages for communicating clinical data with other healthcare systems. 
This component will take care of all the security issues in the system and will provide access control to the different parts and components
