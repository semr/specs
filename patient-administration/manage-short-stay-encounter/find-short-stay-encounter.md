#####Use Case ID: UC-PAS40
#####Use Case Name: Find Short Stay Encounter

**Level:**                     User Level Goal

**Primary Actors:**            Admitting Clerk

**Stakeholders:**              Admitting Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to find short stay encounter.

**Pre Condition:**             Admitting Clerk must be identified and authenticated.

**Post Condition:**            Short stay encounter found successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Find Short Stay Encounter)**

1. Admitting Clerk selects find encounter option.
2. System asks user to enter filtering criteria such as date of service, encounter provider and associated diagnosis.
3. Admitting Clerk specifies the filtering criteria.
5. System displays the list of short stay encounters.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 31.04
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**

![prpa_rm900300uv query](https://f.cloud.github.com/assets/5391320/1295461/6f3f3dfe-30af-11e3-9b8d-6e5d6d62deeb.png)
_______________________________________________________________
**Reference FHIR Resource:**

![encounter fhir resource](https://f.cloud.github.com/assets/5391320/1295268/cb11790e-30a9-11e3-8af5-6e7bb9dfdbda.png)
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






