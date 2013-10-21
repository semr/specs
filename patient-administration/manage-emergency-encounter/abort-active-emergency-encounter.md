#####Use Case ID: UC-PAS59
#####Use Case Name: Abort Active Emergency Encounter

**Level:**                     User Level Goal

**Primary Actors:**            Emergency Room Clerk (ER Clerk)

**Stakeholders:**              Emergency Room Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to abort active emergency encounter.

**Pre Condition:**             Emergency Room Clerk must be identified and authenticated. 

**Post Condition:**            Active emergency encounter aborted successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Abort Active Emergency Encounter)**

1. ER Clerk requests abort active emergency encounter option.
2. System returns the list of emergency encounters available.
3. ER Clerk selects an appropriate emergency encounter and requests its abortion.
4. System cancels the specified emergency encounter.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST403004UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm403004uv abort](https://f.cloud.github.com/assets/5391320/1370185/1b4cd0b0-3a16-11e3-9698-d0d6defcafd5.png)
_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![encounter fhir resource](https://f.cloud.github.com/assets/5391320/1295268/cb11790e-30a9-11e3-8af5-6e7bb9dfdbda.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

N/A

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
