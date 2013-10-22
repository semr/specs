#####Use Case ID: UC-PAS62
#####Use Case Name: Find Emergency Encounter

**Level:**                     User Level Goal

**Primary Actors:**            Emergency Room Clerk (ER Clerk)

**Stakeholders:**              Emergency Room Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to find emergency encounter.

**Pre Condition:**             Emergency Room Clerk must be identified and authenticated. 

**Post Condition:**            Emergency encounter found successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Find Emergency Encounter)**

1.	ER Clerk selects find emergency encounter option.
2.	System asks user to enter filtering criteria such as date of service, encounter provider and associated diagnosis.
3.	ER Clerk specifies the filtering criteria.
4.	System displays the list of emergency encounters.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid filtering criteria.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm900300uv query](https://f.cloud.github.com/assets/5391320/1370020/cea05754-3a0c-11e3-9c47-21db0e1c6c02.png)
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
