#####Use Case ID: UC-PAS56
#####Use Case Name: Revise Active Emergency Encounter

**Level:**                     User Level Goal

**Primary Actors:**            Emergency Room Clerk (ER Clerk)

**Stakeholders:**              Emergency Room Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to revise active emergency encounter.

**Pre Condition:**             Emergency Room Clerk must be identified and authenticated. 

**Post Condition:**            Active emergency encounter will be revised successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Revise Active Emergency Encounter)**

1. ER Clerk requests system to modify active encounter information.
2. System asks user to modify active emergency encounter details like emergency contact information, attending practitioner.
3. ER Clerk modifies the required fields.
5. System revises the active emergency encounter.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST403001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm403002uv revise](https://f.cloud.github.com/assets/5391320/1370183/129875e6-3a16-11e3-8190-664de727a0cf.png)
_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![encounter fhir resource](https://f.cloud.github.com/assets/5391320/1295268/cb11790e-30a9-11e3-8af5-6e7bb9dfdbda.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

* Section Level Template **"Encounters Section (entries optional) (V2)"**
* Section Level Template **"Encounters Section (entries required) (V2)"**

_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

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







