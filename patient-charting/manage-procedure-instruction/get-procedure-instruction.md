#####Use Case ID: UC-PCS42
#####Use Case Name: Get Procedure Instruction

**Level:**                     User Level Goal

**Primary Actors:**            Physician, Nurse

**Stakeholders:**              Physician, Nurse, Patient, Healthcare Provider, Order Filler

**Purpose:**                   The main intent of this use case is to get patient specific test and procedure instruction.

**Pre Condition:**             User must be identified and authenticated. 

**Post Condition:**            Instruction details will be displayed successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Get Procedure Instruction)**

1. User requests to get instruction details.
2. System displays the list of patient specific instructions.
3. User selects an appropriate instruction.
4. System displays the details of instruction such as instruction content, effective time, instruction writer, patient and associated order.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:Get Instruction( User : Order Filler )**

1. User requests to get instruction details.
2. System displays the list of orders.
3. User selects an appropriate order
4. System displays the list of instructions associated with that order.
5. Repeat 3-4 steps of main scenario.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 10.03, AM 10.04, FN 17.01
