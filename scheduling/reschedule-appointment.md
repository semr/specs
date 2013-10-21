####Description
--------------
The developed system will provide user with the facility to reschedule already scheduled appointments on patient’s request. The system will also notify participating resources about the updated schedule of an appointment.

####Fully Dressed Use Case
--------------------------

#####Use Case ID: UC-SS02
#####Use Case Name: Reschedule Appointment

**Level:**                     User Level Goal

**Primary Actors:**            Assistant

**Stakeholders:**              Assistant, Patient, Physician, Healthcare Provider

**Purpose:**                   The main intent of this use case is to reschedule an appointment on patient’s request.

**Pre Condition:**             Assistant must be identified and authenticated.

**Post Condition:**            Appointment will be rescheduled successfully.

**Frequency of Occurrence:**   High

**Priority**                   High
__________________________________________________________
**Main Success Scenario: (Reschedule Appointment)**

1. Assistant requests for rescheduling an appointment.
2. System asks user to select from latest available time slots.
3. Assistant selects a new time slot for the appointment.
4. System then perform the following actions:
  * Updates appointment entry for the specified patient in electronic patient record.
  * The request for his medical chart sent to the central medical archive, will be updated with the rescheduled time.
  * The request for the recent orthopedic x-ray images sent to the radiology PACS, will be updated with the rescheduled time.
  * The rescheduled appointment is sent to the patient tracking system to update its schedules.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Scheduling):**

PRSC_ST000002UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 28.01
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Scheduling):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![appointment entity](https://f.cloud.github.com/assets/5391320/1371056/e9cf593e-3a30-11e3-9f10-51d12706bdc8.png)
_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

Yet to be defined.
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Entry Level Template **"Encounter Plan (V2)"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

N/A

