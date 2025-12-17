# Artifacts Summary - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* **Artifacts Summary**

## Artifacts Summary

This page provides a list of the FHIR artifacts defined as part of this implementation guide.

### Behavior: Capability Statements 

The following artifacts define the specific capabilities that different types of systems are expected to have in order to comply with this implementation guide. Systems conforming to this implementation guide are expected to declare conformance to one or more of the following capability statements.

| | |
| :--- | :--- |
| [US Core Client CapabilityStatement](CapabilityStatement-us-core-client.md) | This Section describes the expected capabilities of the US Core Client which is responsible for creating and initiating the queries for information about an individual patient. The complete list of FHIR profiles, RESTful operations, and search parameters supported by US Core Servers are defined in the[Conformance Requirements for Server](CapabilityStatement-us-core-server.md). US Core Clients have the option of choosing from this list to access necessary data based on their local use cases and other contextual requirements. |
| [US Core Client CapabilityStatement2](CapabilityStatement-us-core-client2.md) | This Section describes the expected capabilities of the US Core Client which is responsible for creating and initiating the queries for information about an individual patient. The complete list of FHIR profiles, RESTful operations, and search parameters supported by US Core Servers are defined in the[Conformance Requirements for Server](CapabilityStatement-us-core-server.md). US Core Clients have the option of choosing from this list to access necessary data based on their local use cases and other contextual requirements. |
| [US Core Server CapabilityStatement](CapabilityStatement-us-core-server.md) | This Section describes the expected capabilities of the US Core Server actor which is responsible for providing responses to the queries submitted by the US Core Requestors. The complete list of FHIR profiles, RESTful operations, and search parameters supported by US Core Servers are defined. Systems implementing this capability statement should meet the ASTP 2015 Common Clinical Data Set (CCDS) access requirement for Patient Selection 170.315(g)(7) and Application Access - Data Category Request 170.315(g)(8) and the ASTP[U.S. Core Data for Interoperability (USCDI) Version 6 July 2025](https://www.healthit.gov/isp/sites/isp/files/2025-07/USCDI-Version-6-July-2025.pdf). |
| [US Core Server UsCoreServerCapabilityStatement2](CapabilityStatement-us-core-server2.md) | This Section describes the expected capabilities of the US Core Server actor which is responsible for providing responses to the queries submitted by the US Core Requestors. The complete list of FHIR profiles, RESTful operations, and search parameters supported by US Core Servers are defined. Systems implementing this capability statement should meet the ASTP 2015 Common Clinical Data Set (CCDS) access requirement for Patient Selection 170.315(g)(7) and Application Access - Data Category Request 170.315(g)(8) and the ASTP[U.S. Core Data for Interoperability (USCDI) Version 6 July 2025](https://www.healthit.gov/isp/sites/isp/files/2025-07/USCDI-Version-6-July-2025.pdf). |

### Behavior: Search Parameters 

These define the properties by which a RESTful server can be searched. They can also be used for sorting and including related resources.

| | |
| :--- | :--- |
| [USCoreAllergyintoleranceClinicalStatus](SearchParameter-us-core-allergyintolerance-clinical-status.md) | **active | inactive | resolved**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreAllergyintolerancePatient](SearchParameter-us-core-allergyintolerance-patient.md) | **Who the sensitivity is for**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreCareTeamRole](SearchParameter-us-core-careteam-role.md) | Returns CareTeam resources with a participant role matching the specified code. |
| [USCoreCareplanCategory](SearchParameter-us-core-careplan-category.md) | **Type of plan**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreCareplanDate](SearchParameter-us-core-careplan-date.md) | **Time period plan covers**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreCareplanPatient](SearchParameter-us-core-careplan-patient.md) | **Who the care plan is for**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreCareplanStatus](SearchParameter-us-core-careplan-status.md) | **draft | active | on-hold | revoked | completed | entered-in-error | unknown**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreCareteamPatient](SearchParameter-us-core-careteam-patient.md) | **Who care team is for**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreCareteamStatus](SearchParameter-us-core-careteam-status.md) | **proposed | active | suspended | inactive | entered-in-error**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreConditionAbatementDate](SearchParameter-us-core-condition-abatement-date.md) | **Date-related abatements (dateTime and period)**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreConditionAssertedDate](SearchParameter-us-core-condition-asserted-date.md) | Returns conditions with an[assertedDate extension](http://hl7.org/fhir/StructureDefinition/condition-assertedDate)matching the specified date (dateTime). |
| [USCoreConditionCategory](SearchParameter-us-core-condition-category.md) | **The category of the condition**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreConditionClinicalStatus](SearchParameter-us-core-condition-clinical-status.md) | **The clinical status of the condition**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreConditionCode](SearchParameter-us-core-condition-code.md) | **Code for the condition**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreConditionEncounter](SearchParameter-us-core-condition-encounter.md) | **Encounter created as part of**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreConditionLastUpdated](SearchParameter-us-core-condition-lastupdated.md) | **When the resource version last changed**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreConditionOnsetDate](SearchParameter-us-core-condition-onset-date.md) | **Date related onsets (dateTime and Period)**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreConditionPatient](SearchParameter-us-core-condition-patient.md) | **Who has the condition?**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreConditionRecordedDate](SearchParameter-us-core-condition-recorded-date.md) | **Date record was first recorded**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreRace](SearchParameter-us-core-race.md) | Returns patients with a race extension matching the specified code. |

### Structures: Resource Profiles 

These define constraints on FHIR resources for systems conforming to this implementation guide.

| | |
| :--- | :--- |
| [US Core ADI DocumentReference Profile](StructureDefinition-us-core-adi-documentreference.md) | The US Core Advance Directive Information (ADI) DocumentReference Profile inherits from the FHIR[DocumentReference](https://hl7.org/fhir/R4/documentreference.html)resource; refer to it for scope and usage definitions. It sets minimum expectations for searching and fetching patient Advance Directive Information (ADI) documents using the DocumentReference resource. Examples of advance healthcare directive documents include physician order for life sustaining treatment (POLST), do not resuscitate order (DNR), and medical power of attorney. In addition to the document contents, it communicates the type of advance directive document, the author, the verifier, and other properties. To represent whether advance directive documents exist for a patient, see the[US Core Observation ADI Documentation Profile](StructureDefinition-us-core-observation-adi-documentation.md). To represent orders based on an individual's Portable Medical Order (PMO), see the[US Core PMO ServiceRequest Profile](StructureDefinition-us-core-pmo-servicerequest.md). This profile sets minimum expectations for searching and fetching patient ADI documents using the DocumentReference resource. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core AllergyIntolerance Profile](StructureDefinition-us-core-allergyintolerance.md) | The US Core AllergyIntolerance Profile inherits from the FHIR[AllergyIntolerance](https://hl7.org/fhir/R4/allergyintolerance.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the AllergyIntolerance resource to record, search, and fetch allergies/adverse reactions associated with a patient. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core CarePlan Profile](StructureDefinition-us-core-careplan.md) | The US Core CarePlan Profile inherits from the FHIR[CarePlan](https://hl7.org/fhir/R4/careplan.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the CarePlan resource to record, search, and fetch assessment and plan of treatment data associated with a patient. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core CareTeam Profile](StructureDefinition-us-core-careteam.md) | The US Core CareTeam Profile inherits from the FHIR[CareTeam](https://hl7.org/fhir/R4/careteam.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the CareTeam resource for identifying the Care Team members associated with a patient to promote interoperability and adoption through common implementation. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core Pediatric Weight for Height Observation Profile](StructureDefinition-pediatric-weight-for-height.md) | US Core Pediatric Weight for Height Observation Profile inherits from the US Core Vital Signs Profile. This profile sets minimum expectations for the Observation resource to record, search, and fetch pediatric weight-for-length per age and sex observations in FHIR with a standard LOINC code and UCUM units of measure. It specifies which**additional**core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |

