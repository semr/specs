#####Use Case ID: UC-PAS42
#####Use Case Name: Reschedule Admission

**Level:**                     User Level Goal

**Primary Actors:**            Clerk

**Stakeholders:**              Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to reschedule inpatient admission.

**Pre Condition:**             Clerk must be identified and authenticated.

**Post Condition:**            Inpatient admission rescheduled successfully.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Reschedule Admission)**

1. Clerk selects reschedule inpatient encounter option.
2. System displays the list of inpatient encounters.
3. Clerk selects an appropriate inpatient encounter.
4. System asks user to modify encounter appointment details such as time of service.
5. Clerk modifies the required details.
6. System reschedules an appointment for inpatient encounter.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid time for reschedule.
2. Physician not available for rescheduled date.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST402001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**

![revise-inpatient-appointment](https://f.cloud.github.com/assets/5391320/1370047/90debed2-3a0d-11e3-843c-18fceb99dfcb.png)
_______________________________________________________________
**Reference FHIR Resource:**

![encounter fhir resource](https://f.cloud.github.com/assets/5391320/1369999/74cb4914-3a0c-11e3-8d49-1317a89cc65d.png)
_______________________________________________________________
**Reference CDA Template:**

Entry Level Template **"Encounter Plan (V2)"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**

OpenEHR Archetype: (Encounter)

``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-COMPOSITION.encounter.v1

concept
	[at0000]	-- Encounter
language
	original_language = <[ISO_639-1::en]>
description
	original_author = <
		["name"] = <"Thomas Beale">
		["organisation"] = <"Ocean Informatics">
		["date"] = <"2005-10-10">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"Record of encounter as a progress note.">
			use = <"">
			keywords = <"progress", "note", "encounter">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"AuthorDraft">
	other_contributors = <>
	other_details = <
		["references"] = <"">
		["MD5-CAM-1.0.1"] = <"EDEB60AEFE411C22B796CBE227E44095">
	>

definition
	COMPOSITION[at0000] matches {	-- Encounter
		category matches {
			DV_CODED_TEXT matches {
				defining_code matches {[openehr::433]}
			}
		}
	}


ontology
	term_definitions = <
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Encounter">
					description = <"Generic encounter or progress note composition">
				>
			>
		>
	>
```






