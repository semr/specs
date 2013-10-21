####Description
--------------
The Scheduling Service module will allow user to revise appointment information such as contact information (e.g. name, phone number). The system will also notify patient tracking system about the updated schedule of an appointment.

####Fully Dressed Use Case
--------------------------

#####Use Case ID: UC-SS03
#####Use Case Name: Revise Appointment

**Level:**                     User Level Goal

**Primary Actors:**            Assistant

**Stakeholders:**              Assistant, Patient, Physician, Healthcare Provider

**Purpose:**                   The main intent of this use case is to revise appointment details.

**Pre Condition:**             Assistant must be identified and authenticated.

**Post Condition:**            Appointment will be revised successfully.

**Frequency of Occurrence:**   Medium

**Priority**                   High
__________________________________________________________
**Main Success Scenario: (Revise Appointment)**

1. Assistant selects revise appointment information options.
2. System displays the list of scheduled appointments.
3. Assistant selects an appropriate appointment.
4. System displays the appointment details and asks user to modify the desired information such as contact person’s name and phone number.
5. Assistant modifies the desired fields and submits them.
6. System then perform the following actions:
  * Records the updated appointment entry in electronic patient record.
  * The revised appointment is sent to the patient tracking system to update its schedules.
  

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid appointment information cannot be entered.

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
