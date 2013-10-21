#####Use Case ID: UC-PRS05
#####Use Case Name: Get Provider Preformatted Report

**Level:**                     User Level Goal

**Primary Actors:**            Clerk

**Stakeholders:**              Clerk, Provider

**Purpose:**                   The main intent of this use case is to get print-ready provider report from the provider registry system.

**Pre Condition:**             Clerk must be identified and authenticated.

**Post Condition:**            Provider preformatted report will be accessed successfully.

**Frequency of Occurrence:**   High
__________________________________________________________
**Main Success Scenario: (Get Provider Preformatted Report)**

1. Clerk requests provider preformatted report or “Summary” report.
2. System asks user to enter filtering criteria such as demographic information (name, role, designation).
3. Clerk specifies the filtering criteria.
4. System displays the list of providers ordered by name.
5. Clerk selects the appropriate provider for summary report.
6. System creates the document and sends a standard document transport message **Provider Report Query Response** containing the "Provider Summary" report as an attachment.

_______________________________________________________________________________
**Alternate Flows** 

**Alt-1:Administrative Preformatted Report**

1. Clerk requests provider desired preformatted report or “Consumer Usage” report.
2. System displays the list of all providers ordered by name.
3. Clerk selects the appropriate provider for summary report.
4. System creates the document and sends a standard document transport message **Administrative Report Query Response** containing the "Provider Summary" report as an attachment.

________________________________________________________________________
**Reference Hl7 V3 Interaction Identifiers (Domain: Personnel Management):**

PRPM_ST305100UV01
_______________________________________________________________
**Reference CCHIT Criteria:**

N/A
_______________________________________________________________
**Reference Hl7 RMIM (Domain: Personnel Management):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

![prpm_rm306600uv provider admin report](https://f.cloud.github.com/assets/5391320/1371220/fdca3c98-3a34-11e3-827c-4a4850070c7b.png)

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
