#####Use Case ID: UC-TS02
#####Use Case Name: Import Code System Revision

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Administrator  

**Stakeholders:**              Terminology Provider, Terminology User

**Purpose:**                   The main intent of this use case is to import code system revision to make it available to the terminology users through Terminology Server.

**Pre Condition:**             Terminology Administrator must be identified and authenticated. Terminology Administrator must have access to code system revision provided by the terminology provider.

**Post Condition:**            Imported code system revision is converted into format that terminology server supports. Code System is available for access via the terminology server.

**Frequency of Occurrence:**   low

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Import Code System Revision)**

1.	Terminology Admin selects the import code system revision option.
2.	System asks user to specify the current code system Id, description, current code system version Id, new version Id, scope of replacement (description) and location of the file containing code system contents.
3.	Terminology Admin enters the details of the new code system version and specifies the current code system Id.
4.	System perform following actions;
    * Import new code system version file and validate its structure.
    * Convert the vocabulary contents into CTS supported format.
    * Log all activities and display information (error report and succession report).
5.	The system will also notify users who registered for content update notifications.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1. Code system not found at source location.
2. Supplied contents cannot be processed.

_______________________________________________________________
**Open Issues**

Code System format variations to be supported by STS.
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

