#####Use Case ID: UC-PAS43
#####Use Case Name: Admission

**Level:**                     User Level Goal

**Primary Actors:**            Admitting Clerk

**Stakeholders:**              Admitting Clerk, Physician, Patient , Healthcare Provider

**Purpose:**                   The main intent of this use case is to capture inpatient admission information.

**Pre Condition:**             Admitting Clerk must be identified and authenticated.

**Post Condition:**            Patient admitted successfully.

**Frequency of Occurrence:**   Medium
__________________________________________________________
**Main Success Scenario: (Admission)**

1. Admitting Clerk selects patient admission for inpatient encounter.
2. System displays the list of appointment for inpatient encounters.
3. Admitting Clerk reviews appointment details and requests system to create inpatient encounter.
4. System asks user to enter encounter details such as patient stay details (floor, ward, room), admission type (such as “elective”), consulting physician, admitting diagnosis and emergency contact information (name, contact number).
5. Admitting Clerk enters the required information and submits it.
6. System successfully records inpatient encounter information.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Patient Administration):**

PRPA_ST402001UV02
_______________________________________________________________
**Reference CCHIT Criteria:**

IP 15.12, FN 03.01, IP 01.01, IP 01.02, IP 01.03
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Patient Administration):**

![prpa_rm402001uv active-inpatient](https://f.cloud.github.com/assets/5391320/1370004/875c733c-3a0c-11e3-9626-3aa4ce0cb378.png)

_______________________________________________________________
**Reference FHIR Resource:**

![encounter fhir resource](https://f.cloud.github.com/assets/5391320/1369999/74cb4914-3a0c-11e3-8d49-1317a89cc65d.png)
_______________________________________________________________
**Reference CDA Template:**

Section Level Template **"Encounters Section (entries optional)"**

Section Level Template **"Encounters Section (entries required)"**
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):**

OpenEHR Archetype: (Patient Admission)

``` Archetype
archetype (adl_version=1.4)
	openEHR-EHR-ADMIN_ENTRY.admission.v1

concept
	[at0000]	-- Patient admission
language
	original_language = <[ISO_639-1::en]>
	translations = <
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			author = <
				["name"] = <"Mona Saleh">
			>
		>
	>
description
	original_author = <
		["name"] = <"Chunlan Ma">
		["organisation"] = <"Ocean Informatics">
		["email"] = <"chunlan.ma@oceaninformatics.com">
		["date"] = <"19/07/07">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"This admission ADMIN_ENTRY archetype was designed for representing the minimum admission data. This is based on the Australian/New Zealand Standard Implementation of Health Level Seven (HL7) Version 2.4 (Part 1: Patient administration) and Health Level Seven (HL7) Standard Version 2.3.1.">
			use = <"">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
		["ar-sy"] = <
			language = <[ISO_639-1::ar-sy]>
			purpose = <"هذا النموذج الخاص بإدخال المريض تم تصميمه لتمثيل الحد الأدنى من بيانات إدخال المريض.
و هذا يستخدم التطبيق العياري في أستراليا و نيوزيلندة للمستوى الصحي السابع النسخة/الإصدار 2.4 (الجزء الأول:إدراة المريض), و الإصدار 2.3.1 من المستوى الصحي السابع.">
			use = <"">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"AuthorDraft">
	other_contributors = <"Sistine Barretto", ...>
	other_details = <
		["references"] = <"">
		["MD5-CAM-1.0.1"] = <"54E7D096A051918F6E3EF51257DD6B60">
	>

definition
	ADMIN_ENTRY[at0000] matches {	-- Patient admission
		data matches {
			ITEM_TREE[at0001] matches {	-- Tree
				items cardinality matches {2..*; unordered} matches {
					ELEMENT[at0002] matches {	-- Patient class
						value matches {
							DV_CODED_TEXT matches {
								defining_code matches {
									[local::
									at0003, 	-- Inpatient/overnight patient
									at0004, 	-- Same day patient
									at0005, 	-- Outpatient
									at0006, 	-- Emergency patient
									at0007, 	-- Community client
									at0008, 	-- Pre-admit
									at0009, 	-- Commercial account
									at0010, 	-- Not-applicable
									at0011]	-- Unknown
								}
							}
						}
					}
					CLUSTER[at0073] occurrences matches {0..1} matches {	-- Assigned patient location
						items cardinality matches {1..*; unordered} matches {
							ELEMENT[at0074] occurrences matches {0..1} matches {	-- Point of care/Unit
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0077] occurrences matches {0..1} matches {	-- Ward
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0078] occurrences matches {0..1} matches {	-- Room
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0079] occurrences matches {0..1} matches {	-- Bed
								value matches {
									DV_TEXT matches {*}
								}
							}
							CLUSTER[at0104] occurrences matches {0..1} matches {	-- Facility
								items cardinality matches {1..*; unordered} matches {
									ELEMENT[at0105] occurrences matches {0..1} matches {	-- Namespace ID
										value matches {
											DV_TEXT matches {*}
										}
									}
									ELEMENT[at0106] occurrences matches {0..1} matches {	-- Universal ID
										value matches {
											DV_TEXT matches {*}
										}
									}
									ELEMENT[at0107] occurrences matches {0..1} matches {	-- Universal ID type
										value matches {
											DV_CODED_TEXT matches {
												defining_code matches {
													[local::
													at0108, 	-- DNS
													at0109, 	-- GUID
													at0110, 	-- HCD
													at0111, 	-- HL7
													at0112, 	-- ISO
													at0113, 	-- L, M, N
													at0114, 	-- Random
													at0115, 	-- UUID
													at0116, 	-- x400
													at0118]	-- x500
												}
											}
										}
									}
								}
							}
							ELEMENT[at0101] occurrences matches {0..1} matches {	-- Building
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0102] occurrences matches {0..1} matches {	-- Floor
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0103] occurrences matches {0..1} matches {	-- Location description
								value matches {
									DV_TEXT matches {*}
								}
							}
							CLUSTER[at0084] occurrences matches {0..1} matches {	-- Address
								items cardinality matches {1..*; unordered} matches {
									ELEMENT[at0085] occurrences matches {0..1} matches {	-- Street
										value matches {
											DV_TEXT matches {*}
										}
									}
									ELEMENT[at0086] occurrences matches {0..1} matches {	-- City
										value matches {
											DV_TEXT matches {*}
										}
									}
									ELEMENT[at0087] occurrences matches {0..1} matches {	-- State/province
										value matches {
											DV_TEXT matches {*}
										}
									}
									ELEMENT[at0088] occurrences matches {0..1} matches {	-- Post code
										value matches {
											DV_TEXT matches {*}
										}
									}
									ELEMENT[at0089] occurrences matches {0..1} matches {	-- Country
										value matches {
											DV_TEXT matches {*}
										}
									}
								}
							}
							ELEMENT[at0081] occurrences matches {0..1} matches {	-- Location type
								value matches {
									DV_CODED_TEXT matches {
										defining_code matches {
											[local::
											at0082, 	-- Clinic
											at0090, 	-- Home
											at0091, 	-- Department
											at0092, 	-- Nursing unit
											at0093]	-- Provider's office
										}
									}
								}
							}
						}
					}
					ELEMENT[at0013] occurrences matches {0..1} matches {	-- Admission type
						value matches {
							DV_CODED_TEXT matches {
								defining_code matches {
									[local::
									at0014, 	-- Accident
									at0015, 	-- Emergency
									at0016, 	-- Labour & Delivery
									at0017, 	-- Routine
									at0018, 	-- Newborn
									at0019, 	-- Urgent
									at0020, 	-- Elective
									at0021, 	-- Geriatric respite admission
									at0022]	-- Statistical admission
								}
							}
						}
					}
					ELEMENT[at0023] occurrences matches {0..1} matches {	-- Pre-admit number
						value matches {
							DV_TEXT matches {*}
						}
					}
					CLUSTER[at0094] occurrences matches {0..1} matches {	-- Prior patient location
						items cardinality matches {1..*; unordered} matches {
							CLUSTER[at0119] occurrences matches {0..1} matches {	-- Facility
								items cardinality matches {1..*; unordered} matches {
									use_node ELEMENT /data[at0001]/items[at0073]/items[at0104]/items[at0105]	-- /data[Tree]/items[Assigned patient location]/items[Facility]/items[Namespace ID]
									use_node ELEMENT /data[at0001]/items[at0073]/items[at0104]/items[at0106]	-- /data[Tree]/items[Assigned patient location]/items[Facility]/items[Universal ID]
									use_node ELEMENT /data[at0001]/items[at0073]/items[at0104]/items[at0107]	-- /data[Tree]/items[Assigned patient location]/items[Facility]/items[Universal ID type]
								}
							}
							CLUSTER[at0095] occurrences matches {0..1} matches {	-- Adress
								items cardinality matches {1..*; unordered} matches {
									use_node ELEMENT /data[at0001]/items[at0073]/items[at0084]/items[at0085]	-- /data[Tree]/items[Assigned patient location]/items[Address]/items[Street]
									use_node ELEMENT /data[at0001]/items[at0073]/items[at0084]/items[at0086]	-- /data[Tree]/items[Assigned patient location]/items[Address]/items[City]
									use_node ELEMENT /data[at0001]/items[at0073]/items[at0084]/items[at0087]	-- /data[Tree]/items[Assigned patient location]/items[Address]/items[State/province]
									use_node ELEMENT /data[at0001]/items[at0073]/items[at0084]/items[at0088]	-- /data[Tree]/items[Assigned patient location]/items[Address]/items[Post code]
									use_node ELEMENT /data[at0001]/items[at0073]/items[at0084]/items[at0089]	-- /data[Tree]/items[Assigned patient location]/items[Address]/items[Country]
								}
							}
							use_node ELEMENT /data[at0001]/items[at0073]/items[at0074]	-- /data[Tree]/items[Assigned patient location]/items[Point of care/Unit]
							use_node ELEMENT /data[at0001]/items[at0073]/items[at0077]	-- /data[Tree]/items[Assigned patient location]/items[Ward]
							use_node ELEMENT /data[at0001]/items[at0073]/items[at0078]	-- /data[Tree]/items[Assigned patient location]/items[Room]
							use_node ELEMENT /data[at0001]/items[at0073]/items[at0079]	-- /data[Tree]/items[Assigned patient location]/items[Bed]
							use_node ELEMENT /data[at0001]/items[at0073]/items[at0101]	-- /data[Tree]/items[Assigned patient location]/items[Building]
							use_node ELEMENT /data[at0001]/items[at0073]/items[at0102]	-- /data[Tree]/items[Assigned patient location]/items[Floor]
							use_node ELEMENT /data[at0001]/items[at0073]/items[at0103]	-- /data[Tree]/items[Assigned patient location]/items[Location description]
						}
					}
					CLUSTER[at0098] occurrences matches {0..*} matches {	-- Attending doctor
						items cardinality matches {1..*; unordered} matches {
							ELEMENT[at0099] occurrences matches {0..1} matches {	-- ID
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0100] occurrences matches {0..1} matches {	-- Family name
								value matches {
									DV_TEXT matches {*}
								}
							}
							ELEMENT[at0120] occurrences matches {0..1} matches {	-- Last name
								value matches {
									DV_TEXT matches {*}
								}
							}
						}
					}
					CLUSTER[at0025] occurrences matches {0..1} matches {	-- Referring doctor
						items cardinality matches {1..*; unordered} matches {
							use_node ELEMENT /data[at0001]/items[at0098]/items[at0099]	-- /data[Tree]/items[Attending doctor]/items[ID]
							use_node ELEMENT /data[at0001]/items[at0098]/items[at0100]	-- /data[Tree]/items[Attending doctor]/items[Family name]
							use_node ELEMENT /data[at0001]/items[at0098]/items[at0120]	-- /data[Tree]/items[Attending doctor]/items[Last name]
						}
					}
					CLUSTER[at0121] occurrences matches {0..*} matches {	-- Consulting doctor
						items cardinality matches {1..*; unordered} matches {
							use_node ELEMENT /data[at0001]/items[at0098]/items[at0099]	-- /data[Tree]/items[Attending doctor]/items[ID]
							use_node ELEMENT /data[at0001]/items[at0098]/items[at0100]	-- /data[Tree]/items[Attending doctor]/items[Family name]
							use_node ELEMENT /data[at0001]/items[at0098]/items[at0120]	-- /data[Tree]/items[Attending doctor]/items[Last name]
						}
					}
					ELEMENT[at0041] occurrences matches {0..1} matches {	-- Hospital service
						value matches {
							DV_TEXT matches {*}
						}
					}
					ELEMENT[at0049] occurrences matches {0..1} matches {	-- Admit source
						value matches {
							DV_TEXT matches {*}
						}
					}
					CLUSTER[at0051] occurrences matches {0..1} matches {	-- Admitting doctor
						items cardinality matches {1..*; unordered} matches {
							use_node ELEMENT /data[at0001]/items[at0098]/items[at0099]	-- /data[Tree]/items[Attending doctor]/items[ID]
							use_node ELEMENT /data[at0001]/items[at0098]/items[at0100]	-- /data[Tree]/items[Attending doctor]/items[Family name]
							use_node ELEMENT /data[at0001]/items[at0098]/items[at0120]	-- /data[Tree]/items[Attending doctor]/items[Last name]
						}
					}
					ELEMENT[at0061] occurrences matches {0..1} matches {	-- Financial class
						value matches {
							DV_CODED_TEXT matches {
								defining_code matches {
									[local::
									at0062, 	-- Australian Health Care Agreements
									at0063, 	-- Private health insurance
									at0064, 	-- Self-funded
									at0065, 	-- Worker's compensation
									at0122, 	-- Motor vehicle third party personal claim
									at0123, 	-- Other compensation (e.g. public liability, common law, medical negligence)
									at0124, 	-- Department of Veterans' Affairs
									at0125, 	-- Department of Defence
									at0126, 	-- Correctional facility
									at0127, 	-- Other hospital or public authority (contracted care)
									at0128, 	-- Reciprocal health care agreements (with other countries)
									at0129, 	-- Other
									at0130]	-- Not known
								}
							}
						}
					}
					ELEMENT[at0066] occurrences matches {0..1} matches {	-- Charge price indicator
						value matches {
							DV_CODED_TEXT matches {
								defining_code matches {[ac0001]}		-- Any term that 'is a' 'Charge price indicator'
							}
						}
					}
					ELEMENT[at0071] matches {	-- Admit date/time
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
					text = <"Patient admission">
					description = <"Used for admitted patient only. It signals the beginning of a patient's stay in a health care facility.">
				>
				["at0001"] = <
					text = <"Tree">
					description = <"@ internal @">
				>
				["at0002"] = <
					text = <"Patient class">
					description = <"Intended mode of treatement.">
				>
				["at0003"] = <
					text = <"Inpatient/overnight patient">
					description = <"Inpatient/overnight patient">
				>
				["at0004"] = <
					text = <"Same day patient">
					description = <"Same day patient">
				>
				["at0005"] = <
					text = <"Outpatient">
					description = <"Outpatient">
				>
				["at0006"] = <
					text = <"Emergency patient">
					description = <"Emergency patient">
				>
				["at0007"] = <
					text = <"Community client">
					description = <"Community client">
				>
				["at0008"] = <
					text = <"Pre-admit">
					description = <"Pre-admit">
				>
				["at0009"] = <
					text = <"Commercial account">
					description = <"Commercial account">
				>
				["at0010"] = <
					text = <"Not-applicable">
					description = <"Not-applicable">
				>
				["at0011"] = <
					text = <"Unknown">
					description = <"Unknown">
				>
				["at0013"] = <
					text = <"Admission type">
					description = <"The circumstance under which the patient will be admitted.">
				>
				["at0014"] = <
					text = <"Accident">
					description = <"Accident">
				>
				["at0015"] = <
					text = <"Emergency">
					description = <"Emergency">
				>
				["at0016"] = <
					text = <"Labour & Delivery">
					description = <"Labour & Delivery">
				>
				["at0017"] = <
					text = <"Routine">
					description = <"Routine">
				>
				["at0018"] = <
					text = <"Newborn">
					description = <"Newborn">
				>
				["at0019"] = <
					text = <"Urgent">
					description = <"Urgent">
				>
				["at0020"] = <
					text = <"Elective">
					description = <"Elective">
				>
				["at0021"] = <
					text = <"Geriatric respite admission">
					description = <"Geriatric respite admission">
				>
				["at0022"] = <
					text = <"Statistical admission">
					description = <"Statistical admission">
				>
				["at0023"] = <
					text = <"Pre-admit number">
					description = <"ID number of patient's pre-admission">
				>
				["at0025"] = <
					text = <"Referring doctor">
					description = <"Clinician who referred patient to the consulting doctor">
				>
				["at0041"] = <
					text = <"Hospital service">
					description = <"For local use, this field hold the type of organizational unit or clinical unit, e.g. CARDO1.">
				>
				["at0049"] = <
					text = <"Admit source">
					description = <"Refer to NHDD 000385 Mode of admission and
NHDD 000150 Source of referral to public psychiatric hospital">
				>
				["at0051"] = <
					text = <"Admitting doctor">
					description = <"*">
				>
				["at0061"] = <
					text = <"Financial class">
					description = <"*">
				>
				["at0062"] = <
					text = <"Australian Health Care Agreements">
					description = <"Australian Health Care Agreements ">
				>
				["at0063"] = <
					text = <"Private health insurance">
					description = <"Private health insurance">
				>
				["at0064"] = <
					text = <"Self-funded">
					description = <"Self-funded">
				>
				["at0065"] = <
					text = <"Worker's compensation">
					description = <"Worker's compensation">
				>
				["at0066"] = <
					text = <"Charge price indicator">
					description = <"*">
				>
				["at0071"] = <
					text = <"Admit date/time">
					description = <"Date/time the patient was admitted.">
				>
				["at0073"] = <
					text = <"Assigned patient location">
					description = <"Assigned patient location when the patient was admitted.">
				>
				["at0074"] = <
					text = <"Point of care/Unit">
					description = <"*">
				>
				["at0077"] = <
					text = <"Ward">
					description = <"*">
				>
				["at0078"] = <
					text = <"Room">
					description = <"*">
				>
				["at0079"] = <
					text = <"Bed">
					description = <"*">
				>
				["at0081"] = <
					text = <"Location type">
					description = <"*">
				>
				["at0082"] = <
					text = <"Clinic">
					description = <"*">
				>
				["at0084"] = <
					text = <"Address">
					description = <"*">
				>
				["at0085"] = <
					text = <"Street">
					description = <"*">
				>
				["at0086"] = <
					text = <"City">
					description = <"*">
				>
				["at0087"] = <
					text = <"State/province">
					description = <"*">
				>
				["at0088"] = <
					text = <"Post code">
					description = <"*">
				>
				["at0089"] = <
					text = <"Country">
					description = <"*">
				>
				["at0090"] = <
					text = <"Home">
					description = <"*">
				>
				["at0091"] = <
					text = <"Department">
					description = <"*">
				>
				["at0092"] = <
					text = <"Nursing unit">
					description = <"*">
				>
				["at0093"] = <
					text = <"Provider's office">
					description = <"*">
				>
				["at0094"] = <
					text = <"Prior patient location">
					description = <"The patient location prior admission">
				>
				["at0095"] = <
					text = <"Adress">
					description = <"*">
				>
				["at0098"] = <
					text = <"Attending doctor">
					description = <"The attending doctor providing services to the
patient">
				>
				["at0099"] = <
					text = <"ID">
					description = <"*">
				>
				["at0100"] = <
					text = <"Family name">
					description = <"*">
				>
				["at0101"] = <
					text = <"Building">
					description = <"*">
				>
				["at0102"] = <
					text = <"Floor">
					description = <"*">
				>
				["at0103"] = <
					text = <"Location description">
					description = <"*">
				>
				["at0104"] = <
					text = <"Facility">
					description = <"*">
				>
				["at0105"] = <
					text = <"Namespace ID">
					description = <"*">
				>
				["at0106"] = <
					text = <"Universal ID">
					description = <"*">
				>
				["at0107"] = <
					text = <"Universal ID type">
					description = <"*">
				>
				["at0108"] = <
					text = <"DNS">
					description = <"*">
				>
				["at0109"] = <
					text = <"GUID">
					description = <"*">
				>
				["at0110"] = <
					text = <"HCD">
					description = <"*">
				>
				["at0111"] = <
					text = <"HL7">
					description = <"*">
				>
				["at0112"] = <
					text = <"ISO">
					description = <"*">
				>
				["at0113"] = <
					text = <"L, M, N">
					description = <"*">
				>
				["at0114"] = <
					text = <"Random">
					description = <"*">
				>
				["at0115"] = <
					text = <"UUID">
					description = <"*">
				>
				["at0116"] = <
					text = <"x400">
					description = <"*">
				>
				["at0118"] = <
					text = <"x500">
					description = <"*">
				>
				["at0119"] = <
					text = <"Facility">
					description = <"*">
				>
				["at0120"] = <
					text = <"Last name">
					description = <"*">
				>
				["at0121"] = <
					text = <"Consulting doctor">
					description = <"Consultant responsible for the care of the patient,including salaried specialist, visiting medical officer">
				>
				["at0122"] = <
					text = <"Motor vehicle third party personal claim">
					description = <"*">
				>
				["at0123"] = <
					text = <"Other compensation (e.g. public liability, common law, medical negligence)">
					description = <"*">
				>
				["at0124"] = <
					text = <"Department of Veterans' Affairs">
					description = <"*">
				>
				["at0125"] = <
					text = <"Department of Defence">
					description = <"*">
				>
				["at0126"] = <
					text = <"Correctional facility">
					description = <"*">
				>
				["at0127"] = <
					text = <"Other hospital or public authority (contracted care)">
					description = <"*">
				>
				["at0128"] = <
					text = <"Reciprocal health care agreements (with other countries)">
					description = <"*">
				>
				["at0129"] = <
					text = <"Other">
					description = <"*">
				>
				["at0130"] = <
					text = <"Not known">
					description = <"*">
				>
			>
		>
		["ar-sy"] = <
			items = <
				["at0000"] = <
					text = <"إدخال المريض">
					description = <"يستخدم فقط للمرضى الذين تم إدخالهم. و ذلك يشير إلى بداية بقاء المريض في مؤسسة الرعاية الصحية">
				>
				["at0001"] = <
					text = <"*Tree(en)">
					description = <"*@ internal @(en)">
				>
				["at0002"] = <
					text = <"درجة المريض">
					description = <"أسلوب المعاملة المقصود">
				>
				["at0003"] = <
					text = <"مريض داخلي/ليلي">
					description = <"مريض داخلي/ليلي">
				>
				["at0004"] = <
					text = <"مريض اليوم الواحد">
					description = <"مريض اليوم الواحد">
				>
				["at0005"] = <
					text = <"المريض الخارجي">
					description = <"المريض الخارجي">
				>
				["at0006"] = <
					text = <"مريض الطوارئ">
					description = <"مريض الطوارئ">
				>
				["at0007"] = <
					text = <"عميل مجتمعي">
					description = <"عميل مجتمعي">
				>
				["at0008"] = <
					text = <"ما قبل الإدخال">
					description = <"ما قبل الإدخال">
				>
				["at0009"] = <
					text = <"حساب تجاري">
					description = <"حساب تجاري">
				>
				["at0010"] = <
					text = <"غير قابل للتطبيق">
					description = <"غير قابل للتطبيق">
				>
				["at0011"] = <
					text = <"غير معروف">
					description = <"غير معروف">
				>
				["at0013"] = <
					text = <"نوع الإدخال">
					description = <"الظروف التي يتم إدخال المريض تحتها">
				>
				["at0014"] = <
					text = <"حادث">
					description = <"حادث">
				>
				["at0015"] = <
					text = <"طوارئ">
					description = <"طوارئ">
				>
				["at0016"] = <
					text = <"الولادة و الوضع">
					description = <"الولادة و الوضع">
				>
				["at0017"] = <
					text = <"روتيني/معتاد">
					description = <"روتيني/معتاد">
				>
				["at0018"] = <
					text = <"حديث الولادة">
					description = <"حديث الولادة">
				>
				["at0019"] = <
					text = <"عاجل">
					description = <"عاجل">
				>
				["at0020"] = <
					text = <"اختياري">
					description = <"اختياري">
				>
				["at0021"] = <
					text = <"إدخال المسنين للراحة">
					description = <"إدخال المسنين للراحة">
				>
				["at0022"] = <
					text = <"الإدخال الإحصائي">
					description = <"الإدخال الإحصائي">
				>
				["at0023"] = <
					text = <"رقم ما قبل الإدخال">
					description = <"الرقم التعريفي للمريض ما قبل الإدخال">
				>
				["at0025"] = <
					text = <"الطبيب صاحب الإحالة">
					description = <"الطبيب الذي قام بإحالة المريض إلى الطبيب الاستشاري">
				>
				["at0041"] = <
					text = <"خدمة المستشفى">
					description = <"للاستخدام المحلي, و يمثل هذا الحق نو الوحدة التنظيمية أو السريرية, مثل: 
CARDO1">
				>
				["at0049"] = <
					text = <"مصدر الإدخال">
					description = <"برجاء الرجوع إلى طريق الإدخال في 
NHDD 000385 
و مصدر الإحالة إلى المستشفى النفسي العام
NHDD 000150 ">
				>
				["at0051"] = <
					text = <"الطبيب المسئول عن الإدخال">
					description = <"*">
				>
				["at0061"] = <
					text = <"الدرجة الاقتصادية">
					description = <"*">
				>
				["at0062"] = <
					text = <"الاتفاقات الأسترالية للرعاية الصحية">
					description = <"الاتفاقات الأسترالية للرعاية الصحية">
				>
				["at0063"] = <
					text = <"التأمين الصحي الخاص">
					description = <"التأمين الصحي الخاص">
				>
				["at0064"] = <
					text = <"مموَّل شخصيا">
					description = <"مموَّل شخصيا">
				>
				["at0065"] = <
					text = <"تعويضات العامل">
					description = <"تعويضات العامل">
				>
				["at0066"] = <
					text = <"مؤشر ثمن الرعاية">
					description = <"*">
				>
				["at0071"] = <
					text = <"وقت/ تاريخ الإدخال">
					description = <"الوقت و التاريخ الذين تم فيهما إدخال المريض">
				>
				["at0073"] = <
					text = <"المكان المعَيَّن للمريض">
					description = <"المكان الذي تم تعيينه للمريض عند إدخال المريض">
				>
				["at0074"] = <
					text = <"نقطة تقديم الرعاية/الوحدة">
					description = <"*">
				>
				["at0077"] = <
					text = <"العنبر">
					description = <"*">
				>
				["at0078"] = <
					text = <"الغرفة/الحجرة">
					description = <"*">
				>
				["at0079"] = <
					text = <"السرير">
					description = <"*">
				>
				["at0081"] = <
					text = <"نوع الموقع">
					description = <"*">
				>
				["at0082"] = <
					text = <"عيادة">
					description = <"*">
				>
				["at0084"] = <
					text = <"العنوان">
					description = <"*">
				>
				["at0085"] = <
					text = <"الشارع">
					description = <"*">
				>
				["at0086"] = <
					text = <"المدينة">
					description = <"*">
				>
				["at0087"] = <
					text = <"الولاية/المقاطعة">
					description = <"*">
				>
				["at0088"] = <
					text = <"الرمز البريدي">
					description = <"*">
				>
				["at0089"] = <
					text = <"الدولة/البلد">
					description = <"*">
				>
				["at0090"] = <
					text = <"منزل">
					description = <"*">
				>
				["at0091"] = <
					text = <"القِسم">
					description = <"*">
				>
				["at0092"] = <
					text = <"وحدة تمريضية">
					description = <"*">
				>
				["at0093"] = <
					text = <"مكتب مُزَوِّد الخدمة">
					description = <"*">
				>
				["at0094"] = <
					text = <"المكان السابق للمريض">
					description = <"المكان السابق للمريض">
				>
				["at0095"] = <
					text = <"العنوان">
					description = <"*">
				>
				["at0098"] = <
					text = <"الطبيب الحاضر">
					description = <"الطبيب الحاضر الذي يقدم الخدمات للمريض">
				>
				["at0099"] = <
					text = <"العتصر التعريفي">
					description = <"*">
				>
				["at0100"] = <
					text = <"اسم العائلة">
					description = <"*">
				>
				["at0101"] = <
					text = <"المبنى">
					description = <"*">
				>
				["at0102"] = <
					text = <"الطابق/الدور">
					description = <"*">
				>
				["at0103"] = <
					text = <"وصف الموقع">
					description = <"*">
				>
				["at0104"] = <
					text = <"المؤسسة">
					description = <"*">
				>
				["at0105"] = <
					text = <"العنصر التعريفي للمساحة">
					description = <"*">
				>
				["at0106"] = <
					text = <"العنصر التعريفي الشامل">
					description = <"*">
				>
				["at0107"] = <
					text = <"نوع العنصر التعريفي الشامل">
					description = <"*">
				>
				["at0108"] = <
					text = <"نظام تعريف المجال">
					description = <"*">
				>
				["at0109"] = <
					text = <"العنصر التعريفي الكوني الفريد">
					description = <"*">
				>
				["at0110"] = <
					text = <"HCD">
					description = <"*">
				>
				["at0111"] = <
					text = <"المستوى الصحي السابع">
					description = <"*">
				>
				["at0112"] = <
					text = <"منظمة المعايير الدولية">
					description = <"*">
				>
				["at0113"] = <
					text = <"L, M, N">
					description = <"*">
				>
				["at0114"] = <
					text = <"عشوائي">
					description = <"*">
				>
				["at0115"] = <
					text = <"العنصر التعريفي الكوني الفريد">
					description = <"*">
				>
				["at0116"] = <
					text = <"x400">
					description = <"*">
				>
				["at0118"] = <
					text = <"x500">
					description = <"*">
				>
				["at0119"] = <
					text = <"المؤسسة">
					description = <"*">
				>
				["at0120"] = <
					text = <"الاسم الأخير">
					description = <"*">
				>
				["at0121"] = <
					text = <"الطبيب الاستشاري">
					description = <"الطبيب الاستشاري المسئول عن تقديم الرعاية للمريض, بنا قي ذلك الأخصائي الذي يعمل بأجر, و المسئول الطبي الزائر">
				>
				["at0122"] = <
					text = <"المطالبة الشخصية الخاصة بالعربة من طرف ثالث">
					description = <"*">
				>
				["at0123"] = <
					text = <"التعويضات الأخرى - المسئولية العامة, القانون العمومي, الإهمال الطبي">
					description = <"*">
				>
				["at0124"] = <
					text = <"قسم شئون المحاربين القدامى">
					description = <"*">
				>
				["at0125"] = <
					text = <"إدارة الدفاع">
					description = <"*">
				>
				["at0126"] = <
					text = <"المؤسسة التصحيحية">
					description = <"*">
				>
				["at0127"] = <
					text = <"مستشفى أو قسم عام آخر - رعاية بالتعاقد">
					description = <"*">
				>
				["at0128"] = <
					text = <"اتفاقات الرعاية الصحية التبادلية - مع البلدان/الدول الأخرى">
					description = <"*">
				>
				["at0129"] = <
					text = <"أخرى">
					description = <"*">
				>
				["at0130"] = <
					text = <"غير معروف">
					description = <"*">
				>
			>
		>
	>
	constraint_definitions = <
		["en"] = <
			items = <
				["ac0001"] = <
					text = <"Any term that 'is a' 'Charge price indicator'">
					description = <"*">
				>
			>
		>
		["ar-sy"] = <
			items = <
				["ac0001"] = <
					text = <"أي مصطلح مكافئ لمؤشر ثمن الرعاية">
					description = <"*">
				>
			>
		>
	>
```
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




