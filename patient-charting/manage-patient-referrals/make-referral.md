#####Use Case ID: UC-PCS56
#####Use Case Name: Make Referral

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Healthcare Provider

**Purpose:**                   The main intent of this use case is to make patient referral both outside or inside the healthcare facility.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            Patient will be referred to the target provider successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Make Referral)**

1. Physician selects add referral option.
2. System displays the list of patients available.
3. Physician selects an appropriate patient.
4. System displays the list of potential healthcare providers or clinicians.
5. Physician selects an appropriate provider.
6. System asks to enter description.
7. Physician enters the description and submits it.
8. System then perform the following actions:
  * Validates the fields.
  * Adds clinical (e.g associated problem/diagnosis) and administrative data ( e.g patient demographics, insurance data) of patient as part of referral.
  * Adds test and procedure results (if exist) as part of referral.
  * Transfers referral full contents to the target clinician or provider.
  * Records referral as well as the user identity, date and the time of referral.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
_______________________________________________________________
**EHR Functional Model ID: (Support for referral process):**

DC.2.4.4.1
