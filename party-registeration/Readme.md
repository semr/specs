1. Module Scope
---------------

Party registration services represent functions necessary to manage, search, and access provider registry. It provides a consistent specification for accessing and managing provider registry, independent of the underlying technology stack. Party registration repository represents various resources including provider demographics, organization demographics, provider groups and hospital organization (e.g. cardiology service group). The following thematic areas are considered in scope for.

* **Provider and Organization Management:** 
This is a set of functionality that provides the ability to manage provider and organization demographics as part of a party registration service. Its functions include the ability to identify a provider and record its demographics, manage provider organization, maintaining hospital organizations as well as managing provider groups. These functions are generally protected and accessible by registration clerk and clerk with appropriate authorization.

* **Search / Query:**
This is a set of functionality that provides the ability to find provider and organization details based on some search criteria. This includes search providers and organization by parameters such as name, address, role and multiple identifiers. These functions are generally protected and accessible by clerks, providers and organizations with appropriate authorization.

2. Module Perspective
---------------------
PRS is a subsystem of the SEMR which provides functionality of management of provider (personnel) and organization demographics internally and also used to connect the sources systems with centralized registry by communicating provider/provider organization information. In addition, secondary sources can also communicate provider information with centralized registry if the information is not available from the primary sources. Secondary sources are organizations that supply ancillary information about individual health care practitioners. Any details of an external system are out of scope of this document. The following figure shows decomposition of PRS on the functionality areas and the supported external systems.

![prs-architecture](https://f.cloud.github.com/assets/5391320/1225168/8fa7de4c-275f-11e3-9712-daafb4126ce9.png)

3. Module Functions 
-------------------
The PRS is intended to allow the look up and management of a wide variety of provider management features, including, but not limited to, provider registry and organization registry. This includes the ability to establish and maintain physician group, send notification to concerned authorities about the updates in the registries and manage hospitals internal organizations. At the functional level, the service interface will explicitly allow the query, creation and modification of the different personnel management components.

4. User Classes and Characteristics 
-----------------------------------
Actors will use the personnel management service for different purposes. These different actors can be generalized into a basic PRS User an Actor that is simply an individual, organization, or application that requires access to content for some purpose. Specializations of the PRS User actor participate in additional operational specific scenarios. Actors described in this section are not necessarily human actors, but also include organizations and systems. Following figure  outlines the specializations and composition of the different actors used in this specification. These actors are described below.

![Figure-#2-User-Categories-of-PRS](https://f.cloud.github.com/assets/5391320/1225174/af918adc-275f-11e3-9431-33ff828d333e.jpg)

The following actors take a role in the party registration service actors:

| **Name**        | **Description**               | **Responsibilities**                                         |      
|-----------------|-------------------------------|--------------------------------------------------------------|
|**PRS Service**  |PRS Server Instance            |The PRS Service is a specific implementation of the PRS Server.
|**Clerk**        |Primary Actor                  |Clerk is an actor responsible for accessing and managing personnel, organizations and physician groups locally.
|**Registration Clerk**|Primary Actor             |Users belonging to this category are responsible for registration of the providers locally.
|**Provider**     |Primary Actor                  |Provider is an actor who is responsible for accessing and viewing his/her full profile as well as querying about his/her provider group membership.
|**Primary Source System**|Primary Actor          |Source systems are the systems deployed typically by licensing and regulatory bodies to answer organization queries related to providers and organizations. User belonging to this category is responsible for answering queries from JPRS and JPORS. Primary sources may also be employer organizations that have ongoing relationships with individual practitioners and can (collaboratively) supply role information about them to the JPRS in the absence of an authoritative primary source.
|**Secondary Source System**|Secondary Actor      |Secondary source systems are the systems that supply ancillary information about individual health care practitioners.
|**Healthcare Organization**|Off-Stage Actor      |A Healthcare organization has an interest in accurate and consistent personnel management records storage.
|**PRS Enabled Applications** |Secondary Actor    |All those systems interested in accessing provider information.

5. System Features
------------------
Following are the system features of the PRS:

![Figure-#3:-Use-Case-Diagram-of-PRS](https://f.cloud.github.com/assets/5391320/1225183/d9c93c8c-275f-11e3-8d01-fa7be8fb994b.jpg)

###Appendix A: Glossary
-----------------------
* **Electronic Patient Record:**
The Electronic Patient Record provides a general view of all patient-related data to care providers within the Good Health Hospital, including specialists who use the system to prepare themselves for treating patients and to store their notes on a patient's medical history, evaluation and prognosis. Part of the patient record is an overview of all prior and planned admissions for a patient, as for outpatient encounters and other healthcare activities.
* **Jurisdictional Provider Registry System (JPRS):**
The jurisdictional provider registry system (JPRS) is a centralized source of information about individual healthcare providers. Data feeds to the JPRS come from a variety of primary sources; typically licensing and regulatory bodies like the College of Physicians, that make use of the publish and subscribe services, and query and report capabilities of the JPRS to make their data available to subscribing organizations. Access to the data is governed by contractual agreements between individual sources (who 'own' the data in the JPRS) and consumer organizations.
* **Jurisdictional Provider Organization Registry System (JPORS):**
The jurisdictional provider organization registry system (JPORS) is a centralized source of information about healthcare provider organizations. Data feeds to the JPORS come from a variety of primary sources, typically licensing and regulatory bodies like the College of Pharmacists that use the publish and subscribe services, and query and report capabilities of the JPORS to make their data available to subscribing organizations. Access to the data is governed by contractual agreements between individual sources (who 'own' the data in the JPORS) and consumer organizations.
* **Services:**
Services are real-world events, such as clinic appointments, the performance of which is controlled by a schedule.
* **Domain Message Information Model (DMIM):** 
A form of Refined Message Information Model (R-MIM) constructed to represent the totality of concepts embodied in the individual R-MIMs needed to support the communication requirements of a particular HL7 domain.

###Appendix B: Domain Analysis Models
-------------------------------------
The following Domain Analysis Model (DAM) was developed by the personnel management committee as part of the exercise of modeling the business of Personnel Management. This same business information is in turn reflected in the Domain Information Model (DMIM), where needed to fulfill messaging requirements. The purpose of the DAM is to show the relationships between the significant classes in the domain and the key attributes of interest within each class.

![dam pms](https://f.cloud.github.com/assets/5391320/1225194/47b9bd0c-2760-11e3-8feb-35a5c8655f80.gif)

**Domain Analysis Walkthrough:** The Personnel Management Domain Analysis Model (DAM) represents the central concepts, attributes, and relationships that define the domain(s)-of-interest of the Personnel Management Technical Committee (PM TC) using the iconography of UML class diagrams. The development of a DAM for a given domain is described in the Requirements and Analysis chapter of the Health Development Framework (HDF) process being developed by HL7.


An initial version of the PM DAM was built over the course of two Working Group meetings in 2003 using input from a variety of domain experts from Human Relations (HR), regulatory agencies, and US Department of Defense Credential and Credential/Privilege Management. It has subsequently been (and will continue to be) expanded/more finely granulated based on ongoing discussions with numerous domain experts including those working on specific projects such as Provider Registries, Credentialing and Privileging Systems, etc.


The DAM intentionally utilizes 'non-RIM-speak' (i.e. terms familiar to domain experts but not necessarily used in the RIM) to capture the essential concepts, attributes, and relationships of the domain in 'domain-friendly' terms. In the best-of-all-possible worlds, the DAM would reach a fairly mature state before it would be utilized as a guide to construct a semantically equivalent PM DMIM. In fact, the PM TC had an existing DMIM before they committed to adopting the HDF and, as a consequence, building a DAM. As such, the DAM is being simultaneously developed in both a forward (DAM -> DMIM) and backward (DMIM -> DAM) direction.


A listing of the Domain Analysis Classes is included below to provide a glossary critical to the successful understanding of the mapping between the DAM and DMIM that explains the semantic equivalence between the two representations.


The central conceptual idea represented in the PM DAM is that of an instance of an Entity playing/assuming a Role. Note that Entity is an abstract concept, i.e. there are no instances of the Entity concept, but instead instances of the various subtypes of Entity, i.e. Place, Organization, Device, and Living Subject (which, in turn has subtypes of Person and Animal).


A specific Role may require certain Qualifications (which may be bundled together in complex collections whose semantics are specified by instances of Qualification Relationship) of the Entity subtype instance playing the Role. The specific Qualification of the 'playing' Entity instance may be validated by the 'assigning' Entity instance by one or more Credential instances issued to the playing Entity. Credential is modeled as a specialization of the concept of Qualification to distinguish that a Qualifications simply an assertion, whereas a Credential involves two Parties: a Responsible Party (the receiver of the credential) and a Commissioning Party (the issuer of the credential). These two concepts are currently not shown in the DAM but are conceptually represented in the PM DMIM by the relationships of Player and Scoper. Note that if a specific Credential is required for a particular Role, the scoping Entity (or other person or organization) may choose to validate the existence of the credential for the specific player Entity, capturing the details of this validation process in a Certificate of Verification.
An instance of an Entity-in-a-Role may apply for or be assigned to a Position, an action that is documented using an instance of the Application or Assignment class. Subsequent analysis as to the attributes of this class may dictate that it be split into two separate classes. A Position may be associated with one or more instances of the Responsibility class. Similar to the relationship between Qualification and Credential, the concept Responsibility is subtype to Privilege, a type of Responsibility with a higher degree of formality in that it involves a 'contract' between the Privilege Grantor and the Privilege Recipient (concepts not currently shown in the DAM but similar DMIM concepts of Player and Scoper as discussed above). The DAM does NOT show that a Privilege may be granted to a Entity-in-a-Role in the absence of a formal assignment to a Position although this business process is often supported. This additional association is not shown because the details of any differences in messages required to support this concept are as yet unknown and uncertain. Finally, note that a Position may be associated with a complex set of Criterion instances which specify the set of Qualification and/or Credential instances and their inter-relationships in the context of a specific Position. The Criterion class has been subtyped to Time-Based Criterion and Non-Time-Based Criterion based on domain expert input. However, to date, little analysis has been done with respect to these concepts.

###Appendix C: To Be Determined List:
-------------------------------------
Following is list of things to be determined at project’s later stages:
* Communication with source systems such as licensing or regulatory bodies.
* Figuring out whether Jurisdictional provider registry system (JPRS) exists in the region (or country or city) or we have to develop it or it is out of projects scope.
* Figuring out whether jurisdictional provider organization registry system (JPORS) exists in the region (or country or city) or we have to develop it or it is out of projects scope.
