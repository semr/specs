#####Use Case ID: UC-PCS24
#####Use Case Name: Add Vital Sign

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Patient, Healthcare Provider

**Purpose:**                   The main intent of this use case is to add vital sign.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            Vital sign will be added successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Add Vital Sign)**

1. Physician selects add vital sign option.
2. System asks user to select vital sign type such as height, weight, blood pressure, heart rate,
BMI, BMI status, temperature and respiratory rate. Different vital signs can be described
using vital sign specific fields, For example:
  * Blood pressure have fields such as systolic (upper #) and diastolic
  * Body Weight has fields such as patient’s weight and its unit.
  * Heart rate has heart beats per minute field.
  * Body mass index have fields such as height and weight of the patient.
3. Physician selects the type of vital sign.
4. System asks user to specify the fields according to the selected vital sign type. For example in case of height, system will ask user to enter feet and inches.
5. Physician specifies the required fields.
6. System validates the field and records the vital sign.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 08.13, AM 08.14, AM 08.25
