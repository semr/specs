#####Use Case ID: UC-PAS36
#####Use Case Name: Post Discharge

**Level:**                     User Level Goal

**Primary Actors:**            Nursing Unit Clerk

**Stakeholders:**              Nursing Unit Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to record post discharge updates.

**Pre Condition:**             Nursing Unit Clerk must be identified and authenticated.

**Post Condition:**            Recorded post discharge update successfully.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Post Discharge)**

1. Nursing Unit Clerk selects post discharge information to modify recorded encounter information.
2. System asks user to modify the short stay encounter information such as discharge disposition information.
3. Nursing Unit Clerk modifies the information.
4. System successfully records encounter information.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Invalid Information.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST405001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 31.02,AM 31.03, AM 31.04, AM 28.01, FN 03.01
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm405003uv complete](https://f.cloud.github.com/assets/5391320/1295482/03a694d8-30b0-11e3-9213-d65a7365af8e.png)
_______________________________________________________________
**Reference FHIR Resource:**
[More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![encounter fhir resource](https://f.cloud.github.com/assets/5391320/1295268/cb11790e-30a9-11e3-8af5-6e7bb9dfdbda.png)
_______________________________________________________________
**Reference CDA Template:**
[More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Document Level Template **"Discharge Summary (V2)"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**
[More Details](http://www.openehr.org/ckm/)

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






