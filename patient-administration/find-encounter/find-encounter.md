#####Use Case ID: UC-PAS76
#####Use Case Name: Find Encounter

**Level:**                     User Level Goal

**Primary Actors:**            Patient

**Stakeholders:**              Patient, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to find encounters by parameter.

**Pre Condition:**             Patient must be identified and authenticated.

**Post Condition:**            System will find filtered encounters successfully.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Find Encounters By Organization)**

1. Patient requests to find patient encounters history in a particular organization.
2. System asks user to enter the patient Id and regional healthcare organization information such as name and OID.
3. Patient specifies the healthcare organization information.
4. System displays the list of organizations.
5. Patient selects an appropriate healthcare organization.
6. System displays patient’s encounter history for that particular hospital.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1**

1. Invalid organization details.
2. Invalid patient Id.

**Alt-1:Find Encounter By Time**

1. Patient requests to find patient encounters history by time.
2. System asks user to enter the patient Id and a time frame (date range: 20020301-20070301)
3. Patient specifies the required information.
4. System displays list of patient encounters for specified timeframe.

  * Sub-Flow:
      * Invalid time frame.
      * Invalid Patient Id.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST900301UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 31.04
