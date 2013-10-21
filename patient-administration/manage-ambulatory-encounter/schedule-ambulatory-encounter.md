#####Use Case ID: UC-PAS21
#####Use Case Name: Schedule Ambulatory Encounter

**Level:**                     User Level Goal

**Primary Actors:**            Receptionist

**Stakeholders:**              Receptionist, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to schedule ambulatory encounter.

**Pre Condition:**             Receptionist must be identified and authenticated.

**Post Condition:**            Ambulatory encounter scheduled appropriately.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Schedule Ambulatory Encounter)**

1. Receptionist selects schedule ambulatory encounter option.
2. System asks user to enter data related to patient encounter.
3. Receptionist enters the patient information, reason for visit and physician information.
4. System creates an appointment for ambulatory encounter.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information cannot be added.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST401001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

FN 03.01
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**

![inpatient-encounter-event](https://f.cloud.github.com/assets/5391320/1370109/f2892f7a-3a10-11e3-8685-13b26797a2c5.png)
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


