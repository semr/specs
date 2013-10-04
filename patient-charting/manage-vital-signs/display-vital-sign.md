#####Use Case ID: UC-PCS26
#####Use Case Name: Display Vital Sign

**Level:**                     User Level Goal

**Primary Actors:**            Physician, Patient

**Stakeholders:**              Physician, Patient, Healthcare Provider, Order Filler

**Purpose:**                   The main intent of this use case is to display vital sign.

**Pre Condition:**             User must be identified and authenticated.

**Post Condition:**            Vital sign details will be displayed successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Display Vital Sign)**

1. User requests to display vital sign.
2. System displays the list of patient’s vital signs.
3. User selects an appropriate vital sign.
4. System not only displays the vital sign but also indicates to the user when a vital sign measurement falls outside a preset normal range set by the authorized user.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:Type is weight or height**

1. Repeat 1-3 steps of main scenario.
2. System then performs the following actions:
  * Displays the vital sign measurement
  * Indicates to the user when a vital sign measurement falls outside a preset normal range.
  * Display graph of height or weight over time.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 08.15, AM 08.24
