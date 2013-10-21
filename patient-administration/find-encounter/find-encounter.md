#####Use Case ID: UC-PAS76
#####Use Case Name: Find Encounter

**Level:**                     User Level Goal

**Primary Actors:**            Patient

**Stakeholders:**              Patient, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to find encounters by parameter.

**Pre Condition:**             Patient must be identified and authenticated.

**Post Condition:**            System will find filtered encounters successfully.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Find Encounters By Organization)**

1. Patient requests to find patient encounters history in a particular organization.
2. System asks user to enter the patient Id and regional healthcare organization information such as name and OID.
3. Patient specifies the healthcare organization information.
4. System displays the list of organizations.
5. Patient selects an appropriate healthcare organization.
6. System displays patient’s encounter history for that particular hospital.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1**

1. Invalid organization details.
2. Invalid patient Id.

**Alt-1:Find Encounter By Time**

1. Patient requests to find patient encounters history by time.
2. System asks user to enter the patient Id and a time frame (date range: 20020301-20070301)
3. Patient specifies the required information.
4. System displays list of patient encounters for specified timeframe.

  * Sub-Flow:
      * Invalid time frame.
      * Invalid Patient Id.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST900301UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 31.04

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

1. Query
![prpa_rm900300uv query](https://f.cloud.github.com/assets/5391320/1370020/cea05754-3a0c-11e3-9c47-21db0e1c6c02.png)

1. Response
![prpa_rm900350uv query-response](https://f.cloud.github.com/assets/5391320/1370612/901e0e7c-3a25-11e3-85dc-434c147f47af.png)
_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![encounter fhir resource](https://f.cloud.github.com/assets/5391320/1369999/74cb4914-3a0c-11e3-8d49-1317a89cc65d.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Section Level Template: **" Encounters Section (entries optional) (V2) "**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

OpenEHR Archtype (Encounter):

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
