1. Module Scope
---------------

Order Entry enables a user to electronically record, store, retrieve, and manage orders at a minimum, Following are order types:
1. Medications;
2. Laboratory;
3. Radiology/imaging; and
4. Provider referrals
Order Entry content represents various resources including medication list, diagnosis, order type, problem list, order target, order specimen, route of administration, order priority, taxonomies and formal description logic based on ontologies. The following thematic areas are considered in scope for SOES.

* **Medication Order:** 
This is a set of functionality that provides the ability to manage content as part of an order entry. Medication order functions include the ability to create new order, update order and manage interaction checking alerts. These functions are generally protected and accessible by the authorized users like doctors, physicians and clinician.

* **Medication Dispensing:** 
This is a set of functionality that provides the ability to manage dispensing of medication in order entry. Dispensing functions include the ability to verify prescription, check status of medication and dispense medicine. These functions are generally protected and accessible by the authorized users like pharmacist.

* **Medication Administration:**
This is a set of functionality that provides the ability to manage the administration of medication as a part of an order entry. Administration functions include the ability to calculate dosage based on weight, check for duplicate or missed medication. These functions are generally protected and accessible by the authorized users like patient agent and nurses.

* **Search / Query:**
This is a set of functionality that provides the ability to find orders based on some search criteria. This includes restrictions to specific associations or other attributes of the order, including navigation of associations for result sets. 

2. Module Perspective
---------------------
Computerized order entry is the process of entering medication, radiology, lab orders or other physician instructions electronically instead of on paper charts. The use of an Order entry system helps in reducing number of errors related to poor handwriting or transcription of medication orders.  Order Entry systems are often used in tandem with e-prescribing systems, which alert physicians and clinicians to a particular patient’s drug allergies and current medications. Structured orders provide the semantics of the concepts being conveyed in an electronic message or record. Experience shows that in order to share content, a hub and spokes model forcing order entry consumers to use a common hub is more intrusive for users and introduces adoption barriers, especially in distributed environments. This system has the aim to overcome such barriers by a separation of behavior (software functionality) from content (the deployed order entry module). 

![orderentry-arch](https://f.cloud.github.com/assets/4283040/1224699/e42daab2-2752-11e3-9535-50a3b2bc3bf1.PNG)

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
