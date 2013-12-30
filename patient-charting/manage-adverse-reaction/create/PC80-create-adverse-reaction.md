#####Use Case ID: UC-PC80
#####Use Case Name: Create Adverse Reaction

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Nurse

**Purpose:**                   The main intent of this use case is to add a adverse reaction of a patient condition.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            Adverse Reactioh recorded successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Create Adverse Reaction)**

1. User selects a adverse reaction option.
2. System asks user to specify the type, severity and substance (if known).
3. User enters the required fields. 
4. System validates the fields and records the adverse reaction.

__________________________________________________________
**Alternate Flow:**

1. Repeat step 1-3  from the main success scenario.
2. If substance is known, associate particular substance with the reaction.
3. Repeat step 4 from the main success scenario.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**
[More Details](https://www.cchit.org/cchit-certified)

FN 05.05, FN 05.13
