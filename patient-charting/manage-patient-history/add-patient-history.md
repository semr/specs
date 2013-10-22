#####Use Case ID: UC-PCS21
####Use Case Name: Add Patient History

**Level:**                     User Level Goal

**Primary Actors:**            Doctor/ Physician/ Clinician 

**Stakeholders:**              Patient Charting User

**Purpose:**                   The main intent of this use case is to add history of the patient.

**Pre Condition:**             Doctor/ Physician/ Clinician must be identified and authenticated.  

**Post Condition:**            The patient history added successfully.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Add Patient History)**

1.	Physician selects the new patient history option for the particular patient.
2.	Physician will add smoking status, alcohol status and intrinsic patient history.
3.	Physician will save the history.
4.	System will store history in coded form.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Physician will specify the location to collect history.
2.	System will perform following actions:
    * It will collect history from specified sources.
    * It will validate history.
    * It will store history in coded form.

**Sub-Flow**

1.	Specified source is not accessible.
2.	Request cannot be processed.

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient History):**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 06.05, AM 06.06, AM 06.01
_______________________________________________________________
**EHR Functional Criteria:**

DC 1.2

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient History)):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

-NA-

_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![image](https://f.cloud.github.com/assets/4283040/1379214/0b00623a-3ae8-11e3-8568-c9a7f6c6bf8b.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Document Level Template **"History and Physical (V2)"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

Procedure (openEhr Archetype)
```Archetype
archetype (adl_version=1.4)
	openEHR-EHR-OBSERVATION.story.v1
concept
	[at0000]	-- Story/History
language
	original_language = <[ISO_639-1::en]>
	translations = <
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			author = <
				["name"] = <"Mona Saleh">
			>
		>
		["es-ar"] = <
			language = <[ISO_639-1::es-ar]>
			author = <
				["name"] = <"Guillermo Palli">
			>
		>
	>
description
	original_author = <
		["name"] = <"Heather Leslie">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"heather.leslie@oceaninformatics.com">
		["date"] = <"2008-05-15">
	>
	details = <
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			purpose = <"*To record a narrative description of the clinical history, as told to a clinician or recorded directly by an individual/patient, and to provide a framework in which to nest detailed CLUSTER archetypes, each of which will describe the various aspects of the clinical history in further detail.(en)">
			use = <"">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
		["es-ar"] = <
			language = <[ISO_639-1::es-ar]>
			purpose = <"*To record a narrative description of the clinical history, as told to a clinician or recorded directly by an individual/patient, and to provide a framework in which to nest detailed CLUSTER archetypes, each of which will describe the various aspects of the clinical history in further detail.(en)">
			use = <"">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To record a narrative description of the clinical history, as told to a clinician or recorded directly by an individual/patient, and to provide a framework in which to nest detailed CLUSTER archetypes, each of which will describe the various aspects of the clinical history in further detail.">
			use = <"Use to record the formal 'History of Presenting Complaint' by a clinician, as told to them by a patient; or use to record an individual's own account of their 'story' of symptoms, for example in a personal health record.

Use to incorporate the narrative descriptions of clinical history within existing or legacy clinical systems into an archetyped format, using the 'Story' data element.

Use to record a simple narrative and/or as a container archetype - to provide a common, queryable ENTRY archetype framework which can be extended by the inclusion of additional, specific and detailed CLUSTER archetypes, each of which will describe the various aspects of the clinical history. Examples of history-related CLUSTER archetypes include CLUSTER.symptom or CLUSTER.health_event.">
			keywords = <"history", "presenting", "complaint", "story">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"AuthorDraft">
	other_contributors = <"Sam Heard, Ocean Informatic, Australia", ...>
	other_details = <
		["current_contact"] = <"Heather Leslie, Ocean Informatics, heather.leslie@oceaninformatics.com">
		["MD5-CAM-1.0.1"] = <"CC7485F0AECA743E8ED57C71FF8850F5">
	>
definition
	OBSERVATION[at0000] matches {	-- Story/History
		data matches {
			HISTORY[at0001] matches {	-- Event Series
				events cardinality matches {1..*; unordered} matches {
					EVENT[at0002] occurrences matches {0..1} matches {	-- Any event
						data matches {
							ITEM_TREE[at0003] matches {	-- Tree
								items cardinality matches {1..*; unordered} matches {
									ELEMENT[at0004] occurrences matches {0..1} matches {	-- Story
										value matches {
											DV_TEXT matches {*}
										}
									}
									allow_archetype CLUSTER[at0006] occurrences matches {0..*} matches {	-- Details
										include
											archetype_id/value matches {/openEHR-EHR-CLUSTER\.symptom(-[a-zA-Z0-9_]+)*\.v1|openEHR-EHR-CLUSTER\.health_event(-[a-zA-Z0-9_]+)*\.v1|openEHR-EHR-CLUSTER\.issue(-[a-zA-Z0-9_]+)*\.v1/}
									}
								}
							}
						}
					}
				}
			}
		}
	}
ontology
	term_definitions = <
		["ar-sy"] = <
			items = <
				["at0000"] = <
					text = <"قصة المرض أو التاريخ - سوابق المرض">
					description = <"*The clinical history of a person, as told to a clinician or recorded directly by an individual/patient.(en)">
				>
				["at0001"] = <
					text = <"*Event Series(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"إحدى الوقائع">
					description = <"*Default, unspecified point in time or interval event which may be explicitly defined in a template or at run-time.(en)">
				>
				["at0003"] = <
					text = <"*Tree(en)">
					description = <"*@ internal @(en)">
				>
				["at0004"] = <
					text = <"قصة المريض">
					description = <"*Narrative description of the clinical history or story.(en)">
				>
				["at0006"] = <
					text = <"التفاصيل">
					description = <"*Additional structured details about the individual's story or patient's history.(en)">
					comment = <"*For example: a specific symptom such as nausea or pain; an event such as a fall off a bicycle; or an issue such as a desire to quit using tobacco.(en)">
				>
			>
		>
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Story/History">
					description = <"The clinical history of a person, as told to a clinician or recorded directly by an individual/patient.">
				>
				["at0001"] = <
					text = <"Event Series">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Any event">
					description = <"Default, unspecified point in time or interval event which may be explicitly defined in a template or at run-time.">
				>
				["at0003"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0004"] = <
					text = <"Story">
					description = <"Narrative description of the clinical history or story.">
				>
				["at0006"] = <
					text = <"Details">
					description = <"Additional structured details about the individual's story or patient's history.">
					comment = <"For example: a specific symptom such as nausea or pain; an event such as a fall off a bicycle; or an issue such as a desire to quit using tobacco.">
				>
			>
		>
		["es-ar"] = <
			items = <
				["at0000"] = <
					text = <"Evolucion o historia">
					description = <"*The clinical history of a person, as told to a clinician or recorded directly by an individual/patient.(en)">
				>
				["at0001"] = <
					text = <"Eventos">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"*Any event(en)">
					description = <"*Default, unspecified point in time or interval event which may be explicitly defined in a template or at run-time.(en)">
				>
				["at0003"] = <
					text = <"Arbol">
					description = <"@ internal @">
				>
				["at0004"] = <
					text = <"Historia">
					description = <"*Narrative description of the clinical history or story.(en)">
				>
				["at0006"] = <
					text = <"Detalles">
					description = <"*Additional structured details about the individual's story or patient's history.(en)">
					comment = <"*For example: a specific symptom such as nausea or pain; an event such as a fall off a bicycle; or an issue such as a desire to quit using tobacco.(en)">
				>
			>
		>
>

```
