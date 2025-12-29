# Artifacts Summary - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* **Artifacts Summary**

## Artifacts Summary

This page provides a list of the FHIR artifacts defined as part of this implementation guide.

### Behavior: Capability Statements 

The following artifacts define the specific capabilities that different types of systems are expected to have in order to comply with this implementation guide. Systems conforming to this implementation guide are expected to declare conformance to one or more of the following capability statements.

| | |
| :--- | :--- |
| [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md) | This Section describes the expected capabilities of the US Core Client which is responsible for creating and initiating the queries for information about an individual patient. The complete list of FHIR profiles, RESTful operations, and search parameters supported by US Core Servers are defined in the[Conformance Requirements for Server](CapabilityStatement-us-core-server.md). US Core Clients have the option of choosing from this list to access necessary data based on their local use cases and other contextual requirements. |
| [US Core Server CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-server-liquid.md) | This Section describes the expected capabilities of the US Core Server actor which is responsible for providing responses to the queries submitted by the US Core Requestors. The complete list of FHIR profiles, RESTful operations, and search parameters supported by US Core Servers are defined. Systems implementing this capability statement should meet the ASTP 2015 Common Clinical Data Set (CCDS) access requirement for Patient Selection 170.315(g)(7) and Application Access - Data Category Request 170.315(g)(8) and the ASTP[U.S. Core Data for Interoperability (USCDI) Version 6 July 2025](https://www.healthit.gov/isp/sites/isp/files/2025-07/USCDI-Version-6-July-2025.pdf). |

### Behavior: Search Parameters 

These define the properties by which a RESTful server can be searched. They can also be used for sorting and including related resources.

| | |
| :--- | :--- |
| [USCoreObservationCategory](SearchParameter-us-core-observation-category.md) | **The classification of the type of observation**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreObservationCode](SearchParameter-us-core-observation-code.md) | **The code of the observation type**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreObservationDate](SearchParameter-us-core-observation-date.md) | **Obtained date/time. If the obtained element is a period, a date that falls in the period**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreObservationLastUpdated](SearchParameter-us-core-observation-lastupdated.md) | **When the resource version last changed**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreObservationPatient](SearchParameter-us-core-observation-patient.md) | **The subject that the observation is about (if patient)**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreObservationStatus](SearchParameter-us-core-observation-status.md) | **The status of the observation**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |

### Structures: Resource Profiles 

These define constraints on FHIR resources for systems conforming to this implementation guide.

| | |
| :--- | :--- |
| [US Core Laboratory Result Observation Profile](StructureDefinition-us-core-observation-lab.md) | The US Core Laboratory Result Observation Profile is based upon the US Core Observation Clinical Result Profile and, along with the US Core DiagnosticReport Profile for Laboratory Results Reporting, meets the U.S. Core Data for Interoperability (USCDI) Laboratory requirements. Laboratory results are grouped and summarized using the DiagnosticReport resource, which references Observation resources. Each Observation resource represents an individual laboratory test and result value, a “nested” panel (such as a microbial susceptibility panel) that references other observations, or rarely a laboratory test with component result values. The US Core Laboratory Result Observation Profile sets minimum expectations for the Observation resource to record, search, and fetch laboratory test results associated with a patient to promote interoperability and adoption through common implementation. It identifies which core elements, extensions, vocabularies, and value sets SHALL be present in the resource and constrains the way the elements are used when using this profile. It provides the floor for standards development for specific use cases. |
| [US Core Observation ADI Documentation Profile](StructureDefinition-us-core-observation-adi-documentation.md) | The US Core Observation Advance Directive Information (ADI) Documentation Profile inherits from the FHIR[Observation](https://hl7.org/fhir/R4/observation.html)resource; refer to it for scope and usage definitions. This profile and the[US Core Observation ADI DocumentationReference Profile](StructureDefinition-us-core-adi-documentreference.md)meet the[U.S. Core Data for Interoperability (USCDI)](https://www.healthit.gov/isp/united-states-core-data-interoperability-uscdi)**Advance Directive Observation**Data Element requirements. It is used to communicate whether a person has advance directive information (ADI) and, if one or more documents exist, their location. Examples of advance healthcare directive documents include physician order for life sustaining treatment (POLST), do not resuscitate order (DNR), and medical power of attorney. To communicate the type of advance directive document, the author, the verifier, and other properties, see the US Core ADI DocumentReference Profile. This profile sets minimum expectations for the Observation resource to record, search, and fetch findings about the presence of a patient's advance directives. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core Observation Clinical Result Profile](StructureDefinition-us-core-observation-clinical-result.md) | The US Core Observation Clinical Result Profile is based upon the core FHIR Observation Resource and, along with the US Core DiagnosticReport Profile, meets the US Core Data for Interoperability (USCDI) requirements for**Diagnostic Imaging**and**Clinical Tests**Data Classes. This profile sets minimum expectations for the Observation resource to record and search non-laboratory clinical test results (e.g., radiology and other clinical observations generated from procedures). An example would be when a gastroenterologist reports the size of a polyp observed during a colonoscopy. This profile is the basis for the US Core Laboratory Result Observation Profile, which defines additional data elements to record and search laboratory test results.The US Core Observation Clinical Result Profile sets minimum expectations to promote interoperability and adoption through common implementation. It identifies which core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains the way the elements are used when using this profile. It provides the floor for standards development for specific use cases. |
| [US Core Patient Profile](StructureDefinition-us-core-patient.md) | The US Core Patient Profile inherits from the FHIR[Patient](https://hl7.org/fhir/R4/patient.html)resource; refer to it for scope and usage definitions. This profile meets the requirements of the[U.S. Core Data for Interoperability (USCDI)](https://www.healthit.gov/isp/united-states-core-data-interoperability-uscdi)**Patient Demographics/Information**Data Class. It sets minimum expectations for the Patient resource to record, search, and fetch basic demographics and other administrative information about an individual patient. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |

### Example: Example Instances 

These are example instances that show what data produced and consumed by systems conforming with this implementation guide might look like.

| | |
| :--- | :--- |
| [AllergyIntolerance Example](AllergyIntolerance-example.md) | This is a allergyintolerance example for the**US Core AllergyIntolerance Profile**. |

