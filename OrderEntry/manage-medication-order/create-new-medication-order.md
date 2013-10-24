#####Use Case ID: UC-OES01
#####Use Case Name: Create Medication Order

**Level:**                     User Level Goal

**Primary Actors:**            Doctor/ Physician/ Clinician 

**Stakeholders:**              Order Entry User

**Purpose:**                   The main intent of this use case is the creation of new medication order.

**Pre Condition:**             Doctor/ Physician/ Clinician must be identified and authenticated.  

**Post Condition:**            New medication order is created successfully without any conflicts.

**Frequency of Occurrence:**   High

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Create Medication Order)**

1.	Physician selects the new medication order option and selects MRNO (or any other identification criteria) from the list.
2.	System shows the relevant data including weight of the patient, allergies and history.
3.	Physician specifies symptoms, signs, and investigations.
4.	System will perform the following action:  
  * It will show the list of medication,  
  * It will calculate the dosage of medication based on body mass index, age or defined medication protocols.
5.	Physician selects the medication from the specified list and specifies the frequency and route of medication.
6.	System performs following actions:  
  * validate information,  
  * Investigate for any drug or allergy interactions.
7.	Physician will save the medication order.
8.	System will perform following actions:  
  * It will record the time stamp of ordered medication,  
  * It will set medication status to active,  
  * It will send order to pharmacy along with order ID.

__________________________________________________________
**Alternate Flows** 

**Alt-1: If medication not exist in list**

1.	Physician will search medication by its name, code or brand name.
2.	System will show the list of medications.
3.	Physician will select required medication
4.	The steps 6 to 8 in main scenario of events are then executed.

**Alt-2: Verbal Order**

1.	Repeat step 1 and 2 from the main scenario.
2.	Physician prescribes medication verbally and system records it.
3.	System identifies medication keywords out of recorded order.
4.	Physician performs verification read back.
5.	The steps 6 to 8 in main scenario of events are then executed.

**Alt-3: Co-Signature Configuration**

1.	Repeat step 1 to 6 from the main scenario.
2.	Physician configures the medication order for verification from another physician.
3.	System notifies the physician who has to co-sign the order.
4.	Physician verifies and signs the medication order.
5.	System responds back to initiating physician.
6.	The step 7 and 8 in main scenario of events are then executed.

**Alt-4: Interaction Checking**

1.	Repeat step 1 to 6 from the main scenario.
2.	Physician review the system response of interaction checking and take actions as: 
  * In case any drug or allergy interaction reveals, it sort some other alternate medication and proceed with normal order flow if find no drug to drug or drug to allergy interaction, 
  * In case absence of any drug to drug or drug to allergy interaction, the physician proceeds with normal flow of medication order, 
  * System will set the medication status to active.
3.	The step 7 and 8 in main scenario of events are then executed.

_______________________________________________________________
**Open Issues**

Verbal Language Supprt
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Pharmacy):**

DORX_ST000300UV01, DORX_ST060020UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

IP 08.02, IP 10.03, IP 10.04, IP 10.08, IP 10.11, IP 10.14, IP 10.15, IP 10.26, IP 10.27, FN 07.03, FN 07.04, FN 07.06

_______________________________________________________________
**Reference Hl7 RMIM (Domain: Pharmacy):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![image](https://f.cloud.github.com/assets/4283040/1379357/3c8baebe-3aec-11e3-9217-6f37231a9187.png)
![image](https://f.cloud.github.com/assets/4283040/1379360/4573a586-3aec-11e3-9dde-78e2b8c3a062.png)

**Contradiction Checking**

![image](https://f.cloud.github.com/assets/4283040/1379362/55798de2-3aec-11e3-86a9-04b231d1c9d4.png)

_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![image](https://f.cloud.github.com/assets/4283040/1379365/69e4763e-3aec-11e3-9172-27a0500baa55.png)

**Contradiction Checking**

![image](https://f.cloud.github.com/assets/4283040/1379366/75c63fa0-3aec-11e3-9eb4-ae595744ea7a.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

Section Level Template **"Medications Section (entries optional) (V2)"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

Procedure (openEhr Archetype)

**Prescription**

```Archetype
archetype (adl_version=1.4)
	openEHR-EHR-COMPOSITION.prescription.v1

concept
	[at0000]	-- Prescription
language
	original_language = <[ISO_639-1::en]>
description
	original_author = <
		["name"] = <"Sam Heard">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"sam.heard@oceaninformatics.com">
		["date"] = <"23/03/2006">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"A composition for transfering medication orders to the pharmacy.">
			use = <"This composition is only required for transfer of medications to the pharmacy.">
			keywords = <"medication", "prescribe", "order">
			misuse = <"Medication orders, as instructions, have a prescribe action that records prescription and communication to the pharmacy. This composition is only required if the medication orders are required to be transmitted within openEHR to the pharmacy.">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"AuthorDraft">
	other_contributors = <>
	other_details = <
		["references"] = <"">
	>

definition
	COMPOSITION[at0000] matches {	-- Prescription
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
							ELEMENT[at0002] occurrences matches {0..1} matches {	-- Prescription category
								value matches {
									DV_CODED_TEXT matches {
										defining_code matches {
											[local::
											at0003, 	-- PBS
											at0004, 	-- RPBS
											at0005]	-- Private
										}
									}
								}
							}
						}
					}
				}
			}
		}
		content cardinality matches {0..*; unordered} matches {
			allow_archetype SECTION[at0006] matches {
				include
					archetype_id/value matches {/openEHR-EHR-SECTION\.medications\.v1/}
				exclude
					archetype_id/value matches {/.*/}
			}
		}
	}


ontology
	term_definitions = <
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Prescription">
					description = <"Set of medication orders communicated to pharmacy">
				>
				["at0001"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Prescription category">
					description = <"Australian prescription category">
				>
				["at0003"] = <
					text = <"PBS">
					description = <"Australian pharmaceutical benefits scheme">
				>
				["at0004"] = <
					text = <"RPBS">
					description = <"Repatriation pharmaceutical benefits scheme (ADF)">
				>
				["at0005"] = <
					text = <"Private">
					description = <"Entire cost met by patient or agent">
				>
				["at0006"] = <
					text = <"Section: Medications">
					description = <"*">
				>
			>
		>
	>
```

**Adverse Reaction**

```
archetype (adl_version=1.4)
	openEHR-EHR-EVALUATION.adverse_reaction.v1
concept
	[at0000]	-- Adverse Reaction
language
	original_language = <[ISO_639-1::en]>
	translations = <
		["de"] = <
			language = <[ISO_639-1::de]>
			author = <
				["name"] = <"Jasmin Buck, Sebastian Garde">
				["organisation"] = <"University of Heidelberg, Central Queensland University">
			>
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			author = <
				["name"] = <"Mona Saleh">
				["email"] = <"monasaleh01@live.com">
			>
		>
	>
description
	original_author = <
		["name"] = <"Heather Leslie">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"heather.leslie@oceaninformatics.com">
		["date"] = <"2010-11-08">
	>
	details = <
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			purpose = <"*To record information about any harmful, desirable or unexpected reaction to a substance or agent, including:
- immune mediated reactions Types I-IV (including true allergic reactions and hypersensitivities), and 
- non-immune mediated reactions (including pseudoallergic reactions, side effects, intolerances, drug toxicities (eg Gentamicin), drug-drug interactions, food-drug interactions, drug-disease interactions and idiosyncratic reactions).

To record information about previous exposures to a substance, allowing a persisting and evolving summary of adverse reaction events to build up over time.

To record additional information that will support and inform a clinical assessment of the propensity of an individual to experience an adverse reaction if exposed to a specific substance, class of substance or agent in the future.(en)">
			use = <"*Use to record all information about the presence of adverse reaction/s (including an allergic reaction/s)  to a substance to support direct clinical care of an individual; as part of a managed Adverse Reaction list; to enable safe exchange of information about adverse reactions; and to assist computerised knowledge-based activities such as clinical decision support and alerts.

Use to provide a single place within the health record to record a range of clinical statements about adverse reactions, including:  
-  record cumulative information about each exposure to a known substance, class of substance or agent; and 
-  record a clinician's opinion that administration of, or exposure to, a substance or agent is absolutely contraindicated.

This archetype has been designed to allow recording of information about a more generic substance, class of substance or agent, and then allow more specific details to be recorded including identification of the specific substance on a per exposure basis, including links to other parts of the health record where further details may be located. Note:  it is possible on second or subsequent exposures to a previously identified substance for a reaction not to occur and this archetype allows for these events to be closely linked in a way that will assist in determining if the adverse reaction has been incorrectly identified.

Design of this archetype has been deliberatly focused on identifying a pragmatic, core data set that will be suitable for most common use clinical scenarios but permits extension of the model when additional detail is required through incorporation of additional archetypes in the 'Additional Reaction Detail', 'Additional Exposure Detail', and 'Reporting Details' slots. Examples of clinical situations where the extension will be required are for a detailed immunology assessment, for reporting to regulatory bodies or clinical trial use.

A data element for Substance Category has not been modelled as this should be able to be derived from any coded entry for Substance/Agent and be used in decision support activities. A coded Category is not adequate to support decision support if Substance/Agent is only entered via free text.

The act of recording an adverse reaction in the health record implies there is a potential hazard for the individual if they are exposed to the same substance/agent in the future - a relative contraindication. If a clinician considers that it is not safe for the individual to be deliberately re-exposed to the substance/agent again, for example, following a manifestation of anaphylaxis, the 'Absolute contraindication' data flag should be recorded as ‘True’. Note: Conversely, a statement about ‘Severity’ of propensity (with possible values such as Mild, Moderate and Severe) has deliberately not been modelled explicitly. Predicting or estimating the grade of possible severity of a future reaction is not safe to record and persist in data, except where it is absolutely clear that the risk of deliberate re-exposure is unacceptable and highly likely to cause significant harm, such as a previous manifestation of anaphylaxis, and in this case the ‘Absolute contraindication’ data flag should be used. 

Valuable first-level information that could be presented to the clinician when they need to assess propensity for future reactions are:
- statements about previous clinical manifestations following exposure,
- source of the information/reporter, and
- a flag for absolute contra-indication. 
Second-level information can be drawn from each exposure event and links to additional detailed information such as history, examination and diagnoses stored elsewhere in the record, if it is available.

A formal Adverse Reaction Report to regulatory bodies is a document that will contain a broad range of information in addition to the specific details of the adverse reaction. The report will be comprised of this Adverse Reaction archetype plus a variable number of others - for example, demographics, weight, medication and problem/diagnosis.(en)">
			keywords = <"*reaction(en)", "*allergy(en)", "*allergic(en)", "*adverse(en)", "*event(en)", "*effect(en)", "*sensitivity(en)", "*intolerance(en)", "*hypersensitivity(en)", "*side effect(en)", "*toxicity(en)", "*interaction(en)", "*drug(en)", "*food(en)", "*medication(en)", "*agent(en)", "*substance(en)", "*immune(en)", "*non-immune(en)", "*chemical(en)">
			misuse = <"*Not to be used for recording the absence (or negative presence) of a reaction to 'any substances' or to identified substances – use the EVALUATION.exclusion family of archetypes to express a positive statement of Adverse Reaction exclusion. 

Not to be used for recording that no information was able to be obtained about the Adverse Reaction status of a patient. Use the EVALUATION.absent_information family of archetypes to record that a positive statement that information was not able to be obtained, for example, if a non-cooperative patient refuses to answer questions.

Not to be used to record adverse events, including failures of clinical process, interventions or products. For example: abnormal use or mistakes/errors made in administration of an agent or substance; mislabelling; harm or injury caused by an intervention or procedure; overdose etc.

Not to be used for recording alerts.

Not to be used for recording failed therapy.(en)">
			copyright = <"© openEHR Foundation">
		>
		["de"] = <
			language = <[ISO_639-1::de]>
			purpose = <"*To record information about any harmful, desirable or unexpected reaction to a substance or agent, including:
- immune mediated reactions Types I-IV (including true allergic reactions and hypersensitivities), and 
- non-immune mediated reactions (including pseudoallergic reactions, side effects, intolerances, drug toxicities (eg Gentamicin), drug-drug interactions, food-drug interactions, drug-disease interactions and idiosyncratic reactions).

To record information about previous exposures to a substance, allowing a persisting and evolving summary of adverse reaction events to build up over time.

To record additional information that will support and inform a clinical assessment of the propensity of an individual to experience an adverse reaction if exposed to a specific substance, class of substance or agent in the future.(en)">
			use = <"*Use to record all information about the presence of adverse reaction/s (including an allergic reaction/s)  to a substance to support direct clinical care of an individual; as part of a managed Adverse Reaction list; to enable safe exchange of information about adverse reactions; and to assist computerised knowledge-based activities such as clinical decision support and alerts.

Use to provide a single place within the health record to record a range of clinical statements about adverse reactions, including:  
-  record cumulative information about each exposure to a known substance, class of substance or agent; and 
-  record a clinician's opinion that administration of, or exposure to, a substance or agent is absolutely contraindicated.

This archetype has been designed to allow recording of information about a more generic substance, class of substance or agent, and then allow more specific details to be recorded including identification of the specific substance on a per exposure basis, including links to other parts of the health record where further details may be located. Note:  it is possible on second or subsequent exposures to a previously identified substance for a reaction not to occur and this archetype allows for these events to be closely linked in a way that will assist in determining if the adverse reaction has been incorrectly identified.

Design of this archetype has been deliberatly focused on identifying a pragmatic, core data set that will be suitable for most common use clinical scenarios but permits extension of the model when additional detail is required through incorporation of additional archetypes in the 'Additional Reaction Detail', 'Additional Exposure Detail', and 'Reporting Details' slots. Examples of clinical situations where the extension will be required are for a detailed immunology assessment, for reporting to regulatory bodies or clinical trial use.

A data element for Substance Category has not been modelled as this should be able to be derived from any coded entry for Substance/Agent and be used in decision support activities. A coded Category is not adequate to support decision support if Substance/Agent is only entered via free text.

The act of recording an adverse reaction in the health record implies there is a potential hazard for the individual if they are exposed to the same substance/agent in the future - a relative contraindication. If a clinician considers that it is not safe for the individual to be deliberately re-exposed to the substance/agent again, for example, following a manifestation of anaphylaxis, the 'Absolute contraindication' data flag should be recorded as ‘True’. Note: Conversely, a statement about ‘Severity’ of propensity (with possible values such as Mild, Moderate and Severe) has deliberately not been modelled explicitly. Predicting or estimating the grade of possible severity of a future reaction is not safe to record and persist in data, except where it is absolutely clear that the risk of deliberate re-exposure is unacceptable and highly likely to cause significant harm, such as a previous manifestation of anaphylaxis, and in this case the ‘Absolute contraindication’ data flag should be used. 

Valuable first-level information that could be presented to the clinician when they need to assess propensity for future reactions are:
- statements about previous clinical manifestations following exposure,
- source of the information/reporter, and
- a flag for absolute contra-indication. 
Second-level information can be drawn from each exposure event and links to additional detailed information such as history, examination and diagnoses stored elsewhere in the record, if it is available.
A formal Adverse Reaction Report to regulatory bodies is a document that will contain a broad range of information in addition to the specific details of the adverse reaction. The report will be comprised of this Adverse Reaction archetype plus a variable number of others - for example, demographics, weight, medication and problem/diagnosis.(en)">
			keywords = <"*reaction(en)", "*allergy(en)", "*allergic(en)", "*adverse(en)", "*event(en)", "*effect(en)", "*sensitivity(en)", "*intolerance(en)", "*hypersensitivity(en)", "*side effect(en)", "*toxicity(en)", "*interaction(en)", "*drug(en)", "*food(en)", "*medication(en)", "*agent(en)", "*substance(en)", "*immune(en)", "*non-immune(en)", "*chemical(en)">
			misuse = <"*Not to be used for recording the absence (or negative presence) of a reaction to 'any substances' or to identified substances – use the EVALUATION.exclusion family of archetypes to express a positive statement of Adverse Reaction exclusion.
Not to be used for recording that no information was able to be obtained about the Adverse Reaction status of a patient. Use the EVALUATION.absent_information family of archetypes to record that a positive statement that information was not able to be obtained, for example, if a non-cooperative patient refuses to answer questions.
Not to be used to record adverse events, including failures of clinical process, interventions or products. For example: abnormal use or mistakes/errors made in administration of an agent or substance; mislabelling; harm or injury caused by an intervention or procedure; overdose etc.
Not to be used for recording alerts.
Not to be used for recording failed therapy.(en)">
			copyright = <"© openEHR Foundation">
		>
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"To record information about any harmful, desirable or unexpected reaction to a substance or agent, including:
- immune mediated reactions Types I-IV (including true allergic reactions and hypersensitivities), and 
- non-immune mediated reactions (including pseudoallergic reactions, side effects, intolerances, drug toxicities (eg Gentamicin), drug-drug interactions, food-drug interactions, drug-disease interactions and idiosyncratic reactions).
To record information about previous exposures to a substance, allowing a persisting and evolving summary of adverse reaction events to build up over time.
To record additional information that will support and inform a clinical assessment of the propensity of an individual to experience an adverse reaction if exposed to a specific substance, class of substance or agent in the future.">
			use = <"Use to record all information about the presence of adverse reaction/s (including an allergic reaction/s)  to a substance to support direct clinical care of an individual; as part of a managed Adverse Reaction list; to enable safe exchange of information about adverse reactions; and to assist computerised knowledge-based activities such as clinical decision support and alerts.
Use to provide a single place within the health record to record a range of clinical statements about adverse reactions, including:  
-  record cumulative information about each exposure to a known substance, class of substance or agent; and 
-  record a clinician's opinion that administration of, or exposure to, a substance or agent is absolutely contraindicated.
This archetype has been designed to allow recording of information about a more generic substance, class of substance or agent, and then allow more specific details to be recorded including identification of the specific substance on a per exposure basis, including links to other parts of the health record where further details may be located. Note:  it is possible on second or subsequent exposures to a previously identified substance for a reaction not to occur and this archetype allows for these events to be closely linked in a way that will assist in determining if the adverse reaction has been incorrectly identified.
Design of this archetype has been deliberatly focused on identifying a pragmatic, core data set that will be suitable for most common use clinical scenarios but permits extension of the model when additional detail is required through incorporation of additional archetypes in the 'Additional Reaction Detail', 'Additional Exposure Detail', and 'Reporting Details' slots. Examples of clinical situations where the extension will be required are for a detailed immunology assessment, for reporting to regulatory bodies or clinical trial use.
A data element for Substance Category has not been modelled as this should be able to be derived from any coded entry for Substance/Agent and be used in decision support activities. A coded Category is not adequate to support decision support if Substance/Agent is only entered via free text.
The act of recording an adverse reaction in the health record implies there is a potential hazard for the individual if they are exposed to the same substance/agent in the future - a relative contraindication. If a clinician considers that it is not safe for the individual to be deliberately re-exposed to the substance/agent again, for example, following a manifestation of anaphylaxis, the 'Absolute contraindication' data flag should be recorded as ‘True’. Note: Conversely, a statement about ‘Severity’ of propensity (with possible values such as Mild, Moderate and Severe) has deliberately not been modelled explicitly. Predicting or estimating the grade of possible severity of a future reaction is not safe to record and persist in data, except where it is absolutely clear that the risk of deliberate re-exposure is unacceptable and highly likely to cause significant harm, such as a previous manifestation of anaphylaxis, and in this case the ‘Absolute contraindication’ data flag should be used. 
Valuable first-level information that could be presented to the clinician when they need to assess propensity for future reactions are:
- statements about previous clinical manifestations following exposure,
- source of the information/reporter, and
- a flag for absolute contra-indication. 
Second-level information can be drawn from each exposure event and links to additional detailed information such as history, examination and diagnoses stored elsewhere in the record, if it is available.
A formal Adverse Reaction Report to regulatory bodies is a document that will contain a broad range of information in addition to the specific details of the adverse reaction. The report will be comprised of this Adverse Reaction archetype plus a variable number of others - for example, demographics, weight, medication and problem/diagnosis.">
			keywords = <"reaction", "allergy", "allergic", "adverse", "event", "effect", "sensitivity", "intolerance", "hypersensitivity", "side effect", "toxicity", "interaction", "drug", "food", "medication", "agent", "substance", "immune", "non-immune", "chemical">
			misuse = <"Not to be used for recording the absence (or negative presence) of a reaction to 'any substances' or to identified substances – use the EVALUATION.exclusion family of archetypes to express a positive statement of Adverse Reaction exclusion.
Not to be used for recording that no information was able to be obtained about the Adverse Reaction status of a patient. Use the EVALUATION.absent_information family of archetypes to record that a positive statement that information was not able to be obtained, for example, if a non-cooperative patient refuses to answer questions.
Not to be used to record adverse events, including failures of clinical process, interventions or products. For example: abnormal use or mistakes/errors made in administration of an agent or substance; mislabelling; harm or injury caused by an intervention or procedure; overdose etc.
Not to be used for recording alerts.
Not to be used for recording failed therapy.">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"CommitteeDraft">
	other_contributors = <"John Bennett, NEHTA, Australia", "Sharmila Biswas, Dr Sharmila Biswas GP, Australia", "Rong Chen, Cambio Healthcare System, Sweden", "Stephen Chu, NEHTA, Australia (Editor)", "Matthew Cordell, NEHTA, Australia", "David Evans, Queensland Health, Australia", "Shahla Foozonkhah, Ocean Informatics, Australia", "Joanne Foster, School of Nursing & Midwifery, QLD University of Technology & Nursing Informatics Australia, Australia", "Jacquie Garton-Smith, Royal Perth Hospital and DoHWA, Australia", "Sarah Gaunt, NEHTA, Australia", "Andrew Goodchild, NEHTA, Australia", "Heather Grain, Llewelyn Grain Informatics, Australia", "Trina Gregory, cpc, Australia", "Grahame Grieve, Australia", "Sam Heard, Ocean Informatics, Australia", "Andrew James, University of Toronto, Canada", "Julie James, Blue Wave Informatics LLP, United Kingdom", "Ivor Jones, Queensalnd Helath, Australia", "Mary Kelaher, NEHTA, Australia", "Diane Kirkham, NEHTA, Australia", "Robert L'egan, NEHTA, Australia", "Jobst Landgrebe, ii4sm, Switzerland", "Heather Leslie, Ocean Informatics, Australia (Editor)", "Hugh Leslie, Ocean Informatics, Australia", "Rikard Lovstrom, Swedish Medical Association, Sweden", "Sarah Mahoney, Australia", "Mike Martyn, The Hobart Anaesthetic Group, Australia", "David McKillop, NEHTA, Australia", "Ian McNicoll, Ocean Informatics, United Kingdom", "Chris Mitchell, RACGP, Australia", "Stewart Morrison, NEHTA, Australia", "Jörg Niggemann, Compugroup, Germany", "Chris Pearce, Melbourne East GP Network, Australia", "General Practice Computing Group, Australia", "Camilla Preeston, Royal Australian College of General Practitioners, Australia", "Margaret Prichard, NEHTA, Australia", "Jodie Pycroft, Adelaide Northern Division of General Practice Ltd, Australia", "Cathy Richardson, NEHTA, Australia", "Robyn Richards, NEHTA - Clinical Terminology, Australia", "Thilo Schuler, Australia", "Peter Scott, Medical Objects, Australia", "Elena Shabanova, UMMSSOft, Russian Federation", "Elizabeth Stanick, Hobart Anaesthetic Group, Australia", "Hwei-Yee Tai, Tan Tock Seng Hospital, Singapore", "John Taylor, NEHTA, Australia", "Gordon Tomes, Australian Institute of Health and Welfare, Australia", "Richard Townley-O'Neill, NEHTA, Australia", "Kylie Young, The Royal Australian College of General Practitioners, Australia">
	other_details = <
		["references"] = <"Adverse Reaction, draft archetype, National eHealth Transition Authority [Internet]. NEHTA Clinical Knowledge Manager. Authored: 08 Nov 2010. Available at: http://dcm.nehta.org.au/ckm/OKM.html#showarchetype_1013.1.868_7 (accessed Jan 16, 2012).
Allergy, clinical element model, GE/Intermountain Healthcare. Clinical Element Model Search. Available at: http://intermountainhealthcare.org/cem/Pages/Detail.aspx?NCID=520861661&k=allergy (accessed Jan 16, 2012).
Edwards IR, Aronson JK. Adverse drug reactions: definitions, diagnosis, and management. Lancet. 2000 Oct 7;356(9237):1255-9. PubMed PMID: 11072960. 
Horsfield P, Sibeko S. Representation in Electronic Patient Records of Allergic Reactions, Adverse Reactions, and Intolerance of Pharmaceutical Products [Internet]. London, UK: National Health Service; 2006 Sep 07 [cited 2011 Jun 21]; Available at https://svn.connectingforhealth.nhs.uk/svn/public/nhscontentmodels/TRUNK/ref/NPfIT/Allergy_ADR_Intolerance%20v%201.2Final.doc.
Long R, Bentley S. SCG Guidance on the Representation of Allergies and Adverse Reaction Information Using NHS Message Templates [Internet]. London, UK: National Health Service; 2008 Apr 30 [cited 2011 Jun 21]; Available at http://www.connectingforhealth.nhs.uk/systemsandservices/data/scg/scg0001.pdf.
Microsoft. Design Guidance: Displaying Adverse Drug Reaction Risks [Internet]. 2009 January 28 [cited 2011 Jun 21]; Available at www.mscui.net/DesignGuide/DisplayingAllergies.aspx.

Microsoft. Design Guidance: Recording Adverse Drug Reaction Risks [Internet]. 2009 March 27 [cited 2011 Jun 21]; Available at www.mscui.net/DesignGuide/RecordingAllergies.aspx.

Mosby. Mosby's Pocket Dictionary of Medicine, Nursing and Health Professions. 6th Edition. USA: Mosby Elsevier; 2010
National E-Health Transition Authority. Adverse Reactions (Data Specifications) Version 1.1 [Internet]. Sydney, Australia: NEHTA; 2008 Feb 29 [cited 2011 Jun 21]; Available at http://www.nehta.gov.au/component/docman/doc_download/453-adverse-reaction-data-specification-v11.
Riedl MA, Casillas AM. Adverse drug reactions: types and treatment options. Am Fam Physician. 2003 Nov 1;68(9):1781-90. Review. PubMed PMID: 14620598.
Royal Australian College of General Practitioners. Fact Sheet: Allergies & Adverse Reactions (Draft). 2010.
Thien FC. Drug hypersensitivity. Med J Aust. 2006 Sep 18;185(6):333-8. Review. PubMed PMID: 16999678.">
		["MD5-CAM-1.0.1"] = <"260699D2EFDE4F7C7BC3C6C501A51A61">
	>
definition
	EVALUATION[at0000] matches {	-- Adverse Reaction
		data matches {
			ITEM_TREE[at0001] matches {	-- Tree
				items cardinality matches {1..*; unordered} matches {
					ELEMENT[at0002] matches {	-- Substance/Agent
						value matches {
							DV_TEXT matches {*}
						}
					}
					ELEMENT[at0004] occurrences matches {0..1} matches {	-- Absolute Contraindication?
						value matches {
							DV_BOOLEAN matches {
								value matches {True}
							}
						}
					}
					ELEMENT[at0049] occurrences matches {0..1} matches {	-- Future Use
						value matches {
							DV_TEXT matches {*}
						}
					}
					ELEMENT[at0006] occurrences matches {0..1} matches {	-- Overall Comment
						value matches {
							DV_TEXT matches {*}
						}
					}
					CLUSTER[at0009] occurrences matches {0..*} matches {	-- Reaction Event
						items cardinality matches {1..*; unordered} matches {
							ELEMENT[at0010] occurrences matches {0..1} matches {	-- Specific Substance/Agent
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0011] occurrences matches {0..*} matches {	-- Manifestation
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0016] occurrences matches {0..1} matches {	-- Reaction Type
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0021] occurrences matches {0..1} matches {	-- Certainty
								value matches {
									DV_CODED_TEXT matches {
										defining_code matches {
											[local::
											at0022, 	-- Suspected
											at0023, 	-- Probable
											at0024]	-- Confirmed
										}
									}
								}
							}
							ELEMENT[at0012] occurrences matches {0..1} matches {	-- Reaction Description
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0027] occurrences matches {0..1} matches {	-- Onset of Reaction
								value matches {
									DV_DATE_TIME matches {*}
								}
							}
							ELEMENT[at0028] occurrences matches {0..1} matches {	-- Duration of Reaction
								value matches {
									DV_DURATION matches {*}
								}
							}
							allow_archetype CLUSTER[at0029] occurrences matches {0..*} matches {	-- Additional Reaction Detail
								include
									archetype_id/value matches {/openEHR-EHR-CLUSTER\.anatomical_location(-[a-zA-Z0-9_]+)*\.v1/}
							}
							ELEMENT[at0018] occurrences matches {0..1} matches {	-- Exposure Description
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0020] occurrences matches {0..1} matches {	-- Earliest Exposure
								value matches {
									DV_DATE_TIME matches {*}
								}
							}
							ELEMENT[at0025] occurrences matches {0..1} matches {	-- Duration of Exposure
								value matches {
									DV_DURATION matches {*}
								}
							}
							allow_archetype CLUSTER[at0019] occurrences matches {0..*} matches {	-- Additional Exposure Detail
								include
									archetype_id/value matches {/openEHR-EHR-CLUSTER\.amount(-[a-zA-Z0-9_]+)*\.v1|openEHR-EHR-CLUSTER\.medication_admin(-[a-zA-Z0-9_]+)*\.v1|openEHR-EHR-CLUSTER\.timing(-[a-zA-Z0-9_]+)*\.v1/}
							}
							ELEMENT[at0040] occurrences matches {0..1} matches {	-- Clinical Management Description
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0031] occurrences matches {0..*} matches {	-- Multimedia
								value matches {
									DV_MULTIMEDIA matches {
										media_type matches {[openEHR::]}
									}
								}
							}
							allow_archetype CLUSTER[at0041] occurrences matches {0..*} matches {	-- Reporting Details
								include
									archetype_id/value matches {/.*/}
							}
							ELEMENT[at0032] occurrences matches {0..1} matches {	-- Reaction Comment
								value matches {
									DV_TEXT matches {*}
								}
							}
						}
					}
				}
			}
		}
		protocol matches {
			ITEM_TREE[at0042] matches {	-- Tree
				items cardinality matches {0..*; unordered} matches {
					ELEMENT[at0044] occurrences matches {0..1} matches {	-- Reaction Reported?
						value matches {
							DV_BOOLEAN matches {
								value matches {True, False}
							}
						}
					}
					ELEMENT[at0048] occurrences matches {0..1} matches {	-- Report Comment
						value matches {
							DV_TEXT matches {*}
						}
					}
					ELEMENT[at0045] occurrences matches {0..*} matches {	-- Adverse Reaction Report
						value matches {
							DV_URI matches {*}
						}
					}
					ELEMENT[at0047] occurrences matches {0..1} matches {	-- Supporting Clinical Record Information
						value matches {
							DV_EHR_URI matches {*}
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
					text = <"التفاعل الضائر">
					description = <"*A harmful or undesirable, unexpected effect associated with exposure to any substance or agent, including food, plants, animals, venom from animal stings, or a medication at therapeutic or sub-therapeutic doses.(en)">
				>
				["at0001"] = <
					text = <"*Tree(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"*Substance/Agent(en)">
					description = <"*Identification of a substance, agent, or a class of substance, that is considered to be responsible for the Adverse Reaction.(en)">
					comment = <"*Substance/Agent should be coded with a terminology, where possible.(en)">
				>
				["at0004"] = <
					text = <"*Absolute Contraindication?(en)">
					description = <"*Is administration of this Substance/Agent absolutely contraindicated in this individual?(en)">
					comment = <"*A flag indicating that a clinician has identified a propensity for a serious reaction upon further exposure to the Substance/Agent. Record as True if the clinician recommends that deliberate or voluntary exposure to, or administration of, the Substance/Agent should be prevented in future.(en)">
				>
				["at0006"] = <
					text = <"*Overall Comment(en)">
					description = <"*Additional narrative about the Adverse Reaction as a whole, not captured in other fields.(en)">
				>
				["at0009"] = <
					text = <"*Reaction Event(en)">
					description = <"*Details about each Adverse Reaction Event.(en)">
				>
				["at0010"] = <
					text = <"*Specific Substance/Agent(en)">
					description = <"*Specific identification of the actual Substance/Agent considered to be responsible for the Adverse Reaction event.(en)">
					comment = <"*Coding of the specific Substance/Agent with a terminology is preferred, where possible. For example, a medication trade name or identification of a specific food.(en)">
				>
				["at0011"] = <
					text = <"*Manifestation(en)">
					description = <"*Clinical manifestation of the Adverse Reaction expressed as a single word, phrase or brief description, e.g. nausea or rash.(en)">
					comment = <"*Manifestation should be coded with a terminology, where possible. The values entered here may be used to display on an application screen as part a list of adverse reactions, as recommended in the NHS CUI guidelines.(en)">
				>
				["at0012"] = <
					text = <"*Reaction Description(en)">
					description = <"*Narrative description of the Adverse Reaction.(en)">
				>
				["at0016"] = <
					text = <"فئة التفاعل">
					description = <"*The type of Adverse Reaction as determined by the clinician.(en)">
				>
				["at0018"] = <
					text = <"*Exposure Description(en)">
					description = <"*Description about exposure to the Substance/Agent.(en)">
				>
				["at0019"] = <
					text = <"*Additional Exposure Detail(en)">
					description = <"*Additional detail about exposure/s for this Adverse Reaction event, including structured medication amount/frequency/route information.(en)">
				>
				["at0020"] = <
					text = <"*Earliest Exposure(en)">
					description = <"*Record of the date and/or time of the earliest or initial exposure to the Substance/Agent.(en)">
				>
				["at0021"] = <
					text = <"*Certainty(en)">
					description = <"*Degree of certainty, as assessed by a clinician, that the specific Substance/Agent was the cause of the Adverse Reaction.(en)">
				>
				["at0022"] = <
					text = <"*Suspected(en)">
					description = <"*Possibly the causative agent.(en)">
				>
				["at0023"] = <
					text = <"*Probable(en)">
					description = <"*Likely to be the causative agent, but not confirmed by testing or rechallenge.(en)">
				>
				["at0024"] = <
					text = <"*Confirmed(en)">
					description = <"*Confirmed as the causative agent, by testing or rechallenge.(en)">
				>
				["at0025"] = <
					text = <"مدة التعرض">
					description = <"*The amount of time of exposure to the Substance/Agent.(en)">
				>
				["at0027"] = <
					text = <"تاريخ بداية التفاعل">
					description = <"التاريخ و الوقت الذي بدأ فيه التفاعل.">
				>
				["at0028"] = <
					text = <"مدة التفاعل">
					description = <"مدة التفاعل.">
				>
				["at0029"] = <
					text = <"*Additional Reaction Detail(en)">
					description = <"*Additional detail about the Adverse Reaction, including anatomical location.(en)">
				>
				["at0031"] = <
					text = <"*Multimedia(en)">
					description = <"*Inclusion of any multimedia file to support the recording of the Adverse Reaction event.(en)">
					comment = <"*For example, a photo of a rash or presentation with angioneurotic oedema.(en)">
				>
				["at0032"] = <
					text = <"*Reaction Comment(en)">
					description = <"*Additional narrative about the Adverse Reaction event not captured in other fields.(en)">
				>
				["at0040"] = <
					text = <"*Clinical Management Description(en)">
					description = <"*Narrative description of the clinical management provided.(en)">
				>
				["at0041"] = <
					text = <"*Reporting Details(en)">
					description = <"*Further details required for reporting to regulatory bodies.(en)">
				>
				["at0042"] = <
					text = <"*Tree(en)">
					description = <"*@ internal @(en)">
				>
				["at0044"] = <
					text = <"*Reaction Reported?(en)">
					description = <"*Was the Adverse Reaction reported to a regulatory body?(en)">
				>
				["at0045"] = <
					text = <"*Adverse Reaction Report(en)">
					description = <"*Link to an Adverse Reaction Report sent to a regulatory body.(en)">
				>
				["at0047"] = <
					text = <"*Supporting Clinical Record Information(en)">
					description = <"*Link to further information about the presentation and findings that exist elsewhere in the health record, including allergy test reports.(en)">
					comment = <"*For example, presenting symptoms, examination findings, diagnosis etc.(en)">
				>
				["at0048"] = <
					text = <"*Report Comment(en)">
					description = <"*Additional narrative about the Adverse Reaction Report, including the reason for non-reporting, if required.(en)">
				>
				["at0049"] = <
					text = <"*Future Use(en)">
					description = <"*Narrative description of clinician instructions or advice related to future exposure to, or administration of, the Substance/Agent.(en)">
				>
			>
		>
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Adverse Reaction">
					description = <"A harmful or undesirable, unexpected effect associated with exposure to any substance or agent, including food, plants, animals, venom from animal stings, or a medication at therapeutic or sub-therapeutic doses.">
				>
				["at0001"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Substance/Agent">
					description = <"Identification of a substance, agent, or a class of substance, that is considered to be responsible for the Adverse Reaction.">
					comment = <"Substance/Agent should be coded with a terminology, where possible.">
				>
				["at0004"] = <
					text = <"Absolute Contraindication?">
					description = <"Is administration of this Substance/Agent absolutely contraindicated in this individual?">
					comment = <"A flag indicating that a clinician has identified a propensity for a serious reaction upon further exposure to the Substance/Agent. Record as True if the clinician recommends that deliberate or voluntary exposure to, or administration of, the Substance/Agent should be prevented in future.">
				>
				["at0006"] = <
					text = <"Overall Comment">
					description = <"Additional narrative about the Adverse Reaction as a whole, not captured in other fields.">
				>
				["at0009"] = <
					text = <"Reaction Event">
					description = <"Details about each Adverse Reaction Event.">
				>
				["at0010"] = <
					text = <"Specific Substance/Agent">
					description = <"Specific identification of the actual Substance/Agent considered to be responsible for the Adverse Reaction event.">
					comment = <"Coding of the specific Substance/Agent with a terminology is preferred, where possible. For example, a medication trade name or identification of a specific food.">
				>
				["at0011"] = <
					text = <"Manifestation">
					description = <"Clinical manifestation of the Adverse Reaction expressed as a single word, phrase or brief description, e.g. nausea or rash.">
					comment = <"Manifestation should be coded with a terminology, where possible. The values entered here may be used to display on an application screen as part a list of adverse reactions, as recommended in the NHS CUI guidelines.">
				>
				["at0012"] = <
					text = <"Reaction Description">
					description = <"Narrative description of the Adverse Reaction.">
				>
				["at0016"] = <
					text = <"Reaction Type">
					description = <"The type of Adverse Reaction as determined by the clinician.">
					comment = <"Coding of the reaction type is preferred, where possible. Examples: Immune mediated - Types I-IV (including allergy and hypersensitivity); Non-immune mediated - including pseudoallergic reaction, side effect, intolerance, drug toxicity, drug-drug interaction, food-drug interaction, drug-disease interaction and idiosyncratic reaction.">
				>
				["at0018"] = <
					text = <"Exposure Description">
					description = <"Description about exposure to the Substance/Agent.">
				>
				["at0019"] = <
					text = <"Additional Exposure Detail">
					description = <"Additional detail about exposure/s for this Adverse Reaction event, including structured medication amount/frequency/route information.">
				>
				["at0020"] = <
					text = <"Earliest Exposure">
					description = <"Record of the date and/or time of the earliest or initial exposure to the Substance/Agent.">
				>
				["at0021"] = <
					text = <"Certainty">
					description = <"Degree of certainty, as assessed by a clinician, that the specific Substance/Agent was the cause of the Adverse Reaction.">
				>
				["at0022"] = <
					text = <"Suspected">
					description = <"Possibly the causative agent.">
				>
				["at0023"] = <
					text = <"Probable">
					description = <"Likely to be the causative agent, but not confirmed by testing or rechallenge.">
				>
				["at0024"] = <
					text = <"Confirmed">
					description = <"Confirmed as the causative agent, by testing or rechallenge.">
				>
				["at0025"] = <
					text = <"Duration of Exposure">
					description = <"The amount of time of exposure to the Substance/Agent.">
				>
				["at0027"] = <
					text = <"Onset of Reaction">
					description = <"Record of the date and/or time of the onset of the Adverse Reaction.">
				>
				["at0028"] = <
					text = <"Duration of Reaction">
					description = <"The amount of time that the Adverse Reaction was present.">
				>
				["at0029"] = <
					text = <"Additional Reaction Detail">
					description = <"Additional detail about the Adverse Reaction, including anatomical location.">
				>
				["at0031"] = <
					text = <"Multimedia">
					description = <"Inclusion of any multimedia file to support the recording of the Adverse Reaction event.">
					comment = <"For example, a photo of a rash or presentation with angioneurotic oedema.">
				>
				["at0032"] = <
					text = <"Reaction Comment">
					description = <"Additional narrative about the Adverse Reaction event not captured in other fields.">
				>
				["at0040"] = <
					text = <"Clinical Management Description">
					description = <"Narrative description of the clinical management provided.">
				>
				["at0041"] = <
					text = <"Reporting Details">
					description = <"Further details required for reporting to regulatory bodies.">
				>
				["at0042"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0044"] = <
					text = <"Reaction Reported?">
					description = <"Was the Adverse Reaction reported to a regulatory body?">
				>
				["at0045"] = <
					text = <"Adverse Reaction Report">
					description = <"Link to an Adverse Reaction Report sent to a regulatory body.">
				>
				["at0047"] = <
					text = <"Supporting Clinical Record Information">
					description = <"Link to further information about the presentation and findings that exist elsewhere in the health record, including allergy test reports.">
					comment = <"For example, presenting symptoms, examination findings, diagnosis etc.">
				>
				["at0048"] = <
					text = <"Report Comment">
					description = <"Additional narrative about the Adverse Reaction Report, including the reason for non-reporting, if required.">
				>
				["at0049"] = <
					text = <"Future Use">
					description = <"Narrative description of clinician instructions or advice related to future exposure to, or administration of, the Substance/Agent.">
				>
			>
		>
		["de"] = <
			items = <
				["at0000"] = <
					text = <"Nebenwirkung">
					description = <"*A harmful or undesirable, unexpected effect associated with exposure to any substance or agent, including food, plants, animals, venom from animal stings, or a medication at therapeutic or sub-therapeutic doses.(en)">
				>
				["at0001"] = <
					text = <"*Tree(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"*Substance/Agent(en)">
					description = <"*Identification of a substance, agent, or a class of substance, that is considered to be responsible for the Adverse Reaction.(en)">
					comment = <"*Substance/Agent should be coded with a terminology, where possible.(en)">
				>
				["at0004"] = <
					text = <"*Absolute Contraindication?(en)">
					description = <"*Is administration of this Substance/Agent absolutely contraindicated in this individual?(en)">
					comment = <"*A flag indicating that a clinician has identified a propensity for a serious reaction upon further exposure to the Substance/Agent. Record as True if the clinician recommends that deliberate or voluntary exposure to, or administration of, the Substance/Agent should be prevented in future.(en)">
				>
				["at0006"] = <
					text = <"*Overall Comment(en)">
					description = <"*Additional narrative about the Adverse Reaction as a whole, not captured in other fields.(en)">
				>
				["at0009"] = <
					text = <"*Reaction Event(en)">
					description = <"*Details about each Adverse Reaction Event.(en)">
				>
				["at0010"] = <
					text = <"*Specific Substance/Agent(en)">
					description = <"*Specific identification of the actual Substance/Agent considered to be responsible for the Adverse Reaction event.(en)">
					comment = <"*Coding of the specific Substance/Agent with a terminology is preferred, where possible. For example, a medication trade name or identification of a specific food.(en)">
				>
				["at0011"] = <
					text = <"*Manifestation(en)">
					description = <"*Clinical manifestation of the Adverse Reaction expressed as a single word, phrase or brief description, e.g. nausea or rash.(en)">
					comment = <"*Manifestation should be coded with a terminology, where possible. The values entered here may be used to display on an application screen as part a list of adverse reactions, as recommended in the NHS CUI guidelines.(en)">
				>
				["at0012"] = <
					text = <"Beschreibung der Reaktion">
					description = <"*Narrative description of the Adverse Reaction.(en)">
				>
				["at0016"] = <
					text = <"Reaktionsart">
					description = <"*The type of Adverse Reaction as determined by the clinician.(en)">
				>
				["at0018"] = <
					text = <"*Exposure Description(en)">
					description = <"*Description about exposure to the Substance/Agent.(en)">
				>
				["at0019"] = <
					text = <"*Additional Exposure Detail(en)">
					description = <"*Additional detail about exposure/s for this Adverse Reaction event, including structured medication amount/frequency/route information.(en)">
				>
				["at0020"] = <
					text = <"*Earliest Exposure(en)">
					description = <"*Record of the date and/or time of the earliest or initial exposure to the Substance/Agent.(en)">
				>
				["at0021"] = <
					text = <"*Certainty(en)">
					description = <"*Degree of certainty, as assessed by a clinician, that the specific Substance/Agent was the cause of the Adverse Reaction.(en)">
				>
				["at0022"] = <
					text = <"*Suspected(en)">
					description = <"*Possibly the causative agent.(en)">
				>
				["at0023"] = <
					text = <"*Probable(en)">
					description = <"*Likely to be the causative agent, but not confirmed by testing or rechallenge.(en)">
				>
				["at0024"] = <
					text = <"*Confirmed(en)">
					description = <"*Confirmed as the causative agent, by testing or rechallenge.(en)">
				>
				["at0025"] = <
					text = <"Dauer der Exposition">
					description = <"*The amount of time of exposure to the Substance/Agent.(en)">
				>
				["at0027"] = <
					text = <"Datum des Beginns der Reaktion">
					description = <"Das Datum, an dem die Reaktion eintrat.">
				>
				["at0028"] = <
					text = <"Dauer der Reaktion">
					description = <"Die Dauer der Reaktion.">
				>
				["at0029"] = <
					text = <"*Additional Reaction Detail(en)">
					description = <"*Additional detail about the Adverse Reaction, including anatomical location.(en)">
				>
				["at0031"] = <
					text = <"*Multimedia(en)">
					description = <"*Inclusion of any multimedia file to support the recording of the Adverse Reaction event.(en)">
					comment = <"*For example, a photo of a rash or presentation with angioneurotic oedema.(en)">
				>
				["at0032"] = <
					text = <"*Reaction Comment(en)">
					description = <"*Additional narrative about the Adverse Reaction event not captured in other fields.(en)">
				>
				["at0040"] = <
					text = <"*Clinical Management Description(en)">
					description = <"*Narrative description of the clinical management provided.(en)">
				>
				["at0041"] = <
					text = <"*Reporting Details(en)">
					description = <"*Further details required for reporting to regulatory bodies.(en)">
				>
				["at0042"] = <
					text = <"*Tree(en)">
					description = <"*@ internal @(en)">
				>
				["at0044"] = <
					text = <"*Reaction Reported?(en)">
					description = <"*Was the Adverse Reaction reported to a regulatory body?(en)">
				>
				["at0045"] = <
					text = <"*Adverse Reaction Report(en)">
					description = <"*Link to an Adverse Reaction Report sent to a regulatory body.(en)">
				>
				["at0047"] = <
					text = <"*Supporting Clinical Record Information(en)">
					description = <"*Link to further information about the presentation and findings that exist elsewhere in the health record, including allergy test reports.(en)">
					comment = <"*For example, presenting symptoms, examination findings, diagnosis etc.(en)">
				>
				["at0048"] = <
					text = <"*Report Comment(en)">
					description = <"*Additional narrative about the Adverse Reaction Report, including the reason for non-reporting, if required.(en)">
				>
				["at0049"] = <
					text = <"*Future Use(en)">
					description = <"*Narrative description of clinician instructions or advice related to future exposure to, or administration of, the Substance/Agent.(en)">
				>
			>
		>
	>
```

**Medication Order**

```
archetype (adl_version=1.4)
	openEHR-EHR-INSTRUCTION.medication_order.v1
concept
	[at0000]	-- Medication order
language
	original_language = <[ISO_639-1::en]>
description
	original_author = <
		["name"] = <"Sam Heard">
		["organisation"] = <"OpenEHR Foundation">
		["email"] = <"sam.heard@oceaninformatics.com">
		["date"] = <"2013-05-16">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"Recording intent to use or to continue to use a medicine, vaccine or other therapeutic good including instructions on use, dispensing and administration, where neccessary.">
			use = <"For recording instructions to dispense, administer or use a medicine, vaccine or other therapeutic good. This medication instruction can be used in many circumstances including: a record in a progress note; an item in a medication list, prescription  or drug chart (to be dispensed and/or administered); or in a summary document such as discharge summary or a referral for care. The instruction may be complex and involve more than one activity, such as in the case of a reducing dose of Predisolone, or multiple medications as components of the same order.  This would include a written order by a physician, dentist, nurse practitioner, or other designated health professional for a medication to be dispensed and administered to a patient.

This instruction will generally apply to things that can be prescribed or are available 'over the counter'.

Use for orders for vaccinations or other therapeutic goods. These may be presented differently in different applications but require the same structure.
Use for the consistent representation of an item in a medication list comprising the medicines that a clinicians collectively expect the individual to be taking.
The information recorded may separate dose, route and timing to achieve a computable and sharable specification but also allows for narrative instructions for orders like 'Frusemide 40mg two tablets in the morning and one at lunch' to ensure compatibility with existing systems. To achieve a structure statement for such compound orders, two items are required: 'Frusemide 40mg two tablets in the morning' and 'Frusemide 40mg one tablet at lunch'. The instruction will usually include information about the timing and dose  (which may be structured) and in some settings will include the route of administration. The amount of the medicines will usually be given in terms of a number and a dose unit but may be a textural statement to ensure compatibility with existing systems and also coverage of all scenarios.
Use to represent a prescription item for a medicine, vaccine or other therapeutic good within a document such as an electronic prescription (see COMPOSITION.prescription) or a medication chart.
The content is potentially complex. Where the content is re-usable in other contexts, especially the paired ACTION.medication archetype (for recording dispensing, administration etc) the content has been specified in re-useable CLUSTER archetypes. For example: CLUSTER.amount and CLUSTER.amount-range contain the detail about Medication dose; CLUSTER.timing contains detail about structured dose timing; CLUSTER.medication_administration contains structure around administration for both the order and the action; and CLUSTER.chemical_description described the specific ingredients within a medicine. All of these archetypes together are required to make up the total maximal dataset for a re-useable medication instruction.">
			keywords = <"medication", "order", "prescribe", "therapy", "substance", "drug", "therapeutic", "otc", "therapeutic good">
			misuse = <"Not to be used to record administration, use or dispensing. (For those use ACTION.medication)
Not to be used to record ordering of blood products, implants or major devices such as pacemakers and defibrillators, etc.">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"AuthorDraft">
	other_contributors = <"John Bennett, NEHTA, Australia", "Sharmila Biswas, Australia", "Stephen Chu, NEHTA, Australia (Editor)", "Matthew Cordell, NEHTA, Australia", "Gail Easterbrook, Flinders Medical Centre, Australia", "David Evans, Queensland Health, Australia", "Sarah Gaunt, NEHTA, Australia", "Trina Gregory, cpc, Australia", "Sam Heard, Ocean Informatics, Australia (Editor)", "Mary Kelaher, NEHTA, Australia", "Robert L'egan, NEHTA, Australia", "Heather Leslie, Ocean Informatics, Australia (Editor)", "Susan McIndoe, Royal District Nursing Service, Australia", "David McKillop, NEHTA, Australia", "Chris Mitchell, RACGP, Australia", "Stewart Morrison, NEHTA, Australia", "Chris Pearce, Melbourne East GP Network, Australia", "Camilla Preeston, Royal Australian College of General Practitioners, Australia", "Margaret Prichard, NEHTA, Australia", "Cathy Richardson, NEHTA, Australia", "Robyn Richards, NEHTA - Clinical Terminology, Australia", "John Taylor, NEHTA, Australia", "Richard Townley-O'Neill, NEHTA, Australia (Editor)", "Kylie Young, The Royal Australian College of General Practitioners, Australia", "Ian McNicoll, Ocean Informatics. UK">
	other_details = <
		["references"] = <"Medication instruction, draft archetype, NEHTA Clinical Knowledge Manager [Internet]. NEHTA. Authored: 12 Nov 2010. Available at: http://dcm.nehta.org.au/ckm/#showArchetype_1013.1.838_15 (accessed 15 May 2013).
Therapeutic Good Use Data Group, NEHTA  http://www.nehta.gov.au
Intermountain Healthcare Medication order model, Personal Communication to Sam Heard by Dr Stan Huff.
Royal Australian College of General Practitioners. Fact Sheet: Medicines List. 2010.">
		["MD5-CAM-1.0.1"] = <"CBE33FEAE95392609314DC2F209BE166">
	>

definition
	INSTRUCTION[at0000] matches {	-- Medication order
		activities cardinality matches {0..*; unordered} matches {
			ACTIVITY[at0001] occurrences matches {0..1} matches {	-- Order
				description matches {
					ITEM_TREE[at0002] matches {	-- Tree
						items cardinality matches {1..*; unordered} matches {
							ELEMENT[at0003] matches {	-- Medicine
								value matches {
									DV_TEXT matches {*}
									DV_CODED_TEXT matches {
										defining_code matches {[ac0001]}		-- Medication name
									}
								}
							}
							ELEMENT[at0009] occurrences matches {0..1} matches {	-- Overall directions
								value matches {
									DV_TEXT matches {*}
								}
							}
							allow_archetype CLUSTER[at0004] occurrences matches {0..*} matches {	-- Ingredients and form
								include
									archetype_id/value matches {/openEHR-EHR-CLUSTER\.medication_ingredients(-[a-zA-Z0-9_]+)*\.v1/}
							}
							ELEMENT[at0005] occurrences matches {0..1} matches {	-- Dose description
								value matches {
									DV_TEXT matches {*}
								}
							}
							allow_archetype CLUSTER[at0006] occurrences matches {0..1} matches {	-- Structured dose
								include
									archetype_id/value matches {/openEHR-EHR-CLUSTER\.medication_amount(-[a-zA-Z0-9_]+)*\.v1/}
							}
							ELEMENT[at0008] occurrences matches {0..1} matches {	-- Timing description
								value matches {
									DV_TEXT matches {*}
								}
							}
							CLUSTER[at0010] occurrences matches {0..1} matches {	-- Structured timing
								items cardinality matches {1..*; unordered} matches {
									ELEMENT[at0029] occurrences matches {0..1} matches {	-- PRN
										value matches {
											DV_BOOLEAN matches {
												value matches {True}
											}
										}
									}
									ELEMENT[at0011] occurrences matches {0..*} matches {	-- Start criterion
										value matches {
											DV_TEXT matches {*}
										}
									}
									ELEMENT[at0012] occurrences matches {0..1} matches {	-- Start date
										value matches {
											DV_DATE_TIME matches {*}
										}
									}
									ELEMENT[at0016] occurrences matches {0..*} matches {	-- Stop criterion
										value matches {
											DV_TEXT matches {*}
										}
									}
									ELEMENT[at0013] occurrences matches {0..1} matches {	-- Stop date
										value matches {
											DV_DATE_TIME matches {*}
										}
									}
									ELEMENT[at0014] occurrences matches {0..1} matches {	-- Duration of treatment
										value matches {
											DV_DURATION matches {*}
										}
									}
									ELEMENT[at0015] occurrences matches {0..1} matches {	-- Number of administrations
										value matches {
											DV_COUNT matches {*}
										}
									}
									ELEMENT[at0017] occurrences matches {0..1} matches {	-- Long-term
										value matches {
											DV_BOOLEAN matches {
												value matches {True, False}
											}
										}
									}
									allow_archetype CLUSTER[at0037] occurrences matches {0..1} matches {	-- Detailed timing
										include
											archetype_id/value matches {/openEHR-EHR-CLUSTER\.timing(-[a-zA-Z0-9_]+)*\.v1/}
									}
								}
							}
							ELEMENT[at0044] occurrences matches {0..*} matches {	-- Additional instruction
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0018] occurrences matches {0..*} matches {	-- Clinical indication
								value matches {
									DV_TEXT matches {*}
								}
							}
							allow_archetype CLUSTER[at0043] occurrences matches {0..*} matches {	-- Administration details
								include
									archetype_id/value matches {/openEHR-EHR-CLUSTER\.medication_admin(-[a-zA-Z0-9_]+)*\.v1/}
							}
							ELEMENT[at0035] occurrences matches {0..*} matches {	-- Comment
								value matches {
									DV_TEXT matches {*}
								}
							}
							CLUSTER[at0023] occurrences matches {0..1} matches {	-- Dispensing
								items cardinality matches {1..*; unordered} matches {
									allow_archetype CLUSTER[at0045] occurrences matches {0..*} matches {	-- Quantity
										include
											archetype_id/value matches {/openEHR-EHR-CLUSTER\.medication_amount(-[a-zA-Z0-9_]+)*\.v1/}
									}
									ELEMENT[at0025] occurrences matches {0..1} matches {	-- Number of repeats
										value matches {
											DV_COUNT matches {
												magnitude matches {|>=0|}
											}
										}
									}
									ELEMENT[at0046] occurrences matches {0..1} matches {	-- Minimum interval between repeats
										value matches {
											DV_DURATION matches {*}
										}
									}
									ELEMENT[at0026] occurrences matches {0..1} matches {	-- Brand substitution permitted
										value matches {
											DV_BOOLEAN matches {
												value matches {True, False}
											}
										}
									}
									ELEMENT[at0028] occurrences matches {0..1} matches {	-- Dispensing instructions
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
		}
		protocol matches {
			ITEM_TREE[at0031] matches {	-- Tree
				items cardinality matches {0..*; unordered} matches {
					ELEMENT[at0038] occurrences matches {0..*} matches {	-- Indication for authorised use
						value matches {
							DV_TEXT matches {*}
						}
					}
					ELEMENT[at0032] occurrences matches {0..*} matches {	-- Medication Instruction Id
						value matches {
							DV_IDENTIFIER matches {*}
						}
					}
					ELEMENT[at0042] occurrences matches {0..1} matches {	-- Concession benefit
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
					text = <"Medication order">
					description = <"Details of a medicine, vaccine or other therapeutic good with instructions for use.">
				>
				["at0001"] = <
					text = <"Order">
					description = <"The instructions for a particular medicine, vaccine or other therapeutic good including dose and timing.">
				>
				["at0002"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0003"] = <
					text = <"Medicine">
					description = <"The medicine, vaccine or other therapeutic good being ordered, administered to or used by the subject of care. This item should be coded if possible.">
				>
				["at0004"] = <
					text = <"Ingredients and form">
					description = <"Detailed information about the ingredient(s) including form and strength.">
				>
				["at0005"] = <
					text = <"Dose description">
					description = <"The amount and units of the medicine, vaccine or other therapeutic good to be used or administered at one time.">
				>
				["at0006"] = <
					text = <"Structured dose">
					description = <"Structured information on dose with dose unit. If 'Structured dose' is used with 'Dose description' then these must be semantically equivalent.">
				>
				["at0008"] = <
					text = <"Timing description">
					description = <"The timing of the doses, which may include frequency and details such as relationship to food.">
				>
				["at0009"] = <
					text = <"Overall directions">
					description = <"A complete narrative description of how much, when and how to use the medicine, vaccine or other therapeutic good.">
				>
				["at0010"] = <
					text = <"Structured timing">
					description = <"Details of the timing of the use or administration of the medicine, vaccine or other therapeutic good.">
				>
				["at0011"] = <
					text = <"Start criterion">
					description = <"A condition which, when met, requires the start of administration or use.">
				>
				["at0012"] = <
					text = <"Start date">
					description = <"The date and optional time to begin using the medicine, vaccine or other therapeutic good.">
				>
				["at0013"] = <
					text = <"Stop date">
					description = <"The date and optional time to stop using the medicine, vaccine or other therapeutic good.">
				>
				["at0014"] = <
					text = <"Duration of treatment">
					description = <"The length of time for which the medicine, vaccine or other therapeutic good should be used or administered (from the initial dose to the final dose).">
				>
				["at0015"] = <
					text = <"Number of administrations">
					description = <"The total number of doses of the medicine, vaccine or other therapeutic good that are to be used or administered (from the initial dose to the final dose).">
				>
				["at0016"] = <
					text = <"Stop criterion">
					description = <"A condition which, when met, requires the cessation of administration or use.">
				>
				["at0017"] = <
					text = <"Long-term">
					description = <"It is anticipated that the medicine, vaccine or therapeutic good will be re-prescribed or re-dispensed over a period of time.">
				>
				["at0018"] = <
					text = <"Clinical indication">
					description = <"A reason for ordering the medicine, vaccine or other therapeutic good.">
				>
				["at0023"] = <
					text = <"Dispensing">
					description = <"Information for the dispenser.">
				>
				["at0025"] = <
					text = <"Number of repeats">
					description = <"The number of times the expressed quantity of medicine, vaccine or other therapeutic good may be refilled or redispensed without a new prescription.">
				>
				["at0026"] = <
					text = <"Brand substitution permitted">
					description = <"Indicates whether or not the substitution of a prescribed medicine with a different brand name of the same medicine, vaccine or other therapeutic good, which has been determined as bioequivalent, is allowed when the medication is dispensed/supplied.">
				>
				["at0028"] = <
					text = <"Dispensing instructions">
					description = <"Additional instructions to the person dispensing the medicine, vaccine or other therapeutic good.">
				>
				["at0029"] = <
					text = <"PRN">
					description = <"The timing is dependent within limits on the subject of care's condition or symptoms  (e.g. 4hrly p.r.n. means the medicine can be taken as frequently as every four hours if necessary). \"Pro re nata\" in latin means as circumstances arise.">
				>
				["at0031"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0032"] = <
					text = <"Medication Instruction Id">
					description = <"An identifier used in an external system and associated with this medication instruction.">
				>
				["at0035"] = <
					text = <"Comment">
					description = <"Any additional information that may be needed to ensure the continuity of supply, rationale for current dose and timing, or safe and appropriate use.">
				>
				["at0037"] = <
					text = <"Detailed timing">
					description = <"Structured details of the timing of the use or administration.">
				>
				["at0038"] = <
					text = <"Indication for authorised use">
					description = <"The specific indication for use that is required by an authorising agency to achieve subsidy for or access to the medicine, vaccine or other therapeutic good. This could be a national medication scheme, insurance company or other funding agency.">
				>
				["at0042"] = <
					text = <"Concession benefit">
					description = <"Indicates the category of subsidy appropriate to the item being prescribed.">
				>
				["at0043"] = <
					text = <"Administration details">
					description = <"Details of the administration of the medicine, vaccine or other therapeutic good.">
				>
				["at0044"] = <
					text = <"Additional instruction">
					description = <"An additional statement on how to use the medicine, vaccine or other therapeutic good.">
				>
				["at0045"] = <
					text = <"Quantity">
					description = <"The amount of medicine, vaccine or other therapeutic good to be dispensed.">
				>
				["at0046"] = <
					text = <"Minimum interval between repeats">
					description = <"The minimum time between repeat dispensing of the medicine, vaccine or therapeutic good. Note: This is specified by the ordering clinician for a specific reason such as safety or best practice.">
				>
			>
		>
	>
	constraint_definitions = <
		["en"] = <
			items = <
				["ac0001"] = <
					text = <"Medication name">
					description = <"Any valid term for a medicine or other therapeutic agent.">
				>
			>
		>
	>

```
