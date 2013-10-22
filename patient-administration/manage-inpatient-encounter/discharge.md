#####Use Case ID: UC-PAS45
#####Use Case Name: Discharge

**Level:**                     User Level Goal

**Primary Actors:**            Nursing Unit Clerk

**Stakeholders:**              Nursing Unit Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to capture inpatient discharge event.

**Pre Condition:**             Nursing Unit Clerk must be identified and authenticated.

**Post Condition:**            Patient discharged successfully.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Discharge)**

1. Nursing Unit Clerk requests system to discharge patient.
2. System asks user to enter discharge information.
3. Nursing Unit Clerk enters the required information.
4. System records patient discharge from inpatient encounter successfully.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST402001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**
[More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpa_rm402003uv complete inpatient](https://f.cloud.github.com/assets/5391320/1370011/a24a48b8-3a0c-11e3-91d4-0d443d01f8fe.png)

_______________________________________________________________
**Reference FHIR Resource:**
[More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![encounter fhir resource](https://f.cloud.github.com/assets/5391320/1369999/74cb4914-3a0c-11e3-8d49-1317a89cc65d.png)
_______________________________________________________________
**Reference CDA Template:**
[More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Document Level Template **"Discharge Summary (V2)"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**
[More Details](http://www.openehr.org/ckm/)

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
