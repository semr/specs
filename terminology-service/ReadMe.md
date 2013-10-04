1. Module Scope
---------------

Terminology services represent functions necessary to manage, search, and access terminology content. Terminology services provide a consistent specification for accessing and managing terminology content, independent of the terminology content and underlying technology stack. Terminology content represents various resources including lists, value sets, taxonomies, and formal description logic based ontologies. The following thematic areas are considered in scope for STS.

* **Administration:** 
This is a set of functionality that provides the ability to manage content as part of a terminology service. Administration functions include the ability to load terminologies, export terminologies, as well as the management of notifications. These functions are generally protected and accessible by service administrators with appropriate authorization.

* **Search / Query:** 
This is a set of functionality that provides the ability to find concepts based on some search criteria. This includes restrictions to specific associations or other attributes of the terminology, including navigation of associations for result sets. This represents the primary utility for using terminology content in a number of application contexts. The CTS 2 Query Profile includes capabilities for searching and querying terminology content as well as representing terminology content in the appropriate formats.

* **Authoring / Maintenance:**
This is a set of functionality that provides the ability to create and maintain content. From a terminology service perspective, this would include the appropriate APIs to add, change, or delete concepts and associations. This would also include the processing of change events from various terminology providers.

* **Associations:**
This is a set of functionality that provides the ability to map concepts and the concept's associated attributes from a source terminology to a concept in a target terminology, or create relationships between concepts within a single code system.

2. Module Perspective
---------------------
One of the fundamental goals of computerized medical information is that of precise, accurate and unambiguous communication. An unambiguous communication requires shared understanding of the terminologies being used. Structured terminologies provide the semantics of the concepts being conveyed in an electronic message or record. But being able to predictably access terminological content is still necessary. The problems around terminology should not be resolved using a common data repository. Historically, this approach has been tried, and with some success. However, experience shows that in order to share functionality and content, a hub and spokes model forcing terminology consumers to use a common hub is more intrusive for users and introduces adoption barriers, especially in distributed environments. This system has the aim to overcome such barriers by a separation of behavior (software functionality) from content (the deployed terminologies). This way, in an implementation, adopters can chose the terminology contents they want and use the service functionality to provide the system behavior which is specific to their needs

![cts-arch](https://f.cloud.github.com/assets/4283040/1224445/db134c50-274a-11e3-84fb-70bbaff6d711.PNG)

3. Module Functions 
-------------------
The STS is intended to allow the look up and management of a wide variety of terminology components, including, but not limited to, Concepts, Associations, and Value Sets. This includes the ability to resolve content bound to a specific Concept Domain. At the functional level, the service interface will explicitly allow the query, definition, publication, and modification of the different terminology components that are required of terminologies and terminology services. The scope of this STS covers support for multiple terminology standards and a federated terminology environment.

4. User Classes and Characteristics 
-----------------------------------
Actors will use the terminology service for different purposes. These different actors can be generalized into a basic Terminology User an Actor that is simply an individual, organization, or application that requires access to terminology content for some purpose. Specializations of the Terminology User actor participate in additional operational specific scenarios. Actors described in this section are not necessarily human actors, but also include organizations and systems. Figure outlines the specializations and composition of the different actors used in this specification. These actors are described below.

![user-categories-of-ts](https://f.cloud.github.com/assets/4283040/1224469/8cd6fd42-274b-11e3-85d9-2e0d771afb3c.PNG)

The following actors take a role in the Scheduling service actors:

| **Name**        | **Description**               | **Responsibilities**                                         |      
|-----------------|-------------------------------|--------------------------------------------------------------|
|**Terminology User**| End User of Service| A Terminology User is an actor such as a subject matter expert, terminologist or terminology enabled application. Terminology User activities include, but are not limited to, querying for specific concept codes and browsing or comparing value sets. Specializations of the Terminology User actor follow below.
|**CTS2 Service** | Terminology Server| The CTS 2 Service is a specific implementation of the CTS 2 Terminology Server.
|**Terminology Administrator** | End User of the Service| Users belonging to this category are responsible for requesting for scheduling an appointment via phone or through direct interaction with assistant.  
|**Terminology Enabled Application Developer** | End User of the Service | User belonging to this category is responsible for the development of software applications that make explicit use of controlled terminologies.
|**Terminology Author / Curator** | End User of the Service| A Terminology Author / Curator is an actor who is responsible maintaining terminology content, including but not limited to, the development of new concepts and associations that may be submitted to the Terminology Provider or the extension of an existing terminology with local concepts. This may also determine who can validate and perform quality control of terminology content.
|**Terminology Human Language Translator** | End User of the Service | An actor with domain knowledge who is also familiar with the languages and dialects which they are responsible for translating.
|**Terminology Mapper** | End User of the Service | A Terminology Mapper is an actor (human or system) that is responsible for creating or maintaining specialized associations, or "mappings" between concepts from different code systems.
|**Terminology Provider** | End User of the Service | An actor responsible for the development of Terminology Content.
|**Terminology ValueSet Developer** | Terminology Server| An actor with specific domain knowledge, as well as expertise in controlled terminologies who develop s and maintains domain-or application-specific terminology value sets.

5. System Features
------------------
Following are the system features of the STS:

![usecasemodel](https://f.cloud.github.com/assets/4283040/1243024/1fd85cf0-2a5b-11e3-8ccc-691329bbf630.jpg)
