1. Module Scope
---------------

Patient charting services represent functions necessary to manage, search, and access patient chart registry. Patient charting services provide a consistent specification for accessing and managing patient chart registry, independent of the underlying technology stack. Patient chart registry represents various resources including problem list, allergy list, immunization list, vital signs, clinical notes, clinical guidelines and external documents. Problem oriented approach is adopted for patient charts and the data will be entered in a chart using SOAP (subjective, objective, assessment and plan) format. The following thematic areas are considered in scope according to different phases in SOAP:

* **Subjective:**
This is a set of functionality that provides the ability to manage patient’s condition in narrative form as part of a patient charting service. In simple words, in this phase patient is telling his/her story such as disease symptoms, diet problems and other history. Its functions include the ability to manage problem/diagnosis list, allergy list and immunization list as well as ability to access patient history and his/her family history. These functions are generally protected and accessible by physician and patient with appropriate authorization.

* **Objective:** 
This is a set of functionality that provides the ability to manage data based on objective and traceable observations (such as skin, hair, nails, heart, lungs etc) as part of a patient charting service. The observations are based on actual physical exams such pathology results, MRIs and other test results conducted to identify cause of problem. Its functions include the ability to managing and accessing vital signs as well as calculating BMI and providing time based graphs of height and weight. These functions are generally protected and accessible by physician and patient with appropriate authorization.

* **Assessment:**
This is a set of functionality that provides the ability to manage physician’s medical diagnoses for the medical visit as part of a patient charting service. Its functions include the ability to manage both structured and unstructured (free-text) clinical notes and manage clinical notes templates. Physicians derive assessment of the problem based on patient history (Subjective) and resulting observations from actual reports (Objective). These functions are generally protected and accessible by physician, nurse, assistant and patient with appropriate authorization.

* **Plan:**
This is a set of functionality that provides the ability to manage detail plan of actions for a patient. From a patient charting perspective, this would include creating and accessing guidelines for disease management, wellness and preventive service, presenting alerts based on clinical guidelines, documenting preventive service will be performed, sending patient referral to target clinician, managing medication list, capture external clinical documents, managing consents, authorizations and managing procedure instructions. These functions are generally protected and accessible by physician, domain expert, healthcare provider and patient with appropriate authorization.

* **Search / Query:**
This is a set of functionality that provides the ability to find various patient resources. This includes search clinical documents, patient history, alerts, guideline, instruction and note template by parameters. These functions are generally protected and accessible by assistant, physician, domain expert and patient with appropriate authorization.

2. Module Perspective
---------------------
SPCS is a subsystem of the SEMR which provides functionality of managing and accessing patient charts.  In addition, the SPCS has interfaces to the external systems such as STS (Semantic based terminology Service), SOES (Semantic based order entry service), SPAS (Semantic based patient administration system), and SPC enabled applications. Any details of an external system are out of scope of this document. The figure #1 shows decomposition of SPCS on the functionality areas and the supported external systems.

![patientcharting-arch](https://f.cloud.github.com/assets/4283040/1242986/2d6ac170-2a59-11e3-8efd-a77e289a2f20.PNG)

3. Module Functions 
-------------------
The SPCS is intended to allow the access, display and management of a wide variety of patient charting components, including, but not limited to, problem/diagnosis list, allergy list, immunization list, medication list, vital signs and clinical notes. This includes the ability to manage clinical note templates, make referral to other clinicians, capture external clinical documents, manage consent and authorization documents and presenting alerts. At the functional level, the service interface will explicitly allow the query, creation and modification of the different patient charting components. The scope of this SPCS covers support for adding comments to clinical notes by the patient or patient representatives, managing clinical guidelines and managing alert criteria on top of these clinical guidelines. 


4. User Classes and Characteristics 
-----------------------------------
Actors will use the patient charting service for different purposes. These different actors can be generalized into a basic SPC User an Actor that is simply an individual, organization, or application that requires access to patient charting content for some purpose. Specializations of the SPA User actor participate in additional operational specific scenarios. Actors described in this section are not necessarily human actors, but also include organizations and systems. Figure outlines the specializations and composition of the different actors used in this specification. These actors are described below.

![image](https://f.cloud.github.com/assets/4283040/1242990/592b4028-2a59-11e3-971c-ecff1eea733e.png)

The following actors take a role in the Scheduling service actors:

| **Name**        | **Description**               | **Responsibilities**                                         |      
|-----------------|-------------------------------|--------------------------------------------------------------|
|**SPC Service**| End User of Service| The SPC Service is a specific implementation of the SPC Server.
|**Physician** | End User of Service| A Physician is an actor who is responsible for accessing patient charting information and maintaining patient charting various contents such as medication list, problem list, vital signs, immunization list, referrals and clinical notes. 
|**Patient** | End User of the Service| Users belonging to this category are responsible for accessing his/her patient chart and adding comments on clinical notes.
|**Assistant** | End User of the Service | Assistant is an actor who is responsible for managing and accessing clinical, identification and administrative documents such as consents, authorizations, lab images, insurance policies.
|**Domain Expert** | End User of the Service| Domain expert is an actor who is responsible for managing and accessing clinical guidelines.
|**Surgeon** | Secondary User of the Service | Users belonging to this category are responsible for receiving referrals from other healthcare providers.

5. System Features
------------------
Following are the system features of the SPCS:

![image](https://f.cloud.github.com/assets/4283040/1243012/4729b23c-2a5a-11e3-97ea-e6906fd0833c.png)
