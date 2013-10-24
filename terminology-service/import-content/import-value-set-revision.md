#####Use Case ID: UC-TS03
#####Use Case Name: Import Value-Set Revision

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Administrator  

**Stakeholders:**              Terminology Provider, Terminology User

**Purpose:**                   The main intent of this use case is to import value set version to make it available to the terminology users through Terminology Server.

**Pre Condition:**             Terminology Administrator must be identified and authenticated. Terminology Administrator must have access to value set version provided by the terminology provider.

**Post Condition:**            Imported value set version is converted into format that terminology server supports. Value set version is available for access via the terminology server.

**Frequency of Occurrence:**   low

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Import Value-Set Revision)**

1.	Terminology Admin selects the import value set version option.
2.	System asks user to specify the details of value set (Id, Version, Description )
3.	Terminology Admin enters the details of the value set version.
4.	System asks user to specify the location of the file.
5.	Terminology Admin specifies the location of the file containing value set contents.
6.	System perform following actions:
    * Import new value set version file and validate its structure.
    * Convert the vocabulary contents into CTS supported format.
    * Log all activities and display information (error report and succession report).
7.	The system will also notify users who registered for content update notifications.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Value set not found at source location
2.	Supplied contents cannot be processed 

_______________________________________________________________
**Open Issues**

Value set version format variations to be supported by STS.
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-

_______________________________________________________________
**Reference Hl7 RMIM (Domain: CTS):** [More Details](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=306)

-NA-

_______________________________________________________________
**Reference FHIR Resource:** [More Details](http://www.hl7.org/implement/standards/fhir/resourcelist.html)

-NA-
_______________________________________________________________
**Reference CDA Template:** [More Details](http://www.hl7.org/Special/committees/structure/index.cfm)

-NA-
_______________________________________________________________
**Reference OpenEHR Archetypes (Version 1.4):** [More Details](http://www.openehr.org/ckm/)

-NA-

