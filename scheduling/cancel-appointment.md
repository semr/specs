####Description
--------------
The Scheduling Service module will allow user to cancel a scheduled appointment. It will also notify participating resources such as physician, charting system, tracking system etc about the cancelation of an appointment.

####Fully Dressed Use Case
--------------------------

#####Use Case ID: UC-SS04
#####Use Case Name: Cancel Appointment

**Level:**                     User Level Goal

**Primary Actors:**            Assistant

**Stakeholders:**              Assistant, Patient, Physician, Healthcare Provider

**Purpose:**                   The main intent of this use case is to cancel a scheduled appointment.

**Pre Condition:**             Assistant must be identified and authenticated.

**Post Condition:**            Appointment will be cancelled and notified to resources about its cancelation.

**Frequency of Occurrence:**   Medium

**Priority**                   High
__________________________________________________________
**Main Success Scenario: (Cancel Appointment)**

1. Assistant requests system to cancel appointment.
2. System then perform the following actions:
  * Cancels the appointment.
  * The entry of the scheduled appointment is canceled physician session schedule.
  * The medical chart archives cancel the request for patient's medical chart.
  * The radiology PACS cancels the request of patient’s recent orthopedic x-ray images.
  * The patient tracking system updates its schedules.
  
_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:if appointment type is inpatient or short stay**

1. Assistant requests system to cancel appointment (type = inpatient or short stay).
2. System then perform the following actions:
  * Cancels the appointment.
  * The entry of the scheduled appointment is canceled physician session schedule.
  * The entry of appointment is canceled from service delivery location schedule.
  * The medical chart archives cancel the request for patient's medical chart.
  * The radiology PACS cancels the request of patient’s recent orthopedic x-ray images.
  * The dietary requirements request for patient stay is canceled
  * The patient tracking system updates its schedules.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Scheduling):**

PRSC_ST000002UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 28.01

