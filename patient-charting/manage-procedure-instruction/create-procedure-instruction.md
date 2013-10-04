#####Use Case ID: UC-PCS40
#####Use Case Name: Create Procedure Instruction

**Level:**                     User Level Goal

**Primary Actors:**            Physician, Nurse

**Stakeholders:**              Physician, Nurse, Patient, Healthcare Provider, Order Filler

**Purpose:**                   The main intent of this use case is to create patient specific test and
procedure instructions.

**Pre Condition:**             User must be identified and authenticated. 

**Post Condition:**            Procedure instruction will be created successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Create Procedure Instruction)**

1. Physician selects a create instruction option.
2. System asks user to specify the patient, test or procedure, source type (such as external
source or internal) and instructions content.
3. Physician enters the required fields.
4. System then performs the following actions:
  * Validates the fields.
  * Records the procedure instructions
  * Provides these instructions to the order filler.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Patient does not exist.
2. Invalid test or procedure.

**Alt-2:If source type is external**

1. Repeat 1-3 steps of main scenario.
2. System asks user specify either the hyperlink of the external source or attach external source file containing instructions.
3. Physician specifies the instructions’ external source.
4. Repeat step 4 of the main scenario.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

FN 14.01, AM 10.05, AM 10.06
