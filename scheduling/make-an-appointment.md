####Description
--------------
An Appointment is an agreement between participating resources and usually, but not necessarily, a patient to schedule intervals of time for some purpose. The system will allow user to make an appointment for an encounter. System will also notify the participating resources about the appointment details after appointment being scheduled.

####Fully Dressed Use Case
--------------------------

#####Use Case ID: UC-SS01
#####Use Case Name: Make an Appointment

**Level:**                     User Level Goal

**Primary Actors:**            Assistant

**Stakeholders:**              Assistant, Patient, Physician, Healthcare Provider

**Purpose:**                   The main intent of this use case is to make a new appointment for a resource.

**Pre Condition:**             Assistant must be identified and authenticated.

**Post Condition:**            New appointment will be created successfully.

**Frequency of Occurrence:**   High

**Priority**                   High
__________________________________________________________
**Main Success Scenario: (Make an Appointment)**

1. Assistant requests for creating a new appointment.
2. System asks user to specify patient (if exist), attending physician and appointment type (such as inpatient, outpatient).
3. Assistant enters the required information.
4. System then perform the following actions:
  * Validates the entered data.
  * Records appointment entry for the specified patient in electronic patient record.
  * A request for his medical chart is sent to the central medical archive, which will deliver the chart on its regular delivery round prior to the scheduled visit.
  * A request for recent orthopedic x-ray images is sent to the radiology Picture Archival and Communication System (PACS), which will pre-fetch the image files (from optic media) prior to the scheduled visit.
  * The appointment is sent to the patient tracking system to update its schedules.
 

  
_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:If patient record does not exist**

1. Assistant requests for creating a new appointment.
2. System asks user to specify patient’s brief details required for his/her registration, attending physician and appointment type (such as inpatient, outpatient).
3. Repeat the 3-4 steps of main scenario.

**Alt-2:If appointment type is inpatient or for short stay encounter**

1. Assistant requests for creating a new appointment.
2. System asks user to specify patient (if exist), attending physician and appointment type (if type = inpatient or short stay).
3. Assistant enters the required information and checks for availability of participating resources (such as required physician availability for sessions during inpatient or short stay, service delivery location availability).
4. System then perform the following actions:
  * Validates the entered data.
  * Reserves physician session time and service delivery locations.
  * Records appointment entry for the specified patient in electronic patient record.
  * A request for his medical chart is sent to the central medical archive, which will deliver the chart on its regular delivery round prior to the scheduled visit.
  * The hospital kitchen is informed of the dietary requirements for patient.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Scheduling):**

PRSC_ST000002UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 28.01
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Scheduling):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prsc_rm010000uv appointment](https://f.cloud.github.com/assets/5391320/1371027/622e46fc-3a30-11e3-851d-31890f24feb6.png)

_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

Yet to be defined.
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Entry Level Template **"Encounter Plan (V2)"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

N/A
