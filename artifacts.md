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
| [US Core AllergyIntolerance Profile](StructureDefinition-us-core-allergyintolerance.md) | The US Core AllergyIntolerance Profile inherits from the FHIR[AllergyIntolerance](https://hl7.org/fhir/R4/allergyintolerance.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the AllergyIntolerance resource to record, search, and fetch allergies/adverse reactions associated with a patient. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core DocumentReference Profile](StructureDefinition-us-core-documentreference.md) | The US Core DocumentReference Profile inherits from the FHIR[DocumentReference](https://hl7.org/fhir/R4/documentreference.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for searching and fetching patient documents including Clinical Notes using the DocumentReference resource. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. Before reviewing this profile, implementers are encouraged to read the Clinical Notes Guidance to understand the overlap of the US Core DiagnosticReport Profile for Report and Note exchange and the US Core DocumentReference Profile. |
| [US Core Heart Rate Profile](StructureDefinition-us-core-heart-rate.md) | The US Core Heart Rate Profile inherits from the US Core Vital Signs Profile. This profile sets minimum expectations for the Observation resource to record, search, and fetch heart rate observations with a standard LOINC code and UCUM units of measure. It specifies which**additional**core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core MedicationRequest Profile](StructureDefinition-us-core-medicationrequest.md) | The US Core MedicationRequest Profile inherits from the FHIR[MedicationRequest](https://hl7.org/fhir/R4/medicationrequest.html)resource; refer to it for scope and usage definitions. This profile meets the requirements of the[U.S. Core Data for Interoperability (USCDI)](https://www.healthit.gov/isp/united-states-core-data-interoperability-uscdi)**Medications**Data Class. This profile sets minimum expectations for the MedicationRequest resource to record, search, and fetch a patient's medication prescriptions or orders. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core Observation Pregnancy Status Profile](StructureDefinition-us-core-observation-pregnancystatus.md) | The US Core Pregnancy Status Observation Profile inherits from the FHIR[Observation](https://hl7.org/fhir/R4/observation.html)resource; refer to it for scope and usage definitions. This profile meets the requirements of the U.S. Core Data for Interoperability (USCDI)**Pregnancy Status**Data Element. It sets minimum expectations for the Observation resource to record, search, and fetch the patient's state or condition of being pregnant. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core Organization Profile](StructureDefinition-us-core-organization.md) | The US Core Organization Profile inherits from the FHIR[Organization](https://hl7.org/fhir/R4/organization.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the Organization resource to record, search, and fetch patient or provider organziation information. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core PractitionerRole Profile](StructureDefinition-us-core-practitionerrole.md) | The US Core PractitionerRole Profile inherits from the FHIR[PractitionerRole](https://hl7.org/fhir/R4/practitionerrole.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the PractitionerRole Resource to record, search, and fetch the practitioner role information. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. The requirements for the US Core Practitioner were drawn from the[Argonaut Provider Directory](http://www.fhir.org/guides/argonaut/pd//release1/index.html),[IHE Healthcare Provider Directory](http://ihe.net/uploadedFiles/Documents/ITI/IHE_ITI_Suppl_HPD.pdf)and the[ONC Provider Directory Workshop](https://confluence.oncprojectracking.org/display/PDW/Workshop+Documents). |
| [US Core Vital Signs Profile](StructureDefinition-us-core-vital-signs.md) | This profile is based on the base[FHIR Vital Signs Profile](http://hl7.org/fhir/R4/observation-vitalsigns.html)and defines**additional**constraints on the Observation resource to represent vital signs observations. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. This US Core profiles that are derived from this profile are listed below. |

### Structures: Extension Definitions 

These define constraints on FHIR data types for systems conforming to this implementation guide.

| | |
| :--- | :--- |
| [US Core Direct email Extension](StructureDefinition-us-core-direct.md) | This email address is associated with a["Direct Secure Messaging"](https://directtrust.org/what-we-do/direct-secure-messaging)service. This extension can only be used on contact points where the system = 'email' |
| [US Core Ethnicity Extension](StructureDefinition-us-core-ethnicity.md) | Concepts classifying the person into a named category of humans sharing common history, traits, geographical origin or nationality. The ethnicity codes used to represent these concepts are based upon the[Race & Ethnicity - CDC (CDCREC)](https://phinvads.cdc.gov/vads/ViewCodeSystem.action?id=2.16.840.1.113883.6.238)code system. Detailed ethnicity concepts are grouped by and pre-mapped to the 2 OMB ethnicity categories:* Hispanic or Latino
* Not Hispanic or Latino.
 |
| [US Core Individual Sex Extension](StructureDefinition-us-core-individual-sex.md) | USCDI includes a data element for Sex, intended to support the exchange of a recorded sex value. This extension aligns with the USCDI definition of Sex: "Documentation of a specific instance of sex." It enables systems to share the sex value as it was documented in a particular context. Systems choosing to record sources of information should use the[Provenance resource](http://hl7.org/fhir/R4/element-level-provenance.html). |
| [US Core Race Extension](StructureDefinition-us-core-race.md) | Concepts classifying the person into a named category of humans sharing common history, traits, geographical origin or nationality. The race codes used to represent these concepts are based upon the[Race & Ethnicity - CDC (CDCREC)](https://phinvads.cdc.gov/vads/ViewCodeSystem.action?id=2.16.840.1.113883.6.238)code system. Detailed race concepts are grouped by and pre-mapped to the 5 OMB race categories:* American Indian or Alaska Native
* Asian
* Black or African American
* Native Hawaiian or Other Pacific Islander
* White.
 |
| [US Core Sex Extension](StructureDefinition-us-core-sex.md) | The Sex Extension is used to reflect the documentation of a person's sex. Systems choosing to record sources of information should use the[Provenance resource](http://hl7.org/fhir/R4/element-level-provenance.html).USCDI includes a data element for sex, intended to support the exchange of a sex value that is not characterized as sex assigned at birth or birth sex. This Sex extension supports USCDI. Sex assigned at birth or birth sex can be recorded using the more specific[US Core Birth Sex Extension](StructureDefinition-us-core-birthsex.md). Future versions of this extension may be informed by the content of the HL7 Cross Paradigm IG: Gender Harmony - Sex and Gender Representation, which may include additional guidance on its relationship to administrative gender ([Patient.gender](StructureDefinition-us-core-patient-definitions.md#Patient.gender)). |
| [US Core USCDI Requirement Extension](StructureDefinition-uscdi-requirement.md) | **This extension is only used in the US Core Implementation Guide''s Profile StructureDefinition elements.**It flags elements that are**Additional**USCDI Requirements for certified systems. In other words, elements that are not marked as Must Support but are required for ASTP Health IT certification testing. See the[Conformance page](general-requirements.md)for more information. |

### Example: Example Instances 

These are example instances that show what data produced and consumed by systems conforming with this implementation guide might look like.

| | |
| :--- | :--- |
| [AllergyIntolerance Example](AllergyIntolerance-example.md) | This is a allergyintolerance example for the**US Core AllergyIntolerance Profile**. |

