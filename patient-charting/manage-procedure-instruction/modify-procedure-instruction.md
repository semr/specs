#####Use Case ID: UC-PCS41
#####Use Case Name: Modify Procedure Instruction

**Level:**                     User Level Goal

**Primary Actors:**            Physician, Nurse

**Stakeholders:**              Physician, Nurse, Patient, Healthcare Provider, Order Filler

**Purpose:**                   The main intent of this use case is to modify patient specific test and procedure instructions.

**Pre Condition:**             User must be identified and authenticated. 

**Post Condition:**            Procedure instruction will be modified successfully.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Modify Procedure Instruction)**

1. Physician selects edit instruction option.
2. System displays the list of patient specific instructions.
3. Physician selects an appropriate instruction.
4. System displays the instruction asks user to modify the instruction.
5. Physician modifies the instruction and submits it.
6. System then performs the following actions:
  * Validates the fields.
  * Records the modified instruction.
  * Provides the modified instruction to the order filler.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 10.03, AM 10.04
