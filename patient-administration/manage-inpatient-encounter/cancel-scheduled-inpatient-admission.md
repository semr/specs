#####Use Case ID: UC-PAS47
#####Use Case Name: Cancel Scheduled Inpatient Admission

**Level:**                     User Level Goal

**Primary Actors:**            Receptionist

**Stakeholders:**              Receptionist, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to cancel scheduled inpatient admission.

**Pre Condition:**             Clerk must be identified and authenticated. 

**Post Condition:**            Scheduled inpatient admission cancelled successfully.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Cancel Scheduled Inpatient Admission)**

1. Receptionist requests cancel scheduled inpatient admission option.
2. System returns the list of inpatient encounter appointments available.
3. Receptionist selects an appropriate appointment and requests its cancellation.
4. System cancels the specified appointment.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST412001UV02
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

N/A
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



