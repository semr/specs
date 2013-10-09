#####Use Case ID: UC-PAS26
#####Use Case Name: Post Check Out Update

**Level:**                     User Level Goal

**Primary Actors:**            Receptionist

**Stakeholders:**              Receptionist, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to allow user to post check out updates.

**Pre Condition:**             Receptionist must be identified and authenticated.

**Post Condition:**            Post check out data updated successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Post Check Out Update)**

1. Receptionist selects post check out update to modify recorded encounter information.
2. System asks user to modify the encounter information such as patient information confidentiality.
3. Receptionist modifies the information.
3. System successfully records encounter information.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid information.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST401001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 31.02,AM 31.03, AM 31.04, AM 28.01
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**

![prpa_rm401002uv revise](https://f.cloud.github.com/assets/5391320/1295274/06d351ce-30aa-11e3-82fd-1163db6c7cfb.png)
_______________________________________________________________
**Reference FHIR Resource:**

![encounter fhir resource](https://f.cloud.github.com/assets/5391320/1295268/cb11790e-30a9-11e3-8af5-6e7bb9dfdbda.png)
_______________________________________________________________
**Reference CDA Template:**

* Section Level Template **"Encounters Section (entries optional) (V2)"**
* Section Level Template **"Encounters Section (entries required) (V2)"**

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






