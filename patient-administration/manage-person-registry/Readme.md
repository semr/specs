####Description
--------------
This module will provide user with the functionality to manage person registries. It will allow
user to define common identifying and demographic elements that might be collected for
persons regardless of the roles. This use case excludes attributes that would likely be
collected only for persons in the role of patient. The functionalities in this feature are broadly
categorized in three categories:

* **Notifications** for state transitions of activated, revised, nullified and obsolete (duplicates
resolved).
* **Queries** for find candidates and get demographics.
* **Requests** for adding and revising records.

![manage-person-registry](https://f.cloud.github.com/assets/5391320/1225373/62dd8686-2765-11e3-89a9-472d26a8d288.png)

####Functional Requirements
* REQ-1:	 Add Person to Person Registry
* REQ-2:	 Revise Person record
* REQ-3: Nullify Person Record
* REQ-4: Resolve Duplicate Records
* REQ-5: Find Candidates
* REQ-6: Get Person Demographics
