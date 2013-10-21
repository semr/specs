#####Use Case ID: UC-PAS65
#####Use Case Name: Start Home Health

**Level:**                     User Level Goal

**Primary Actors:**            Nurse

**Stakeholders:**              Nurse, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to start home health encounter.

**Pre Condition:**             Nurse must be identified and authenticated.

**Post Condition:**            Home Health encounter started successfully.

**Frequency of Occurrence:**   Low(Occasionally)
__________________________________________________________
**Main Success Scenario: (Start Home Health)**

1. Nurse selects start home health encounter option.
2. System displays the list of appointment for home health encounters.
3. Nurse reviews appointment details and requests system to start home health encounter.
4. System successfully starts home health encounter.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST404001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm404001uv active](https://f.cloud.github.com/assets/5391320/1370306/d75f6304-3a1a-11e3-994a-4a23ada5688c.png)
_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![encounter fhir resource](https://f.cloud.github.com/assets/5391320/1369999/74cb4914-3a0c-11e3-8d49-1317a89cc65d.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Section Level Template **"Encounters Section (entries optional) (V2)"**

Section Level Template **"Encounters Section (entries optional) (V2)"**
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
