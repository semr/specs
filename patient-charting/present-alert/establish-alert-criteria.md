#####Use Case ID: UC-PCS47
#####Use Case Name: Establish Alert Criteria

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Patient, Healthcare Provider, Order Filler

**Purpose:**                   The main intent of this use case is to establish an alert criteria related to a guideline.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            Alert criteria will be established successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Establish Alert Criteria)**

1. Physician requests to establish alert criteria or rule.
2. System asks user to specify alert name, parameters (such as age, gender, problem/diagnosis, and medication), operator and value.
3. Physician specifies the fields and submits it.
4. System then perform the following actions:
  * Validates the fields
  * Creates alert criteria.
  * Presents alert whenever the specified criteria condition matches to a clinical event. It also records the date/time when alert was presented and other related details

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid parameters.
2. Invalid value.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 22.01, AM 22.03, AM 22.09, AM 22.10
