#####Use Case ID: UC-PAS01
#####Use Case Name: Add Person to Person Registry

**Level:**                     User Level Goal

**Primary Actors:**            Registration Clerk (RC)

**Stakeholders:**              Registration Clerk, Medical Record Clerk, Person, Healthcare Provider

**Purpose:**                   The main intent of this use case is to add person demographics regardless of his/her role.

**Pre Condition:**             Registration Clerk must be identified and authenticated. 

**Post Condition:**            Person identifiers and demographics will be added in person registry successfully.

**Frequency of Occurrence:**   High(Per Minute)
__________________________________________________________
**Main Success Scenario: (Add Person to Person Registry)**

1. RC requests the system to add person’s registry.
2. System asks user to enter both person’s identifier information such as CNIC, insurance number and person’s basic information including name, date of birth, address and telephone number.
3. RC enters the required information.
4. System validates the entered information and asks user to describe person’s relationship with his/her parents, contact information and school information.
5. RC enters the required fields.
6. System then perform following actions: **a)**Validates the entered information, **b)**Assigns a unique identifier to the person, **c)**Successfully add person information to the person registry. 

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be added.
2. Specified parent does not exist.
3. Invalid relationship.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST101301UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A




