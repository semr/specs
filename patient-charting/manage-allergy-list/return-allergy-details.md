#####Use Case ID: UC-PCS19
####Use Case Name: Return Allergy Details

**Level:**                     User Level Goal

**Primary Actors:**            Doctor/ Physician/ Clinician 

**Stakeholders:**              Patient Charting User

**Purpose:**                   TThe main intent of this use case is to return details of the particular allergy.

**Pre Condition:**             Doctor/ Physician/ Clinician must be identified and authenticated.  

**Post Condition:**            Allergy details returned successfully.  

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Return Allergy Details)**

1.	Physician will select allergy from the list and will request for its details.
2.	System will display the identity of the user who added, modified, inactivated or removed items from the allergy and adverse reaction list, including attributes of the changed items along with its date and time.

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Care Provision):**

REPC_RM000323UV
_______________________________________________________________
**Reference CCHIT Criteria:**

FN 05.13, FN 05.05 
_______________________________________________________________
**EHR Functional Criteria:**

DC 1.4.1

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Care Provision):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![image](https://f.cloud.github.com/assets/4283040/1379135/3fcc4d74-3ae5-11e3-8bd3-c5058960e4d2.png)

_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![image](https://f.cloud.github.com/assets/4283040/1378969/9e4d516e-3adf-11e3-89a0-dbb2ec3058d4.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Section Level Template **"Allergies Section (entries optional) (V2)"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

Procedure (openEhr Archetype)
```Archetype
archetype (adl_version=1.4)
	openEHR-EHR-COMPOSITION.adverse_reaction_list.v1
concept
	[at0000]	-- Adverse Reaction List
language
	original_language = <[ISO_639-1::en]>
description
	original_author = <
		["name"] = <"Heather Leslie">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"heather.leslie@oceaninformatics.com">
		["date"] = <"2013-03-14">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To record a persistent and managed list of all known adverse reactions experienced by the subject, or statements about positive exclusion or actual absence of information about adverse reactions, that may influence clinical decision-making and care provision.">
			use = <"Use to record a persistent and managed list of all known adverse reactions (including allergies, hypersensitivities, side effects or intolerances) experienced by the subject, or statements about positive exclusion or actual absence of information about adverse reactions, that may influence clinical decision-making and care provision. 

This list can be utilised as a source of up-to-date adverse reaction data for exchange or as the basis for decision support. 

This list can be comprised of three types of archetype:
- statements about the positive use of medications are recorded using the EVALUATION.adverse_reaction archetype; OR
- a statement about the positive exclusion of medication use can be recorded using the specific EVALUATION.exclusion-adverse_reaction archetype - for example: \"No known adverse reactions\"; OR
- a statement about no information being available - neither a positive and known presence of an adverse reaction nor a positive exclusion - can be recorded using the EVALUATION.absence archetype.

In order for this list to be accurate and safe to use as the basis for decision support activities and for exchange, this list should ideally be curated by a clinician responsible for the health record, rather than managed automatically by the clinical system through business rules alone.">
			keywords = <"adverse", "reaction", "allergy", "intolerance", "effect", "hypersensitivity", "list", "side">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"CommitteeDraft">
	other_contributors = <"Ian McNicoll, Ocean Informatics, United Kingdom (Editor)", "Sam Heard, Ocean Informatics, Australia", "Sistine Barretto-Daniels, Ocean Informatics, Australia">
	other_details = <
		["current_contact"] = <"Heather Leslie, Ocean Informatics, heather.leslie@oceaninformatics.com">
		["MD5-CAM-1.0.1"] = <"7C6282FE2D669F7DF0CC7CA4958E4A57">
	>
definition
	COMPOSITION[at0000] matches {	-- Adverse Reaction List
		category matches {
			DV_CODED_TEXT matches {
				defining_code matches {[openehr::431]}
			}
		}
		content cardinality matches {1..*; unordered} matches {
			allow_archetype EVALUATION[at0002] occurrences matches {0..*} matches {	-- Adverse Reactions
				include
					archetype_id/value matches {/openEHR-EHR-EVALUATION\.adverse_reaction(-[a-zA-Z0-9_]+)*\.v1/}
			}
			allow_archetype EVALUATION[at0003] occurrences matches {0..*} matches {	-- Exclusion Statement
				include
					archetype_id/value matches {/openEHR-EHR-EVALUATION\.exclusion-adverse_reaction(-[a-zA-Z0-9_]+)*\.v1/}
			}
			allow_archetype EVALUATION[at0004] occurrences matches {0..*} matches {	-- Absent Information
				include
					archetype_id/value matches {/openEHR-EHR-EVALUATION\.absence(-[a-zA-Z0-9_]+)*\.v1/}
			}
		}
	}

ontology
	term_definitions = <
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Adverse Reaction List">
					description = <"A persistent and managed list of adverse reactions experienced by the subject that may influence clinical decision-making and care provision.">
				>
				["at0002"] = <
					text = <"Adverse Reactions">
					description = <"Details about known adverse reactions.">
				>
				["at0003"] = <
					text = <"Exclusion Statement">
					description = <"Positive statement about exclusion of known adverse reactions.">
					comment = <"For example: \"No known adverse reactions\".">
				>
				["at0004"] = <
					text = <"Absent Information">
					description = <"Positive statement that no information is available about adverse reactions.">
				>
			>
		>
  >
```
