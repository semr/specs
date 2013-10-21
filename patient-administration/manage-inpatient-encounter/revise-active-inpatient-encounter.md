#####Use Case ID: UC-PAS44
#####Use Case Name: Revise Active Inpatient Encounter

**Level:**                     User Level Goal

**Primary Actors:**            Admitting Clerk

**Stakeholders:**              Admitting Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to revise active inpatient encounter.

**Pre Condition:**             Admitting Clerk must be identified and authenticated.

**Post Condition:**            Active inpatient encounter revised successfully.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Revise Active Inpatient Encounter)**

1. Admitting Clerk requests system to modify active encounter information.
2. System asks user to modify active short stay encounter details such as emergency contact information, attending practitioner.
3. Admitting Clerk modifies the required fields and submits it.
4. System revises the active inpatient encounter record.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST402001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

IP 15.12, FN 03.01, IP 01.01, IP 01.02, IP 01.03
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**

![prpa_rm402002uv revise inpatient](https://f.cloud.github.com/assets/5391320/1370008/92e7ed9e-3a0c-11e3-974f-bf9fa1f3fdd8.png)

_______________________________________________________________
**Reference FHIR Resource:**

![encounter fhir resource](https://f.cloud.github.com/assets/5391320/1369999/74cb4914-3a0c-11e3-8d49-1317a89cc65d.png)
_______________________________________________________________
**Reference CDA Template:**

Section Level Template **"Encounters Section (entries optional)"**

Section Level Template **"Encounters Section (entries required)"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**

OpenEHR Archetype: (Encounter)

```
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



