#####Use Case ID: UC-PAS74
#####Use Case Name: Manage Encounter Location

**Level:**                     User Level Goal

**Primary Actors:**            Clerk

**Stakeholders:**              Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to change or cancel change request forinpatient location during an encounter.

**Pre Condition:**             Clerk must be identified and authenticated. 

**Post Condition:**            System will record the change of patient encounter.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Change Patient Location)**

1. Clerk requests to change patient location.
2. System displays the list of available locations for encounter.
3. Clerk selects appropriate location as a replacement.
4. System changes the patient location to a new location.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:Cancel Patient Location Change**

1. Clerk selects cancel patient location change option.
2. System displays the list of change patient location actions.
3. Clerk selects appropriate change patient location action.
4. System reverses the change in patient location.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST302011UV02, PRPA_ST302012UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
