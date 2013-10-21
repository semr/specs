#####Use Case ID: UC-PAS64
#####Use Case Name: Reschedule Home Health Encounter

**Level:**                     User Level Goal

**Primary Actors:**            Provider Coordinator (PC)

**Stakeholders:**              Provider Coordinator, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to reschedule home health encounter.

**Pre Condition:**             Provider Coordinator must be identified and authenticated.

**Post Condition:**            Home Health encounter rescheduled appropriately.

**Frequency of Occurrence:**   Low(Occasionally)
__________________________________________________________
**Main Success Scenario: (Reschedule Home Health Encounter)**

1. PC selects reschedule home health encounter option.
2. System displays the list of home health encounters.
3. PC selects an appropriate home health encounter.
4. System asks user to modify encounter appointment details such as time of service.
5. PC modifies the required details.
6. System reschedules an appointment for home health encounter.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid time for reschedule.
2. Physician may not be available for rescheduled date.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST404001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![appointment](https://f.cloud.github.com/assets/5391320/1370325/71dc6c06-3a1b-11e3-8f7f-2b1ae3c86bd9.png)
_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![encounter fhir resource](https://f.cloud.github.com/assets/5391320/1369999/74cb4914-3a0c-11e3-8d49-1317a89cc65d.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Entry Level Template **"Encounter Plan (V2)"**
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
