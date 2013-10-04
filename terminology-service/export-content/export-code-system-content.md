#####Use Case ID: UC-TS05
#####Use Case Name: IExport Code system Content

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Administrator  

**Stakeholders:**              Terminology Provider, Terminology User

**Purpose:**                   The main intent of this use case is to export the code system content to the specified location.

**Pre Condition:**             Terminology Administrator must be identified and authenticated. Code System contents source is available for export.

**Post Condition:**            Code system is exported to the required location.

**Frequency of Occurrence:**   low

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  Medium
__________________________________________________________
**Main Success Scenario: (Import Code System Revision)**

1.	Terminology Admin selects the export code system content option.
2.	System asks user to select the code system, its version and export format as well as to specify the subset criteria (option) and target location.
3.	Terminology Admin selects the code system properties and specifies the subset criteria and target location.
4.	System validates the filtering criteria and target location.
5.	System exports the code system source to the specified location.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Unrecognized location input.
2.	Code system source is not exportable by terminology export tools. 

_______________________________________________________________
**Open Issues**

Terminology content format variations to support.
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-
