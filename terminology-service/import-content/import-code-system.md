#####Use Case ID: UC-TS01
#####Use Case Name: Import Code System

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Administrator  

**Stakeholders:**              Terminology Provider, Terminology User

**Purpose:**                   Purpose	The main intent of this use case is to import code system contents to make it available to the terminology users through Terminology Server.

**Pre Condition:**             Terminology Administrator must be identified and authenticated. Terminology Administrator must have access to code system contents provided by the terminology provider.

**Post Condition:**            Imported code system is converted into format that terminology server supports. Code System is available for access via the terminology server.

**Frequency of Occurrence:**   low

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  High
__________________________________________________________
**Main Success Scenario: (Import Code System)**

1.	Terminology Admin selects the import code system option.
2.	System asks user to specify the web or local file containing code system contents.
3.	Terminology Admin specifies the Code System Id, description, version, administrative info and web or local file containing code system contents.
4.	System perform following actions;
    * Import whole code system file and validate its structure.
    * Convert the code system contents into CTS supported format.
    * Log all activities and display information (error report and succession report).

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Code system not found at source location.
2.	Supplied contents cannot be processed. 

_______________________________________________________________
**Open Issues**

Code System format variations to be supported by STS.
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-
