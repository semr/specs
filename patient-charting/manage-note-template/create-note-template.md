#####Use Case ID: UC-PCS28
#####Use Case Name: Create Note Template

**Level:**                     User Level Goal

**Primary Actors:**            Physician

**Stakeholders:**              Physician, Healthcare Provider

**Purpose:**                   The main intent of this use case is to create a new clinical notes template
based on predefined clinical or administrative fields

**Pre Condition:**             Note template will be created successfully.

**Post Condition:**            Note template will be created successfully.

**Frequency of Occurrence:**   Low
__________________________________________________________
**Main Success Scenario: (Create Note Template)**

1. Physician selects a create note template option.
2. System asks user to specify the Id, name of the template, description and list of fields.
3. Physician enters the required fields.
4. System then performs the following actions:
  * Validates the fields.
  * Records a new clinical note template.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Template already exists.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

N/A
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 08.19
_______________________________________________________________
**Reference Hl7 RMIM :** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

N/A

_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

N/A
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Document Level Template **"Consultation Note"**
Document Level Template **"Operative Note"**
Document Level Template **"Procedure Note"**
Document Level Template **"Referral Note"**
Document Level Template **"Progress Note"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

Review (openEhr Archetype)
``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-ACTION.review.v1

concept
	[at0000]	-- Review
language
	original_language = <[ISO_639-1::en]>
description
	original_author = <
		["name"] = <"Heather Leslie">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"heather.leslie@oceaninformatics.com">
		["date"] = <"2011-03-09">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To record details of clinical activity regarding the performance of a formal clinical review of a subject's clinical situation, a specific aspect of their clinical care or a specified part of the health record.">
			use = <"Use to record details of clinical activity regarding the performance of a formal clinical review of a subject's clinical situation, a specific aspect of their clinical care or a specified part of the health record. For example: recording activity around the performance of a formal Medicines Review; or a care coordinator reviewing progress of Care Plans; or a file review by a case worker.">
			keywords = <"record", "review", "medication", "vaccination", "adverse reaction", "allergy", "medicine">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"CommitteeDraft">
	other_contributors = <>
	other_details = <
		["current_contact"] = <"Heather Leslie, Ocean Informatics, heather.leslie@oceaninformatics.com">
		["MD5-CAM-1.0.1"] = <"D6E52ED907C796AABE429BFA416B894A">
	>

definition
	ACTION[at0000] matches {	-- Review
		ism_transition matches {
			ISM_TRANSITION[at0003] matches {	-- Review Planned
				current_state matches {
					DV_CODED_TEXT matches {
						defining_code matches {[openehr::526]}
					}
				}
				careflow_step matches {
					DV_CODED_TEXT matches {
						defining_code matches {[local::at0003]}		-- Review Planned
					}
				}
			}
			ISM_TRANSITION[at0010] matches {	-- Review Postponed
				current_state matches {
					DV_CODED_TEXT matches {
						defining_code matches {[openehr::527]}
					}
				}
				careflow_step matches {
					DV_CODED_TEXT matches {
						defining_code matches {[local::at0010]}		-- Review Postponed
					}
				}
			}
			ISM_TRANSITION[at0012] matches {	-- Review Cancelled
				current_state matches {
					DV_CODED_TEXT matches {
						defining_code matches {[openehr::528]}
					}
				}
				careflow_step matches {
					DV_CODED_TEXT matches {
						defining_code matches {[local::at0012]}		-- Review Cancelled
					}
				}
			}
			ISM_TRANSITION[at0004] matches {	-- Review Scheduled
				current_state matches {
					DV_CODED_TEXT matches {
						defining_code matches {[openehr::529]}
					}
				}
				careflow_step matches {
					DV_CODED_TEXT matches {
						defining_code matches {[local::at0004]}		-- Review Scheduled
					}
				}
			}
			ISM_TRANSITION[at0019] matches {	-- Review Re-scheduled
				current_state matches {
					DV_CODED_TEXT matches {
						defining_code matches {[openehr::529]}
					}
				}
				careflow_step matches {
					DV_CODED_TEXT matches {
						defining_code matches {[local::at0019]}		-- Review Re-scheduled
					}
				}
			}
			ISM_TRANSITION[at0006] matches {	-- Review Performed
				current_state matches {
					DV_CODED_TEXT matches {
						defining_code matches {[openehr::245]}
					}
				}
				careflow_step matches {
					DV_CODED_TEXT matches {
						defining_code matches {[local::at0006]}		-- Review Performed
					}
				}
			}
			ISM_TRANSITION[at0011] matches {	-- Review Suspended
				current_state matches {
					DV_CODED_TEXT matches {
						defining_code matches {[openehr::530]}
					}
				}
				careflow_step matches {
					DV_CODED_TEXT matches {
						defining_code matches {[local::at0011]}		-- Review Suspended
					}
				}
			}
			ISM_TRANSITION[at0013] matches {	-- Review Aborted
				current_state matches {
					DV_CODED_TEXT matches {
						defining_code matches {[openehr::531]}
					}
				}
				careflow_step matches {
					DV_CODED_TEXT matches {
						defining_code matches {[local::at0013]}		-- Review Aborted
					}
				}
			}
			ISM_TRANSITION[at0016] matches {	-- Review Completed
				current_state matches {
					DV_CODED_TEXT matches {
						defining_code matches {[openehr::532]}
					}
				}
				careflow_step matches {
					DV_CODED_TEXT matches {
						defining_code matches {[local::at0016]}		-- Review Completed
					}
				}
			}
		}
		description matches {
			ITEM_TREE[at0001] matches {	-- Tree
				items cardinality matches {0..*; unordered} matches {
					ELEMENT[at0002] occurrences matches {0..1} matches {	-- Review Activity
						value matches {
							DV_TEXT matches {*}
						}
					}
					ELEMENT[at0015] occurrences matches {0..1} matches {	-- Description
						value matches {
							DV_TEXT matches {*}
						}
					}
					ELEMENT[at0014] occurrences matches {0..1} matches {	-- Reason
						value matches {
							DV_TEXT matches {*}
						}
					}
				}
			}
		}
		protocol matches {
			ITEM_TREE[at0017] matches {	-- Tree
				items cardinality matches {0..*; unordered} matches {
					ELEMENT[at0018] occurrences matches {0..1} matches {	-- Start Date/Time
						value matches {
							DV_DATE_TIME matches {*}
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
					text = <"Review">
					description = <"Clinical activity regarding the performance of a formal clinical review of a subject's clinical situation, a specific aspect of their clinical care or a specified part of the health record.">
				>
				["at0001"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Review Activity">
					description = <"Identification of the item or activity that is being reviewed.">
					comment = <"Coding with a terminology is preferred, if available. For example: Medicines List; Care Plan Review; or File Review.">
				>
				["at0003"] = <
					text = <"Review Planned">
					description = <"The review activity is planned.">
				>
				["at0004"] = <
					text = <"Review Scheduled">
					description = <"The review activity has been scheduled.">
				>
				["at0006"] = <
					text = <"Review Performed">
					description = <"The review activity has been performed.">
				>
				["at0010"] = <
					text = <"Review Postponed">
					description = <"The review has been postponed.">
				>
				["at0011"] = <
					text = <"Review Suspended">
					description = <"The review activity has been suspended.">
				>
				["at0012"] = <
					text = <"Review Cancelled">
					description = <"The review activity has been cancelled.">
				>
				["at0013"] = <
					text = <"Review Aborted">
					description = <"The review activity has been aborted.">
				>
				["at0014"] = <
					text = <"Reason">
					description = <"Reason that the care pathway step for the identified Review Activity was carried out.">
					comment = <"For example, the reason for the cancellation or suspension of the Review Activity">
				>
				["at0015"] = <
					text = <"Description">
					description = <"Narrative description of the Review Activity relevant for the care pathway step.">
					comment = <"For example: description of the Medicines Review that was performed; or the Care Plan review that is planned or scheduled.">
				>
				["at0016"] = <
					text = <"Review Completed">
					description = <"The review activity has been completed.">
				>
				["at0017"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0018"] = <
					text = <"Start Date/Time">
					description = <"The start date and/or time for the Review activity.">
					comment = <"This will indicate the scheduled date/time when recorded against the Scheduled care pathway step or the actual Start date/time in the Procedure performed step.">
				>
				["at0019"] = <
					text = <"Review Re-scheduled">
					description = <"The review activity has been re-scheduled.">
				>
			>
		>
	>

```
Report Procedure (openEhr Archetype)
``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-COMPOSITION.report-procedure.v1
specialise
	openEHR-EHR-COMPOSITION.report.v1

concept
	[at0000.1]	-- Procedure Report
language
	original_language = <[ISO_639-1::en]>
description
	original_author = <
		["name"] = <"Heather Leslie">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"heather.leslie@oceaninformatics.com">
		["date"] = <"2012-12-10">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"Generic container archetype to carry information about a procedure or operation performed.">
			use = <"Use as a generic procedure-related archetype to carry information about any procedure or operation performed.  Common examples are: any procedure carried out as a stand-alone activity and not part of a consultation, such as a lumbar puncture or interventional radiology procedure; Endoscopy Report; through to a complete surgical operation report.
The Context component contains an optional unnamed slot that can be used to:
- add optional content during templating to support a use-case specific requirements;
- add EHR model demographic archetypes representing participating parties. While this may not be desired at implementation, this can be useful to demonstrate how demographics may be represented in an implementation ie as a support to clinical content requirements gathering or template review.
The Sections component has been deliberately left unconstrained to maximise re-use of this archetype.">
			keywords = <"report", ...>
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"AuthorDraft">
	other_contributors = <"Heath Frankel, Ocean Informatics, Australia", "Sam Heard, Ocean Informatics, Australia", "Sistine Barretto-Daniels, Ocean Informatics, Australia", "Hugh Leslie, Ocean Informatics, Australia", "Ian McNicoll, Ocean Informatics, Australia">
	other_details = <
		["current_contact"] = <"Heather Leslie, Ocean Informatics, heather.leslie@oceaninformatics.com">
		["MD5-CAM-1.0.1"] = <"A158BB6DE8284F674B65C6D6C0BC5345">
	>

definition
	COMPOSITION[at0000.1] matches {	-- Procedure Report
		category matches {
			DV_CODED_TEXT matches {
				defining_code matches {[openehr::433]}
			}
		}
		context matches {
			EVENT_CONTEXT matches {
				other_context matches {
					ITEM_TREE[at0001] matches {	-- Tree
						items cardinality matches {0..*; unordered} matches {
							ELEMENT[at0002] occurrences matches {0..1} matches {	-- Report ID
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0005] occurrences matches {0..1} matches {	-- Status
								value matches {
									DV_TEXT matches {*}
								}
							}
							allow_archetype CLUSTER occurrences matches {0..*} matches {
								include
									archetype_id/value matches {/.*/}
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
					text = <"Report">
					description = <"Document to communicate information to others, commonly in response to a request from another party.">
				>
				["at0000.1"] = <
					text = <"Procedure Report">
					description = <"Document to communicate information to others about any stand-alone procedure or operation performed.">
				>
				["at0001"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Report ID">
					description = <"Identification information about the report.">
				>
				["at0005"] = <
					text = <"Status">
					description = <"The status of the entire report. Note: This is not the status of any of the report components.">
				>
			>
		>
	>

```
Conclusion (openEhr Archetype)
``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-SECTION.conclusion.v1

concept
	[at0000]	-- Conclusion
language
	original_language = <[ISO_639-1::en]>
	translations = <
		["ru"] = <
			language = <[ISO_639-1::ru]>
			author = <
				["name"] = <"Art Latyp; Латыпов Артур Шамилевич">
				["organisation"] = <"RusBITech РусБИТех, Москва">
			>
			accreditation = <"hmm">
		>
	>
description
	original_author = <
		["name"] = <"Heather Leslie">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"heather.leslie@oceaninformatics.com">
		["date"] = <"11/04/2007">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"Section to bring together all archetypes involved in recording the conclusion in an encounter with a patient">
			use = <"">
			keywords = <"diagnosis", "differential diagnosis">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
		["ru"] = <
			language = <[ISO_639-1::ru]>
			purpose = <"Раздел для объединения всех архетипов, описывающих выводы (заключения) в результате встречи с пациентом ">
			use = <"">
			keywords = <"диагностика", "диагноз", "дифдиагноз", "дифференциальный", "заключение", "вывод">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"AuthorDraft">
	other_contributors = <>
	other_details = <
		["references"] = <"">
	>

definition
	SECTION[at0000] matches {	-- Conclusion
		items cardinality matches {0..*; unordered} matches {
			allow_archetype EVALUATION[at0001] occurrences matches {0..*} matches {
				include
					archetype_id/value matches {/openEHR-EHR-EVALUATION\.differential_diagnosis\.v1|openEHR-EHR-EVALUATION\.problem\.v1|openEHR-EHR-EVALUATION\.problem-diagnosis\.v1/}
			}
		}
	}


ontology
	term_definitions = <
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Conclusion">
					description = <"Section to record conclusions of an encounter with a patient">
				>
				["at0001"] = <
					text = <"Evaluation of a problem, diagnosis etc.">
					description = <"*">
				>
			>
		>
		["ru"] = <
			items = <
				["at0000"] = <
					text = <"Заключение">
					description = <"Раздел для записи заключения (выводов) после встречи с пациентом (осмотра, консультации) ">
				>
				["at0001"] = <
					text = <"Оценка проблемы, диагноз и т.д.">
					description = <"Итоговое мнение врача после осмотра пациента, включая диагноз">
				>
			>
		>
	>

```
Obstetric Summary (openEhr Archetype)
``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-EVALUATION.obstetric_summary.v1

concept
	[at0000]	-- Obstetric summary
language
	original_language = <[ISO_639-1::en]>
description
	original_author = <
		["name"] = <"Sam Heard">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"sam.heard@oceaninformatics.com">
		["date"] = <"2011-02-24">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To record an overview about the obstetric history of a woman for purposes of: providing a snapshot of her obstetric history, reporting to statutory bodies or supporting clinical decision support.">
			use = <"Use to record an overview of the obstetric history of a woman, including a summary of all pregnancies and the associated outcomes or interventions. 

Use this summary as the basis of statutory reporting regarding births.

Use to record the TPAL overview of an obstetric history, if required - the numbers of Term Births (T), Preterm Births (P), Abortions (A) and Living Children (L). Some variations add Gravidity (G) and number of Multiple Births (M).

Some data may be calculated or derived from individual pregnancy records if these are available.">
			keywords = <"obstetric", "pregnancy", "parity", "gravida", "para", "terminations", "miscarriages", "abortions", "spontaneous", "live", "births", "stillbirths", "caesarean", "ectopic", "neonatal", "death", "tubal", "living", "multiple">
			misuse = <"Not for recording summary information about a single pregnancy - use EVALUATION. pregnancy_summary for this purpose.

Not for recording detailed information about each of the individual pregnancies, miscarriages, terminations, or deliveries. This information will be recorded using other specific archetypes as event-based data.">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"AuthorDraft">
	other_contributors = <"Sheryl Alexander, NT Department of Health, Australia", "Margaret Cotter, AMSANT, Australia", "Michelle Dowden, Miwatj Health Ngalkanbuy Health, Australia", "Tim Garden, NTG Department of Health, Australia", "Sam Heard, Ocean Informatics, Australia (Editor)", "Michelle Kealy, Australia", "Bernadette Lack, Deptartment of Health, NT, Australia", "Heather Leslie, Ocean Informatics, Australia (Editor)", "Ian McNicoll, Ocean Informatics UK, United Kingdom", "Jeremy Oats, NT Health, Australia", "Gary Sinclair, NT DoH, Australia", "Cherie Whitbread, Royal Darwin Hospital, Australia", "Jo Wright, NT Dept of Health, Australia">
	other_details = <
		["references"] = <"NEHTA Clinical Knowledge Manager [Internet]. Australia: National eHealth Transition Authority. [Draft EVALUATION archetype] Obstetric Summary; [authored 2011 Feb 24, cited 2011 Aug 17]. Available from http://dcm.nehta.org.au/ckm/OKM.html#showArchetype_1013.1.971_4.">
		["MD5-CAM-1.0.1"] = <"FF7DCD652C6FF29279A87DCDABEB391D">
	>

definition
	EVALUATION[at0000] matches {	-- Obstetric summary
		data matches {
			ITEM_TREE[at0001] matches {	-- Tree
				items cardinality matches {0..*; unordered} matches {
					ELEMENT[at0014] occurrences matches {0..1} matches {	-- Ever Pregnant?
						value matches {
							DV_BOOLEAN matches {
								value matches {True}
							}
						}
					}
					ELEMENT[at0002] occurrences matches {0..1} matches {	-- Gravidity (G)
						value matches {
							DV_COUNT matches {
								magnitude matches {|0..<100|}
							}
						}
					}
					ELEMENT[at0003] occurrences matches {0..1} matches {	-- Parity
						value matches {
							DV_COUNT matches {
								magnitude matches {|>=0|}
							}
						}
					}
					ELEMENT[at0015] occurrences matches {0..1} matches {	-- Term Births (T)
						value matches {
							DV_COUNT matches {*}
						}
					}
					ELEMENT[at0016] occurrences matches {0..1} matches {	-- Preterm Births (P)
						value matches {
							DV_COUNT matches {*}
						}
					}
					ELEMENT[at0017] occurrences matches {0..1} matches {	-- Abortions (A)
						value matches {
							DV_COUNT matches {*}
						}
					}
					ELEMENT[at0004] occurrences matches {0..1} matches {	-- Miscarriages
						value matches {
							DV_COUNT matches {
								magnitude matches {|>=0|}
							}
						}
					}
					ELEMENT[at0005] occurrences matches {0..1} matches {	-- Terminations
						value matches {
							DV_COUNT matches {
								magnitude matches {|>=0|}
							}
						}
					}
					ELEMENT[at0011] occurrences matches {0..1} matches {	-- Ectopic Pregnancies
						value matches {
							DV_COUNT matches {*}
						}
					}
					ELEMENT[at0012] occurrences matches {0..1} matches {	-- Stillbirths
						value matches {
							DV_COUNT matches {*}
						}
					}
					ELEMENT[at0006] occurrences matches {0..1} matches {	-- Live Births
						value matches {
							DV_COUNT matches {
								magnitude matches {|>=0|}
							}
						}
					}
					ELEMENT[at0010] occurrences matches {0..1} matches {	-- Caesarean Sections
						value matches {
							DV_COUNT matches {
								magnitude matches {|>=0|}
							}
						}
					}
					ELEMENT[at0018] occurrences matches {0..1} matches {	-- Multiple Births (M)
						value matches {
							DV_COUNT matches {*}
						}
					}
					ELEMENT[at0007] occurrences matches {0..1} matches {	-- Living Children (L)
						value matches {
							DV_COUNT matches {
								magnitude matches {|>=0|}
							}
						}
					}
				}
			}
		}
		protocol matches {
			ITEM_TREE[at0008] matches {	-- Tree
				items cardinality matches {0..*; unordered} matches {
					ELEMENT[at0009] occurrences matches {0..1} matches {	-- Date Updated
						value matches {
							DV_DATE_TIME matches {*}
						}
					}
					ELEMENT[at0013] occurrences matches {0..1} matches {	-- Stillbirth Definition
						value matches {
							DV_TEXT matches {*}
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
					text = <"Obstetric summary">
					description = <"An overview of the obstetric history of a woman, including a summary of all pregnancies and the associated outcomes or interventions.">
				>
				["at0001"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Gravidity (G)">
					description = <"Number of times a woman has been pregnant, including the current pregnancy, if appropriate.">
				>
				["at0003"] = <
					text = <"Parity">
					description = <"Number of times a woman has given birth after 20 weeks and 0 days gestation.">
					comment = <"Late terminations of pregnancy (after 20 weeks of gestation) are not included. When both 'Term Births (T)' and 'Preterm Births (P)' are recorded, this number should be equal to their sum. Note: Parity is not regarded as the same as the number of infants born - for example, twins would be recorded as one birth event.">
				>
				["at0004"] = <
					text = <"Miscarriages">
					description = <"Number of times a woman has had a miscarriage at less than 20 weeks of gestation.">
					comment = <"Including missed abortions.">
				>
				["at0005"] = <
					text = <"Terminations">
					description = <"Number of times a woman has had a pregnancy terminated, regardless of gestation.">
				>
				["at0006"] = <
					text = <"Live Births">
					description = <"Number of babies born alive.">
				>
				["at0007"] = <
					text = <"Living Children (L)">
					description = <"Number of children who remain alive.">
				>
				["at0008"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0009"] = <
					text = <"Date Updated">
					description = <"The date this summary was last updated.">
				>
				["at0010"] = <
					text = <"Caesarean Sections">
					description = <"Number of Caesarean sections performed.">
				>
				["at0011"] = <
					text = <"Ectopic Pregnancies">
					description = <"Number of ectopic pregnancies.">
				>
				["at0012"] = <
					text = <"Stillbirths">
					description = <"Number of stillbirths.">
					comment = <"Note: Stillbirth definition may be optionally captured in specific data element in Protocol.">
				>
				["at0013"] = <
					text = <"Stillbirth Definition">
					description = <"Definition of stillbirth.">
					comment = <"Maybe useful to record when comparing data from different regions as, as definitions of stillbirth may vary. For example, in Australia a stillborn baby will have a gestation greater than 20 weeks or, if gestation is unknown, weigh more than 400 grams.">
				>
				["at0014"] = <
					text = <"Ever Pregnant?">
					description = <"Has the woman ever been pregnant?">
					comment = <"Record as TRUE if a woman has ever been pregnant. Only useful to record if there is no other detailed data about pregnancies available, or where it may be used to support further knowledge-based activities such as clinical decision support.">
				>
				["at0015"] = <
					text = <"Term Births (T)">
					description = <"Number of infants born on or after 37 weeks of gestation.">
				>
				["at0016"] = <
					text = <"Preterm Births (P)">
					description = <"Number of infants born at less than 37 weeks of gestation.">
				>
				["at0017"] = <
					text = <"Abortions (A)">
					description = <"Number of non-viable pregnancies from all causes and at any gestation, including miscarriages, induced terminations and ectopic pregnancies.">
					comment = <"When all of 'Miscarriages', 'Terminations' and 'Ectopic Pregnancies' are recorded, this number should be equal to their sum.">
				>
				["at0018"] = <
					text = <"Multiple Births (M)">
					description = <"Number of birth events in which more than one fetus has been born.">
				>
			>
		>
	>

```

Substance Use Summary (openEhr Archetype)

``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-EVALUATION.substance_use_summary.v1

concept
	[at0000]	-- Substance Use Summary
language
	original_language = <[ISO_639-1::en]>
	translations = <
		["es-ar"] = <
			language = <[ISO_639-1::es-ar]>
			author = <
				["name"] = <"Dr. Leonardo Der Jachadurian">
				["organisation"] = <"Bitios.com">
			>
			accreditation = <"Medical Doctor (Internal Medicine Specialist)">
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			author = <
				["name"] = <"Mona Saleh">
			>
		>
	>
description
	original_author = <
		["name"] = <"Heather Leslie">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"heather.leslie@oceaninformatics.com">
		["date"] = <"2009-06-21">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"This is a generic archetype used to record an ongoing and persistent summary of the use of any and all substances.">
			use = <"This is a generic archetype used to record an ongoing and persistent summary of the use of any and all substances that have not had specific specialisation archetypes created. The typical use will be related to a summary of use or consumption of substances.">
			keywords = <"consumption", "substance", "use", "usage", "dependence">
			misuse = <"Do not use this archeytpe for recording actual details about the use of the substance and event-related data - this should be captured using the OBSERVATION.substance_use archetype.  Do not use this archetype for recording use or consumption histories for common substances such as tobacco smoking and alcohol.  As substances such as tobacco and alcohol are so commonly consumed, data should be recorded using detailed and specific specialisations of this archetype.">
			copyright = <"© openEHR Foundation">
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			purpose = <"هذا نموضج جنيس (غير محدود الملكية) يستخدم لتسجيل ملخص مستمر عن استخدام أي نوع من أو جميع أنواع المواد">
			use = <"هذا نموضج جنيس (غير محدود الملكية) يستخدم لتسجيل ملخص مستمر عن استخدام أي نوع من أو جميع أنواع المواد التي لا يوجد لها نموذج مخصص. 
و الاستخدام النمطي له متعلق بملخص الاستخدام أو الاستهلاك للمواد.">
			keywords = <"الاستهلاك", "المادة", "الاستخدام", "الاستعمال", "الاعتماد">
			misuse = <"لا يستخدم هذا النموذج لتسجيل التفاصيل الحقيقية عن استخدام المادة أو البيانات المتعلقة بالوقائع - و ينبغي تسجيل ذلك باستخدام نموذج ملاحظة. استخدام المواد

لا تستخدم هذا النموذج لتسجيل تاريخ استخدام أو استهلاك التبغ أو الكحول. 
و حيث إن المواد مثل التبغ أو الكحول هي من المواد المألوفة الاستعمال, فإنه ينبغي تسجيل البيانات الخاصة بها باستخدام تخصيصات تفصيلية و معينة مشتقة من هذا النموذج">
			copyright = <"© openEHR Foundation">
		>
		["es-ar"] = <
			language = <[ISO_639-1::es-ar]>
			purpose = <"Este es un arquetipo genérico usado para registrar el sumario en curso y persistente del uso de cualquier tipo de sustancia.">
			use = <"Este es un arquetipo genérico que se utiliza para registrar un resumen en curso y persistente de la utilización de cualquier sustancia, para la cual no se ha creado ningún arquetipo específico de especialización. El uso típico se relaciona con un resumen de su uso o consumo de sustancias.">
			keywords = <"consumo", "sustancia", "uso", "dependencia">
			misuse = <"No utilice este arquetipo para el registro de detalles actuales sobre el uso de la sustancia y los datos relacionados con eventos. Esto debe ser capturado usando el arquetipo OBSERVATION.substance_use. No utilice este arquetipo para registro de la historia de uso o consumo de las sustancias comunes como el tabaco y el alcohol. Como estas son tan comúnmente consumidas, estos datos deben ser registrados con los arquetipos específicos para ellas.">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"AuthorDraft">
	other_contributors = <"Sam Heard, Ocean Informatics, Australia", "Heather Leslie, Ocean Informatics, Australia (Editor)", "Ian McNicoll, Ocean Informatics, United Kingdom (Editor)">
	other_details = <
		["MD5-CAM-1.0.1"] = <"3DE9486355CA4A3926F27A8B1E8C5CFB">
	>

definition
	EVALUATION[at0000] matches {	-- Substance Use Summary
		data matches {
			ITEM_TREE[at0001] matches {	-- Tree
				items cardinality matches {1..*; unordered} matches {
					ELEMENT[at0005] occurrences matches {0..1} matches {	-- Substance
						value matches {
							DV_TEXT matches {*}
						}
					}
					ELEMENT[at0002] occurrences matches {0..1} matches {	-- Usage Status
						value matches {
							DV_CODED_TEXT matches {
								defining_code matches {
									[local::
									at0003, 	-- Current User
									at0004, 	-- Former Regular User
									at0006, 	-- Former Occasional User
									at0016]	-- Never Used
								}
							}
						}
					}
					CLUSTER[at0007] occurrences matches {1..*} matches {	-- Consumption Summary
						items cardinality matches {1..*; unordered} matches {
							ELEMENT[at0008] occurrences matches {0..1} matches {	-- Form
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0015] occurrences matches {0..1} matches {	-- Method of use
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0009] occurrences matches {0..1} matches {	-- Date commenced
								value matches {
									DV_DATE_TIME matches {*}
								}
							}
							ELEMENT[at0010] occurrences matches {0..1} matches {	-- Age commenced
								value matches {
									DV_DURATION matches {*}
								}
							}
							ELEMENT[at0011] occurrences matches {0..1} matches {	-- Date ceased
								value matches {
									DV_DATE_TIME matches {*}
								}
							}
							ELEMENT[at0012] occurrences matches {0..1} matches {	-- Age ceased
								value matches {
									DV_DURATION matches {*}
								}
							}
							ELEMENT[at0013] occurrences matches {0..1} matches {	-- Comment
								value matches {
									DV_TEXT matches {*}
								}
							}
						}
					}
					allow_archetype CLUSTER[at0014] occurrences matches {0..*} matches {	-- Cessation attempts
						include
							archetype_id/value matches {/openEHR-EHR-CLUSTER\.cessation_attempts\.v1/}
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
					text = <"Substance Use Summary">
					description = <"Generic archetype to record a persisting summary or overview of use or consumption of a defined substance over time.">
				>
				["at0001"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Usage Status">
					description = <"Overview of usage of the substance.">
				>
				["at0003"] = <
					text = <"Current User">
					description = <"Person is a current user of the substance.">
				>
				["at0004"] = <
					text = <"Former Regular User">
					description = <"Person a former or ex-user of the substance on a regular basis.">
				>
				["at0005"] = <
					text = <"Substance">
					description = <"Identification of the substance.">
				>
				["at0006"] = <
					text = <"Former Occasional User">
					description = <"Person a former or ex-user of the substance on a regular basis.">
				>
				["at0007"] = <
					text = <"Consumption Summary">
					description = <"Summary of the pattern of use for any and all forms of the substance, and for multiple episodes of use.">
				>
				["at0008"] = <
					text = <"Form">
					description = <"Identify the form of the substance.">
				>
				["at0009"] = <
					text = <"Date commenced">
					description = <"Date that use of the substance commenced (can be a partial date, such as a year).">
				>
				["at0010"] = <
					text = <"Age commenced">
					description = <"Age that use of the substance commenced.">
				>
				["at0011"] = <
					text = <"Date ceased">
					description = <"Date that use of the substance ceased (can be a partial date, such as a year).">
				>
				["at0012"] = <
					text = <"Age ceased">
					description = <"Age that use of the substance ceased.">
				>
				["at0013"] = <
					text = <"Comment">
					description = <"Comment on the usage of the substance.">
				>
				["at0014"] = <
					text = <"Cessation attempts">
					description = <"Details about attempts to cease use of the substance.">
				>
				["at0015"] = <
					text = <"Method of use">
					description = <"Method of use or consumption of the substance.">
				>
				["at0016"] = <
					text = <"Never Used">
					description = <"Person has never used the substance.">
				>
			>
		>
		["ar-sy"] = <
			items = <
				["at0000"] = <
					text = <"ملخص استخدام المادة">
					description = <"نموذج جنيس (غير محدودو الملكية) لتسجل ملخص مستمر أو نظرة عامة عن استخدام أو استهلاك مادة معينة عبر الزمن.">
				>
				["at0001"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"حالة الاستعمال">
					description = <"نظرة عامة حول استعمال المادة">
				>
				["at0003"] = <
					text = <"مستخدم حالي">
					description = <"الشخص يستخدم المادة حاليا">
				>
				["at0004"] = <
					text = <"كان يستعمله بانتظام سابقا">
					description = <"كان الشخص يستخدم المادة بانتظام في السابق">
				>
				["at0005"] = <
					text = <"المادة">
					description = <"تعريف المادة">
				>
				["at0006"] = <
					text = <"كان يستعمله في مناسبات معينة سابقا">
					description = <"كان الشخص يستعمل المادة في مناسبات معينة سابقا">
				>
				["at0007"] = <
					text = <"ملخص الاستهلاك">
					description = <"ملخص نمط الاستهلاك أي شكل من أو جميع أشكال المادة, و للنوبات المتعددة من الاستخدام">
				>
				["at0008"] = <
					text = <"الشكل">
					description = <"تعريف شكل المادة">
				>
				["at0009"] = <
					text = <"تاريخ البداية">
					description = <"التاريخ الذي تم عنده بداية استخدام المادة - من الممكن أن يكون تاريخا جزئيا, مثل العام الذي تم عنده البداية">
				>
				["at0010"] = <
					text = <"العمر عند بداية الاستخدام">
					description = <"العمر الذي بدأ الشخص عنده تناول المادة">
				>
				["at0011"] = <
					text = <"تاريخ التوقف">
					description = <"التاريخ الذي توقف عنده استخدام المادة - من الممكن أن يكون تاريخا جزئيا, مثل العام الذي توقف عنده الاستخدام">
				>
				["at0012"] = <
					text = <"العمر عند التوقف">
					description = <"التاريخ الذي توقف عنده استخدام المادة">
				>
				["at0013"] = <
					text = <"تعليق">
					description = <"تعليق حول استعمال المادة">
				>
				["at0014"] = <
					text = <"محاولات التوقف">
					description = <"تفاصيل حول محاولات التوقف عن استخدام المادة">
				>
				["at0015"] = <
					text = <"طريقة الاستخدام">
					description = <"طريقة استخدام أو استهلاك المادة">
				>
				["at0016"] = <
					text = <"لم يستعمله أبدا">
					description = <"الشخص لم يستخدم المادة أبداً">
				>
			>
		>
		["es-ar"] = <
			items = <
				["at0000"] = <
					text = <"Sumario del uso de sustancias">
					description = <"Arquetipo genérico para registrar un sumario persistente o visión general del uso o consumo de una sustancia definida, a lo largo del tiempo.">
				>
				["at0001"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Estado de uso">
					description = <"Visión general del uso de la sustancia.">
				>
				["at0003"] = <
					text = <"Usuario actual">
					description = <"La persona es un usuario actual de la sustancia.">
				>
				["at0004"] = <
					text = <"Antiguo usuario regular">
					description = <"Persona que anteriormente fue usuario regular de la sustancia, pero que no la usa actualmente.">
				>
				["at0005"] = <
					text = <"Sustancia">
					description = <"Identificación de la sustancia.">
				>
				["at0006"] = <
					text = <"Antiguo usuario ocasional">
					description = <"Persona que anteriormente fue usuario ocasional de la sustancia, pero que no la usa actualmente.">
				>
				["at0007"] = <
					text = <"Sumario de consumo">
					description = <"Sumario del patrón de uso de todas y cada una de las sustancias y para múltiples episodios de uso.">
				>
				["at0008"] = <
					text = <"Forma">
					description = <"Identificar la forma de la sustancia.">
				>
				["at0009"] = <
					text = <"Fecha de comienzo">
					description = <"Fecha en que comenzó el uso de la sustancia (puede ser una fecha parcial, como ser el año solamente).">
				>
				["at0010"] = <
					text = <"Edad de comienzo">
					description = <"Edad en que comenzó el uso de la sustancia.">
				>
				["at0011"] = <
					text = <"Fecha de cesación">
					description = <"Fecha que el uso de la sustancia cesó (puede ser una fecha parcial, tal como un año).">
				>
				["at0012"] = <
					text = <"Edad de cesación">
					description = <"Edad en la que el uso de la sustancia cesó.">
				>
				["at0013"] = <
					text = <"Comentarios">
					description = <"Comentarios en el uso de la sustancia.">
				>
				["at0014"] = <
					text = <"Intentos de cesación">
					description = <"Detalles acerca de intentos de cesación del uso de la sustancia.">
				>
				["at0015"] = <
					text = <"Método de uso">
					description = <"Método de uso o consumo de la sustancia.">
				>
				["at0016"] = <
					text = <"Nunca fue usuario">
					description = <"Persona que nunca usó la sustancia.">
				>
			>
		>
	>

```

Vaccination Summary (openEhr Archetype)
``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-EVALUATION.vaccination_summary.v1

concept
	[at0000]	-- Vaccination Summary
language
	original_language = <[ISO_639-1::en]>
description
	original_author = <
		["name"] = <"Heather Leslie">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"heather.leslie@oceaninformatics.com">
		["date"] = <"2012-11-23">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To record a summary of the vaccination status for an identified infectious disease or agent.">
			use = <"Use to record a summary statement by a clinician about the vaccination status for an identified infectious disease or agent.

This archetype does not presume any particular schedule or protocol for vaccination.">
			keywords = <"vaccination", "immunisation", "immunization", "summary", "primary", "course", "booster">
			misuse = <"Not to be used to record a status of the subject's possible immune status. Immune status and need for ongoing vaccination or booster will be a clinical decision determined by a number of factors - clinical evidence of previous infection; vaccination status; vaccination history; serology results; contraindications; adverse reactions; and the clinical trigger eg a needle stab injury or exposure to an infectious disease/agent.">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"CommitteeDraft">
	other_contributors = <"Merrilyn Curtis, AnalyzeIT, Australia", "Sistine Barretto-Daniels, Ocean Informatics, Australia">
	other_details = <
		["current_contact"] = <"Heather Leslie, Ocean Informatics, heather.leslie@oceaninformatics.com">
		["MD5-CAM-1.0.1"] = <"252D262E3AD5452A4EADF46B46666452">
	>

definition
	EVALUATION[at0000] matches {	-- Vaccination Summary
		data matches {
			ITEM_TREE[at0001] matches {	-- Tree
				items cardinality matches {1..*; unordered} matches {
					ELEMENT[at0002] occurrences matches {1..*} matches {	-- Infectious Disease or Agent
						value matches {
							DV_TEXT matches {*}
						}
					}
					ELEMENT[at0003] occurrences matches {0..1} matches {	-- Primary Course Status
						value matches {
							DV_CODED_TEXT matches {
								defining_code matches {
									[local::
									at0004, 	-- Not commenced
									at0005, 	-- Incomplete
									at0006, 	-- Complete
									at0007]	-- Indeterminate
								}
							}
						}
					}
					ELEMENT[at0008] occurrences matches {0..1} matches {	-- Date Primary Course Completed
						value matches {
							DV_DATE_TIME matches {*}
						}
					}
					ELEMENT[at0009] occurrences matches {0..1} matches {	-- Date of Last Booster
						value matches {
							DV_DATE_TIME matches {*}
						}
					}
					ELEMENT[at0010] occurrences matches {0..1} matches {	-- Vaccination Status
						value matches {
							DV_CODED_TEXT matches {
								defining_code matches {
									[local::
									at0011, 	-- Vaccination up-to-date
									at0012]	-- Vaccination not up-to-date
								}
							}
						}
					}
				}
			}
		}
		protocol matches {
			ITEM_TREE[at0013] matches {	-- Tree
				items cardinality matches {0..*; unordered} matches {
					ELEMENT[at0014] occurrences matches {0..1} matches {	-- Next Review Due
						value matches {
							DV_DATE_TIME matches {*}
						}
					}
					ELEMENT[at0015] occurrences matches {0..1} matches {	-- Last Updated
						value matches {
							DV_DATE_TIME matches {*}
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
					text = <"Vaccination Summary">
					description = <"Summary of the vaccination status for an identified infectious disease or agent.">
				>
				["at0001"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Infectious Disease or Agent">
					description = <"Identification of the infectious disease or agent.">
					comment = <"There may be multiple diseases or agents that are vaccinated together - for example: diptheria, tetanus and pertussis or measles, mumps and rubella.">
				>
				["at0003"] = <
					text = <"Primary Course Status">
					description = <"Status of the primary course of vaccinations.">
				>
				["at0004"] = <
					text = <"Not commenced">
					description = <"Primary course was not commenced.">
				>
				["at0005"] = <
					text = <"Incomplete">
					description = <"Primary course was commenced but not completed.">
				>
				["at0006"] = <
					text = <"Complete">
					description = <"Primary course was completed.">
				>
				["at0007"] = <
					text = <"Indeterminate">
					description = <"The available information is inadequate to determin the status of the primary course.">
				>
				["at0008"] = <
					text = <"Date Primary Course Completed">
					description = <"The date on which the primary  (or catch-up) course of vaccines was completed.">
				>
				["at0009"] = <
					text = <"Date of Last Booster">
					description = <"The date of which the last vaccine booster was administered.">
				>
				["at0010"] = <
					text = <"Vaccination Status">
					description = <"An assertion about whether the vaccination course is up-to-date.">
				>
				["at0011"] = <
					text = <"Vaccination up-to-date">
					description = <"The vaccination course is up-to-date.">
				>
				["at0012"] = <
					text = <"Vaccination not up-to-date">
					description = <"The vaccination course is not up-to-date.">
				>
				["at0013"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0014"] = <
					text = <"Next Review Due">
					description = <"The date at which the immunisation summary should be reviewed and possibly updated.">
				>
				["at0015"] = <
					text = <"Last Updated">
					description = <"The date on which the immunisation summary was last updated.">
				>
			>
		>
	>

```

Referral Detail (openEhr Archetype)
``` Archetype
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
