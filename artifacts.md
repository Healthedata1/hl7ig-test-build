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
| [US Core ADI DocumentReference Profile](StructureDefinition-us-core-adi-documentreference.md) | The US Core Advance Directive Information (ADI) DocumentReference Profile inherits from the FHIR[DocumentReference](https://hl7.org/fhir/R4/documentreference.html)resource; refer to it for scope and usage definitions. It sets minimum expectations for searching and fetching patient Advance Directive Information (ADI) documents using the DocumentReference resource. Examples of advance healthcare directive documents include physician order for life sustaining treatment (POLST), do not resuscitate order (DNR), and medical power of attorney. In addition to the document contents, it communicates the type of advance directive document, the author, the verifier, and other properties. To represent whether advance directive documents exist for a patient, see the[US Core Observation ADI Documentation Profile](StructureDefinition-us-core-observation-adi-documentation.md). To represent orders based on an individual's Portable Medical Order (PMO), see the[US Core PMO ServiceRequest Profile](StructureDefinition-us-core-pmo-servicerequest.md). This profile sets minimum expectations for searching and fetching patient ADI documents using the DocumentReference resource. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core DocumentReference Profile](StructureDefinition-us-core-documentreference.md) | The US Core DocumentReference Profile inherits from the FHIR[DocumentReference](https://hl7.org/fhir/R4/documentreference.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for searching and fetching patient documents including Clinical Notes using the DocumentReference resource. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. Before reviewing this profile, implementers are encouraged to read the Clinical Notes Guidance to understand the overlap of the US Core DiagnosticReport Profile for Report and Note exchange and the US Core DocumentReference Profile. |
| [US Core Heart Rate Profile](StructureDefinition-us-core-heart-rate.md) | The US Core Heart Rate Profile inherits from the US Core Vital Signs Profile. This profile sets minimum expectations for the Observation resource to record, search, and fetch heart rate observations with a standard LOINC code and UCUM units of measure. It specifies which**additional**core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core MedicationRequest Profile](StructureDefinition-us-core-medicationrequest.md) | The US Core MedicationRequest Profile inherits from the FHIR[MedicationRequest](https://hl7.org/fhir/R4/medicationrequest.html)resource; refer to it for scope and usage definitions. This profile meets the requirements of the[U.S. Core Data for Interoperability (USCDI)](https://www.healthit.gov/isp/united-states-core-data-interoperability-uscdi)**Medications**Data Class. This profile sets minimum expectations for the MedicationRequest resource to record, search, and fetch a patient's medication prescriptions or orders. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core Observation Pregnancy Status Profile](StructureDefinition-us-core-observation-pregnancystatus.md) | The US Core Pregnancy Status Observation Profile inherits from the FHIR[Observation](https://hl7.org/fhir/R4/observation.html)resource; refer to it for scope and usage definitions. This profile meets the requirements of the U.S. Core Data for Interoperability (USCDI)**Pregnancy Status**Data Element. It sets minimum expectations for the Observation resource to record, search, and fetch the patient's state or condition of being pregnant. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core Organization Profile](StructureDefinition-us-core-organization.md) | The US Core Organization Profile inherits from the FHIR[Organization](https://hl7.org/fhir/R4/organization.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the Organization resource to record, search, and fetch patient or provider organziation information. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core PractitionerRole Profile](StructureDefinition-us-core-practitionerrole.md) | The US Core PractitionerRole Profile inherits from the FHIR[PractitionerRole](https://hl7.org/fhir/R4/practitionerrole.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the PractitionerRole Resource to record, search, and fetch the practitioner role information. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. The requirements for the US Core Practitioner were drawn from the[Argonaut Provider Directory](http://www.fhir.org/guides/argonaut/pd//release1/index.html),[IHE Healthcare Provider Directory](http://ihe.net/uploadedFiles/Documents/ITI/IHE_ITI_Suppl_HPD.pdf)and the[ONC Provider Directory Workshop](https://confluence.oncprojectracking.org/display/PDW/Workshop+Documents). |
| [US Core Vital Signs Profile](StructureDefinition-us-core-vital-signs.md) | This profile is based on the base[FHIR Vital Signs Profile](http://hl7.org/fhir/R4/observation-vitalsigns.html)and defines**additional**constraints on the Observation resource to represent vital signs observations. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. This US Core profiles that are derived from this profile are listed below. |

### Example: Example Instances 

These are example instances that show what data produced and consumed by systems conforming with this implementation guide might look like.

| | |
| :--- | :--- |
| [AllergyIntolerance Example](AllergyIntolerance-example.md) | This is a allergyintolerance example for the**US Core AllergyIntolerance Profile**. |

