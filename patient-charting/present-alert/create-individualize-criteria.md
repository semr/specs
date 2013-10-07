#####Use Case ID: UC-PCS50
#####Use Case Name: Create Individualize Criteria

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Healthcare Provider

**Purpose:**                   The main intent of this use case is to create individualize alert criteria to address patients’ specific clinical situation.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            Individualize Criteria will be created successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Create Individualize Criteria)**

1. Physician requests to establish individualize alert criteria or rule.
2. System asks user to specify alert name, matching algorithm (for matching patients in a specific clinical situation), parameters (such as age, gender, problem/diagnosis, and medication), operator and value.
3. Physician specifies the fields and submits it.
4. System then perform the following actions:
  * Validates the fields
  * Creates alert criteria.
  * Presents alert to specified patients whenever the specified criterion condition match to a clinical event.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 22.11
