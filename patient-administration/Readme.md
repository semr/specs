1. Module Scope
---------------

Patient Administration services represent functions necessary to manage, search, and access patient administration registry. Patient Administration services provide a consistent specification for accessing and managing patient administration registry, independent of the underlying technology stack. Patient Administration registry represents various resources including person’s demographics, patient demographics, patient encounters, service locations, entity state changes and encounter appointments. The following thematic areas are considered in scope for.

* **Person Demographics and Identificatio:** 
This is a set of functionality that provides the ability to manage person demographics as part of a patient administration service. Its functions include the ability to identify a person and record its demographics as well as verify the identification documents validity provided by the person. These functions are generally protected and accessible by registration clerk and medical record clerk with appropriate authorization.

* **Patient Demographics and Identification:**
This is a set of functionality that provides the ability to manage patient demographics as part of a patient administration service. The patient information model is not limited to persons; any type of living subject can be registered as a patient. Its functions include the ability to capture full information about the living subject playing the role of patient and patient identification using globally unique identifier. These functions are generally protected and accessible by registration clerk, receptionist and medical record clerk with appropriate authorization.

* **Patient Encounters:** 
This is a set of functionality that provides the ability to capture a whole lifecycle of patient encounter. From a patient administration perspective, this would include the maintaining different types of patient encounters such as ambulatory, inpatient, short stay and home health encounter. This would also include management service delivery location, attending practitioners and encounter organization as well as encounter location. These functions are generally protected and accessible by clerks, receptionist and provider coordinators with appropriate authorization.

* **Search / Query:** 
This is a set of functionality that provides the ability to find encounters history based on some search criteria. This includes search encounters by parameters such as encounter type, date of service, patient Id, encounter organization, attending practitioner and a time frame. These functions are generally protected and accessible by clerks, receptionist, provider coordinator and patient with appropriate authorization.

2. Module Perspective
---------------------

PAS (Patient Administeration) is a subsystem of the SEMR which provides functionality of management of person and patient demographics and visit information about patients.  In addition, the PAS has interfaces to the external systems such TS (Terminology Service), OES (Order entry service) and PAS enabled applications. Any details of an external system are out of scope of this document. The figure #1 shows decomposition of PAS on the functionality areas and the supported external systems.

![pas-architecture](https://f.cloud.github.com/assets/5391320/1220312/226d7c96-26d9-11e3-8c3e-64d34756b426.png)

3. Module Functions 
-------------------
The PAS is intended to allow the look up and management of a wide variety of patient administration components, including, but not limited to, person registry, patient registry, and patient encounters. This includes the ability to verify provided identification document validity, management of attending practitioner, updating encounter location and linking related inpatient encounters. At the functional level, the service interface will explicitly allow the query, creation and modification of the different patient administration components. The scope of this PAS covers support for multiple encounter types and globally unique identifiers for patient registry.

4. User Classes and Characteristics 
-----------------------------------
Actors will use the patient administration service for different purposes. These different actors can be generalized into a basic PAS User an Actor that is simply an individual, organization, or application that requires access to patient administration content for some purpose. Specializations of the PAS User actor participate in additional operational specific scenarios. Actors described in this section are not necessarily human actors, but also include organizations and systems. Figure #2 outlines the specializations and composition of the different actors used in this specification. These actors are described below.

![Figure-#2-User-Categories-of-PAS](https://f.cloud.github.com/assets/5391320/1220389/300f2f7e-26da-11e3-885e-d0648a422906.jpg)

The following actors take a role in the patient administration service actors:

| **Name**        | **Description**               | **Responsibilities**                                         |      
|-----------------|-------------------------------|--------------------------------------------------------------|
|**Clerk**        | End User of Service           |A Clerk is an actor who is responsible for accessing patient administration information and maintaining patient administration contents. Specializations of Clerk includes registration clerk, medical record clerk, data entry clerk, admitting clerk, nursing unit clerk and emergency room clerk.|
|**Registration Clerk**|End User of Service       |Users belonging to this category are responsible for registering person or patient and maintaining their demographics.|
|**Medical Record Clerk**|End User of Service     |The Medical Record Clerk is an actor who works in hospital’s medical record management office. Medical Record Clerk’s activities includes accessing data from patient administration registries and making sure that there is no inconsistent data exist in patient administration registries.
|**Data Entry Clerk**|End User of Service         |The Data Entry Clerks are responsible for maintaining information related to service delivery network.
|**Admitting Clerk**|End User of Service          |Admitting Clerks are responsible for maintaining patient admission information in case of short stay and inpatient encounters.
|**Nursing Unit Clerk**|End User of Service       |The Nursing Unit Clerk is an actor who is responsible for maintain patient’s discharge and post discharge information.
|**Emergency Room Clerk**|End User of Service     |The Emergency Room Clerk is an actor who is responsible for creating and maintaining emergency encounter from their start to completion.
|**Receptionist** |End User of Service            |Users of this category are responsible for querying information form patient administration registry and creating or maintaining ambulatory, inpatient and short stay encounter appointments. They are also responsible for maintaining ambulatory encounter information.
|**Discharge Coordinator**|End User of Service   |Users of this category are responsible for maintaining information related to inpatient discharge status such as “pending”.
|**Provider Coordinator**|End User of Service     |The Provider Coordinator is an actor who is responsible for creating and maintaining home health encounter appointments. 
|**Nurse**        |End User of Service            |Users belonging to this category of actors are responsible for maintaining information related to home health encounters from their start to their completion and also include abort home health encounter.
|**Patient**      |End User of Service            |The Patient is an actor who is responsible for accessing his/her medical history. He/She is also responsible for defining or maintaining level of confidentiality of his/her medical profile.
|**Physician**|Off Stage Actor                    |Physician is an off stage actor who is not responsible for adding value to the system but can get benefit from the system. 
|**Healthcare Provider**|Off Stage Actor          |The Healthcare Provider (Healthcare Organization or agency) is an off stage actor who has an interest in how well this system is functioning.

5. System Features
------------------
Following are the system features of the PAS:

![use-case-model-pas](https://f.cloud.github.com/assets/5391320/1220968/4375148a-26e3-11e3-8f38-bd61fc83b1d5.jpg)
