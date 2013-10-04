1. Module Scope
---------------

Scheduling services represent functions necessary to manage, search, and access appointments. Scheduling services provide a consistent specification for accessing and managing appointment repositories, independent of the underlying technology stack. The following thematic areas are considered in scope for:

* **Appointment Scheduling:** 
This is a set of functionality that provides the ability to manage appointments for outpatient, inpatient and short stay encounters. Its functions include scheduling appointments, rescheduling them, revising appointments, canceling scheduled appointments, checking participating resources availability, managing resources availability information, viewing resource schedule and notifying the external systems about the appointments’ state changes. These functions are generally protected and accessible by physician’s assistant with appropriate authorization.

* **Search / Query:**
This is a set of functionality that provides the ability to find both appointment history and scheduled appointments based on some search criteria. This includes search appointment by parameters such as patient Id, patient name, appointment type, assigned physician and a time frame. These functions are generally protected and accessible by physician’s assistant and physician with appropriate authorization.

2. Module Perspective
---------------------

Scheduling Services is a subsystem of the SEMR which provides functionality of management of appointments for particular resource.  In addition, the Scheduling Service have interfaces to the external systems such PAS (Patient Administration Service), Electronic Patient Record, Food Management System, Archival Management System and Patient Tracking System and Scheduling Service enabled applications. Any details of an external system are out of scope of this document. The figure #1 shows decomposition of Scheduling Service on the functionality areas and the supported external systems.

![scheduling-service-architecture](https://f.cloud.github.com/assets/5391320/1224447/edc8edd2-274a-11e3-8ad5-26f2b050a3f4.png)

3. Module Functions 
-------------------
The Scheduling Service is intended to allow the look up and management of a wide variety of appointment types, including, but not limited to, outpatient appointments, inpatient appointments, and short stay appointments. This includes procedures, observations, food and transportation service appointments as well. Apart from scheduling, Scheduling Service will also notify participating resources (such as physician, nurse, delivery location) and other external systems (such as electronic patient record, food management system, archival management system and patient tracking system) about the scheduling updates. At the functional level, the service interface will explicitly allow the query, creation and modification of the different appointments.

4. User Classes and Characteristics 
-----------------------------------
Actors will use the scheduling service for different purposes. These different actors can be generalized into a basic Scheduling Service User an Actor that is simply an individual, organization, or application that requires access to content for some purpose. Specializations of the Scheduling Service User actor participate in additional operational specific scenarios. Actors described in this section are not necessarily human actors, but also include organizations and systems. Figure #2 outlines the specializations and composition of the different actors used in this specification. These actors are described below.

![user-categories-of-scheduling Service](https://f.cloud.github.com/assets/5391320/1224403/e94ecf98-2749-11e3-8398-75e03612a963.jpg)

The following actors take a role in the Scheduling service actors:

| **Name**        | **Description**               | **Responsibilities**                                         |      
|-----------------|-------------------------------|--------------------------------------------------------------|
|**Scheduling Service**| Scheduling Service Server Instance|The Scheduling Service is a specific implementation of the Scheduling Service Server.
|**Assistant**    |Primary Actor                  |Assistant is an actor who is responsible for scheduling, rescheduling and accessing appointments that are not limited to a patient for scheduling time interval for resource.
|**Patient**      |Secondary Actor                |Users belonging to this category are responsible for requesting for scheduling an appointment via phone or through direct interaction with assistant.  
|**Physician**    |Secondary Actor                |Physician is an actor who is occupied for a time slot in case of appointment being scheduled. He/She can also arrange or request for scheduling an inpatient appointment.


5. System Features
------------------
Following are the system features of the Scheduling Service:

![user-case-diagram-of-scheduling-service](https://f.cloud.github.com/assets/5391320/1224393/94835740-2749-11e3-9487-3a14fdeada6a.jpg)

###Appendix A: Glossary
-----------------------
* **Electronic Patient Record:**
The Electronic Patient Record provides a general view of all patient-related data to care providers within the Good Health Hospital, including specialists who use the system to prepare themselves for treating patients and to store their notes on a patient's medical history, evaluation and prognosis. Part of the patient record is an overview of all prior and planned admissions for a patient, as for outpatient encounters and other healthcare activities.
* **Archive Management System:**
The central medical archive runs an Archive Management system, that uses planned admissions to provide 'pick lists' for delivering patient charts from the archive (or from temporary locations where the chart resides) to the appropriate department on time. The data for the scheduled inpatient stay is used to provide the necessary information for selecting the right chart (e.g. general inpatient chart) and knowing when and where it should be available.
* **Food Management System:**
Food Management system is tightly linked to inpatient logistics, to make sure that sufficient meals are available for inpatients and that dietary requirements are met. Therefore the scheduled admission might be communicated to the food management system in order to provide input for personnel planning and/or the ordering of ingredients. Note that the actual preparation of meals is usually bound to the eventual admission of the patient.
* **Appointment:**
An Appointment is an agreement between participating resources and usually, but not necessarily, a patient to schedule intervals of time for some purpose.
* **Slots:** 
Slots are identifiable periods of time that can be scheduled.
* **Open slots:** 
Open slots are periods of time on a schedule during which a service may occur and/or a resource is available for use.
* **Booked slots:** 
Booked slots are periods of time on a schedule that have already been reserved.
* **Repeating appointments:** 
Repeating appointments are repetitions of the same appointment occurring at later slots but sharing the same patient, service and resource characteristics as the first appointment in the repeating series.
* **Services:** 
Services are real-world events, such as clinic appointments, the performance of which is controlled by a schedule.
* **Domain Message Information Model (DMIM):** 
A form of Refined Message Information Model (R-MIM) constructed to represent the totality of concepts embodied in the individual R-MIMs needed to support the communication requirements of a particular HL7 domain.
