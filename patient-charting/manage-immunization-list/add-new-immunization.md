#####Use Case ID: UC-PCS08
#####Use Case Name: Add New Immunization

**Level:**                     User Level Goal

**Primary Actors:**            Doctor/ Physician/ Clinician 

**Stakeholders:**              Patient Charting User

**Purpose:**                   The main intent of this use case is to add new immunization in the list.

**Pre Condition:**             Doctor/ Physician/ Clinician must be identified and authenticated.  

**Post Condition:**            Immunization added successfully without any conflicts.  

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Add New Immunization)**

1.	Physician selects the add immunization option for a particular patient.
2.	System shows the patient immunization history.
3.	Physician will select the coded immunization from the list and will specify the following information:
    * Route and frequency.
    * immunization type and dose
    * date and time of administration
    * lot number and expiration date
    * manufacturer
    * user ID
4.	System will perform following actions:
    * It will validate the information.
    * It will perform interaction checking.
5.	Physician will save immunization order.
6.	System will perform following actions:
    * It store immunization details as discrete data.
    * It will record the identity of prescriber.
    * It will record the date and time.
    * It will set immunization status to active.

_______________________________________________________________
**Open Issues**

-NA-
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Immunization List):**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

FN 16.02, FN 16.03, IP 15.01, IP 15.06, IP 15.04  

_______________________________________________________________
**EHR Functional Criteria:**

DC 1.4.4

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Charting):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A

_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![image](https://f.cloud.github.com/assets/4283040/1378809/0d83d8dc-3adb-11e3-8725-30a3fd9df3ba.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Section Level Template **"Immunizations Section (entries optional) (V2)"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

Procedure (openEhr Archetype)
```Archetype
archetype (adl_version=1.4)
	openEHR-EHR-COMPOSITION.vaccination_list.v1
concept
	[at0000]	-- Vaccination List
language
	original_language = <[ISO_639-1::en]>
description
	original_author = <
		["name"] = <"Heather Leslie">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"heather.leslie@oceaninformatics.com">
		["date"] = <"2013-03-12">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To record a persistent a list of vaccinations that have been administered to the subject over time and to enable sharing of a vaccination list to other healthcare providers.">
			use = <"Use to record a persistent list of all vaccinations administered to the subject.

In local systems it is possible to generate a list of vaccinations by querying the database for all ACTION.medication archetypes that have been used to record vaccinations. However this list is useful to support exchange of a local vaccination list with other healthcare providers.">
			keywords = <"vaccination", "immunisation", "list">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"CommitteeDraft">
	other_contributors = <"Ian McNicoll, Ocean Informatics, United Kingdom (Editor)", "Sam Heard, Ocean Informatics, Australia", "Sistine Barretto-Daniels, Ocean Informatics, Australia">
	other_details = <
		["current_contact"] = <"Heather Leslie, Ocean Informatics, heather.leslie@oceaninformatics.com">
		["MD5-CAM-1.0.1"] = <"2D1B12194E93B860DBD6E553CB0D0344">
	>
definition
	COMPOSITION[at0000] matches {	-- Vaccination List
		category matches {
			DV_CODED_TEXT matches {
				defining_code matches {[openehr::431]}
			}
		}
		content cardinality matches {1..*; unordered} matches {
			allow_archetype ACTION[at0001] occurrences matches {0..*} matches {	-- Vaccinations Administered
				include
					archetype_id/value matches {/openEHR-EHR-ACTION\.medication(-[a-zA-Z0-9_]+)*\.v1/}
			}
			allow_archetype EVALUATION[at0002] occurrences matches {0..*} matches {	-- Exclusion Statement
				include
					archetype_id/value matches {/.*/}
			}
			allow_archetype EVALUATION[at0003] occurrences matches {0..*} matches {	-- Absent Information
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
					text = <"Vaccination List">
					description = <"A persistent a list of vaccinations that have been administered to the subject over time, that may influence clinical decision-making and care provision.">
				>
				["at0001"] = <
					text = <"Vaccinations Administered">
					description = <"Details about vaccinations that have been administered to the subject.">
				>
				["at0002"] = <
					text = <"Exclusion Statement">
					description = <"Positive statement about the known exclusion of vaccination administration.">
					comment = <"For example: \"No vaccinations have been administered\".">
				>
				["at0003"] = <
					text = <"Absent Information">
					description = <"Positive statement that no information is available about vaccine administration.">
				>
			>
		>
  >
```

