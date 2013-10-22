#####Use Case ID: UC-PRS01
#####Use Case Name: Add Provider

**Level:**                     User Level Goal

**Primary Actors:**            Registration Clerk (RC)

**Stakeholders:**              Registration Clerk, Healthcare Provider

**Purpose:**                   The main intent of this use case is to add provider details.

**Pre Condition:**             RC must be identified and authenticated.

**Post Condition:**            Provider identifiers and demographics will be recorded in local provider
registry successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Add Provider)**

1. RC requests the system to add provider’s registry.
2. System asks user to enter provider’s full information including name, Id, role identifier,
certification document, work locations and disciplinary actions etc.
3. RC enters the required information.
4. System then performs following steps:
  * Validates the entered information.
  * Associates key identifiers information (i.e Id, state medical license, DEA) with provider record.
  * Stores provider record in separate discrete data fields successfully.

______________________________________________________________________________
**Alternate Flows** 

**Alt-1**

1. Invalid information cannot be added.
2. Invalid identifier.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Personnel Management):**

PRPM_ST301000UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

AM 27.01, AM 27.02, AM 27.04
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Domain: Personnel Management):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpm_rm301000uv add provider](https://f.cloud.github.com/assets/5391320/1371216/ec6718d6-3a34-11e3-8e43-2e30db85abbd.png)

_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

![practitioner fhir resource](https://f.cloud.github.com/assets/5391320/1371206/b4705898-3a34-11e3-85cc-9aa08e1cd116.png)
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

N/A
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

OpenEHR Archetype: (Individual Provider)

``` Archetype
archetype (adl_version=1.4)
	openEHR-DEMOGRAPHIC-ROLE.individual_provider.v1

concept
	[at0000]	-- Profissional de saúde
language
	original_language = <[ISO_639-1::pt-br]>
	translations = <
		["en"] = <
			language = <[ISO_639-1::en]>
			author = <
				["name"] = <"Sergio Miranda Freire">
				["organisation"] = <"Universidade do Estado do Rio de Janeiro - UERJ">
				["email"] = <"sergio@lampada.uerj.br">
			>
		>
	>
description
	original_author = <
		["name"] = <"Sergio Miranda Freire & Rigoleta Dutra Mediano Dias">
		["organisation"] = <"Universidade do Estado do Rio de Janeiro - UERJ">
		["email"] = <"sergio@lampada.uerj.br">
		["date"] = <"22/05/2009">
	>
	details = <
		["en"] = <
			language = <[ISO_639-1::en]>
			purpose = <"Representation of an individual healthcare provider demographic data.">
			use = <"Used in demographic service to collect a individual healthcare provider's data.">
			keywords = <"demographic service", "individual healthcare provider">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
		["pt-br"] = <
			language = <[ISO_639-1::pt-br]>
			purpose = <"Representação de dados de uma pessoa exercendo o papel Profissional de Saúde.">
			use = <"Usado em serviços demográficos para coletar dados sobre profissionais de saúde.">
			keywords = <"serviço demográfico", "profissional de saúde">
			misuse = <"">
			copyright = <"© openEHR Foundation">
		>
	>
	lifecycle_state = <"Authordraft">
	other_contributors = <"Sebastian Garde, Ocean Informatics, Germany (Editor)", "Omer Hotomaroglu, Turkey (Editor)", "Heather Leslie, Ocean Informatics, Australia (Editor)">

definition
    ROLE[at0000] matches {  -- Individual healthcare provider 
        identities matches {
            allow_archetype PARTY_IDENTITY[at0001] occurrences matches {1..1} matches {
                include
                    archetype_id/value matches {/(person_name)[a-zA-Z0-9_-]*\.v1/}
            }
        }
        capabilities matches {
  		allow_archetype CAPABILITY[at0002] occurrences matches {0..*} matches {
                    include
                        archetype_id/value matches {/(individual_credentials)[a-zA-Z0-9_-]*\.v1/}
                }
        }
        contacts matches {
            CONTACT[at0003] occurrences matches {0..*} matches {  -- Contacts
                addresses matches {
                    allow_archetype ADDRESS[at0030] occurrences matches {1..1} matches {
                        include
                            archetype_id/value matches {/(address)([a-zA-Z0-9_]+)*\.v1/}
                            archetype_id/value matches {/(electronic_communication)[a-zA-Z0-9_-]*\.v1/}
                    }
                }
            }
        }
        relationships matches {
            PARTY_RELATIONSHIP[at0004] occurrences matches {0..*} matches {  -- Relationship with a third-party payer
                details matches {
                    ITEM_TREE[at0040] occurrences matches {0..1} matches {  -- Details
                        items cardinality matches {1..1; unordered; unique} matches {
                            allow_archetype CLUSTER[at0041] occurrences matches {1..1} matches {
                                include
                                    archetype_id/value matches {/(provider_identifier)[a-zA-Z0-9_-]*\.v1/}
                            }
                        }
                    }
                }
            }
            PARTY_RELATIONSHIP[at0005] occurrences matches {0..*} matches {  -- Employment relationship
                details matches {
                    ITEM_TREE[at0050] occurrences matches {0..1} matches {  -- Details
                        items cardinality matches {1..*; ordered} matches {
                            allow_archetype CLUSTER[at0051] occurrences matches {1..1} matches {
                                include
                                    archetype_id/value matches {/(provider_identifier)[a-zA-Z0-9_-]*\.v1/}
                            }
                            ELEMENT[at0052] occurrences matches {0..1} matches {  -- role
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
		["pt-br"] = <
			items = <
				["at0000"] = <
					text = <"Profissional de saúde">
					description = <"Dados sobre uma pessoa que exerce o papel de um profissional de saúde.">
				>
				["at0001"] = <
					text = <"Nome do profissional">
					description = <"Nome do profissional de saúde.">
				>
				["at0002"] = <
					text = <"Capacitação">
					description = <"Capacitação do Profissional.">
				>
				["at0003"] = <
					text = <"Contato">
					description = <"Contato do profissional de saúde.">
				>
				["at0004"] = <
					text = <"Relacionamento com uma fonte pagadora">
					description = <"Relacionamento entre um profissional de saúde e uma fonte pagadora.">
				>
				["at0005"] = <
					text = <"Relacionamento empregador/empregado">
					description = <"Relacionamento empregador/empregado entre um profissional de saúde e uma organização prestadora de assistência à saúde.">
				>
				["at0030"] = <
					text = <"Endereço">
					description = <"Endereço onde o profissional pode ser contactado.">
				>
				["at0040"] = <
					text = <"Detalhes">
					description = <"Detalhes do relacionamento profissional/fonte pagadora.">
				>
				["at0041"] = <
					text = <"Documento de Identificação">
					description = <"A identificação do profissional de saúde junto à fonte pagadora.">
				>
				["at0050"] = <
					text = <"Detalhes">
					description = <"Detalhes do relacionamento profissional de saúde/prestador de assistência.">
				>
				["at0051"] = <
					text = <"Documento de Identificação">
					description = <"Identificação do profissional de saúde junto à organização prestadora de assistência à saúde.">
				>
				["at0052"] = <
					text = <"Função">
					description = <"A função do profissional de saúde junto à organização prestadora de assistência à saúde.">
				>
			>
		>
		["en"] = <
			items = <
				["at0000"] = <
					text = <"Individual healthcare provider">
					description = <"Data about a person who performs the role of an individual healthcare provider.">
				>
				["at0001"] = <
					text = <"Name">
					description = <"Individual healthcare provider's name.">
				>
				["at0002"] = <
					text = <"Capability">
					description = <"Individual healthcare provider's capability.">
				>
				["at0003"] = <
					text = <"Contact">
					description = <"Individual healthcare provider's contact.">
				>
				["at0004"] = <
					text = <"Relationship with a third-party payer">
					description = <"Relationship between an individual healthcare provider and a third-party payer.">
				>
				["at0005"] = <
					text = <"Employer/employee relationship">
					description = <"Employer/employee relationship between an individual healthcare provider and a healthcare provider organisation.">
				>
				["at0030"] = <
					text = <"Address">
					description = <"Address where the individual provider can be contacted.">
				>
				["at0040"] = <
					text = <"Relationship details">
					description = <"Details of an individual healthcare provider/third-party payer relationship.">
				>
				["at0041"] = <
					text = <"Identifier">
					description = <"The identifer of the individual healthcare provider at the third-party payer.">
				>
				["at0050"] = <
					text = <"Details">
					description = <"Details of the employer/employee relationship.">
				>
				["at0051"] = <
					text = <"Identifier">
					description = <"The identifer of the individual healthcare provider at the healthcare provider organisation.">
				>
				["at0052"] = <
					text = <"Employment role">
					description = <"The role of the individual healthcare provider at the healthcare provider organisation.">
				>
			>
		>
	>

```
