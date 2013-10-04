#####Use Case ID: UC-TS06
#####Use Case Name: IExport Code system Content

**Level:**                     User Level Goal

**Primary Actors:**            Terminology Administrator  

**Stakeholders:**              Terminology User

**Purpose:**                   The main intent of this use case is to export associations to the specified location.

**Pre Condition:**             Terminology Administrator must be identified and authenticated. Associations’ source is available for export.

**Post Condition:**            Association source is exported to the required location.

**Frequency of Occurrence:**   low

**Conformance:**             	 CTS2 (Common Terminology Standard)

**Priority:**                  Medium
__________________________________________________________
**Main Success Scenario: (Import Code System Revision)**

1.	Terminology Admin selects the export association type instances option.
2.	System asks user to specify the details (code system Id, code system version, association types, filter criteria and export format) of association type.
3.	Terminology Admin enters the details of required association content.
4.	 System validates the filtering criteria and target location.
5.	System exports the association source to the specified location.

__________________________________________________________
**Alternate Flows** 

**Alt-1:**

1.	Invalid criteria/format input
2.	Unrecognized location input
3.	Association source is not exportable  

_______________________________________________________________
**Open Issues**

Terminology content format variations to support.
_______________________________________________________________
**Reference Hl7 V3 Interaction Identifiers:**

-NA-
_______________________________________________________________
**Reference CCHIT Criteria:**

-NA-
