#####Use Case ID: UC-PCS48
#####Use Case Name: Modify Alert Criteria

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Patient, Healthcare Provider

**Purpose:**                   The main intent of this use case is to modify alert criteria related to a guideline.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            Alert criteria will be modified successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Modify Alert Criteria)**

1. Physician requests to modify alert criteria.
2. System displays the list of alert criteria related to a guideline.
3. Physician selects appropriate alert criteria to modify.
4. System displays the selected criteria and asks user to modify the rules or parameters of the criteria.
5. Physician modifies the fields and submits it.
6. System then performs the following actions:
  * Validates the fields
  * Creates alert criteria.
  * Presents alert whenever the specified criteria condition match to a clinical event. It also records the date/time when alert was presented and other related details.


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

AM 22.08, AM 22.09, AM 22.10
