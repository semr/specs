#####Use Case ID: UC-PCS56
#####Use Case Name: Make Referral

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Healthcare Provider

**Purpose:**                   The main intent of this use case is to make patient referral both outside or inside the healthcare facility.

**Pre Condition:**             Physician must be identified and authenticated.

**Post Condition:**            Patient will be referred to the target provider successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Make Referral)**

1. Physician selects add referral option.
2. System displays the list of patients available.
3. Physician selects an appropriate patient.
4. System displays the list of potential healthcare providers or clinicians.
5. Physician selects an appropriate provider.
6. System asks to enter description.
7. Physician enters the description and submits it.
8. System then perform the following actions:
  * Validates the fields.
  * Adds clinical (e.g associated problem/diagnosis) and administrative data ( e.g patient demographics, insurance data) of patient as part of referral.
  * Adds test and procedure results (if exist) as part of referral.
  * Transfers referral full contents to the target clinician or provider.
  * Records referral as well as the user identity, date and the time of referral.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
_______________________________________________________________
**EHR Functional Model ID: (Support for referral process):**

DC.2.4.4.1

_______________________________________________________________
**Reference Hl7 RMIM:** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A

_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

Yet to be defined.
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Document Level Template **"Referral Note"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

Referral (openEhr Archetype)
```Archetype
archetype (adl_version=1.4)
	openEHR-EHR-COMPOSITION.referral.v1

concept
	[at0000]	-- Referral document
language
	original_language = <[ISO_639-1::en]>
description
	original_author = <
		["name"] = <"Dr Ian McNicoll">
		["organisation"] = <"NHS CfH / Ocean Informatics">
		["email"] = <"ian.mcnicoll@oceaninformatics .com">
		["date"] = <"08/01/2008">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"For communication of a referral or service request to a service provider">
			use = <"">
			keywords = <"referral", "request">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"Initial">
	other_contributors = <"Heather Leslie", ...>
	other_details = <
		["references"] = <"">
		["MD5-CAM-1.0.1"] = <"6DB82589E80219EF8BA863CAFC2C8EC9">
	>

definition
	COMPOSITION[at0000] matches {	-- Referral document
		category matches {
			DV_CODED_TEXT matches {
				defining_code matches {[openehr::433]}
			}
		}
		context matches {
			EVENT_CONTEXT matches {
				participations cardinality matches {0..*; unordered} matches {
					PARTICIPATION occurrences matches {0..1} matches {
						function matches {
							DV_CODED_TEXT matches {
								defining_code matches {
									[local::
									at0033, 	-- Clinician making Referral
									at0034, 	-- Receiver of referral
									at0035, 	-- Other clinicians to receive copies of referral
									at0036, 	-- Payor
									at0037]	-- General Practitioner
								}
							}
						}
					}
				}
				other_context matches {
					ITEM_TREE[at0001] matches {	-- Tree
						items cardinality matches {3..*; unordered} matches {
							ELEMENT[at0028] occurrences matches {0..1} matches {	-- Requestor Identifier
								value matches {
									DV_TEXT matches {*}
								}
							}
							allow_archetype CLUSTER[at0038] occurrences matches {0..*} matches {	-- Patient
								include
									archetype_id/value matches {/openEHR-EHR-CLUSTER\.individual_personal(-[a-zA-Z0-9_]+)*\.v1/}
							}
							ELEMENT[at0039] occurrences matches {0..1} matches {	-- DateTime attested
								value matches {
									DV_DATE_TIME matches {*}
								}
							}
							ELEMENT[at0040] occurrences matches {0..1} matches {	-- Document Status
								value matches {
									DV_TEXT matches {*}
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
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Referral document">
					description = <"A document expressing all information required to make a request for provision of a specified service by another healthcare provider or organisation.">
				>
				["at0001"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0028"] = <
					text = <"Requestor Identifier">
					description = <"Copy of INSTRUCTION.request-referral's Requestor Identifier.">
				>
				["at0033"] = <
					text = <"Clinician making Referral">
					description = <"*">
				>
				["at0034"] = <
					text = <"Receiver of referral">
					description = <"*">
				>
				["at0035"] = <
					text = <"Other clinicians to receive copies of referral">
					description = <"*">
				>
				["at0036"] = <
					text = <"Payor">
					description = <"*">
				>
				["at0037"] = <
					text = <"General Practitioner">
					description = <"*">
				>
				["at0038"] = <
					text = <"Patient">
					description = <"Details about the patient to be explicitly expressed in the referral document.">
				>
				["at0039"] = <
					text = <"DateTime attested">
					description = <"Date/Time that the referral has been authorised or approved.">
				>
				["at0040"] = <
					text = <"Document Status">
					description = <"*">
				>
			>
		>
	>

```
Referral Detail (openEhr Archetype)
```Archetype
archetype (adl_version=1.4)
	openEHR-EHR-SECTION.referral_details.v1

concept
	[at0000]	-- Referral Details
language
	original_language = <[ISO_639-1::en]>
description
	original_author = <
		["name"] = <"Heather Leslie">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"heather.leslie@oceaninformatics.com">
		["date"] = <"07/03/2010">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To demonstrate a design pattern for representation of an Referral Request.">
			use = <"Use within a COMPOSITION related to referral, such as COMPOSITION.referral.
Supporting summary information can be added to the COMPOSITION slots - for example, SECTION.adverse_list, SECTION.problem_list, SECTION.medication_order_list.">
			keywords = <"referral", "request">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"0">
	other_contributors = <"Heath Frankel, Ocean Informatics, Australia", "Ian McNicoll, Ocean Informatics, United Kingdom">
	other_details = <
		["references"] = <"">
		["MD5-CAM-1.0.1"] = <"77FF1F18C4DC89FD43CAA1B5D5E03CE2">
	>

definition
	SECTION[at0000] matches {	-- Referral Details
		items cardinality matches {0..*; unordered} matches {
			allow_archetype INSTRUCTION[at0001] occurrences matches {0..1} matches {	-- Referral Request
				include
					archetype_id/value matches {/openEHR-EHR-INSTRUCTION\.request(-[a-zA-Z0-9_]+)*\.v1/}
			}
		}
	}


ontology
	term_definitions = <
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Referral Details">
					description = <"To demonstrate a design pattern for representation Referral details within a Referral composition.">
				>
				["at0001"] = <
					text = <"Referral Request">
					description = <"Slot constrained to specifically include archetypes representing referral requests.">
				>
			>
		>
	>

```
