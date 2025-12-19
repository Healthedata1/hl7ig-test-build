# Artifacts Summary - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* **Artifacts Summary**

## Artifacts Summary

This page provides a list of the FHIR artifacts defined as part of this implementation guide.

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
| [USCoreCoveragePatient](SearchParameter-us-core-coverage-patient.md) | **Retrieve coverages for a patient**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDevicePatient](SearchParameter-us-core-device-patient.md) | **Patient information, if the resource is affixed to a person**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDeviceStatus](SearchParameter-us-core-device-status.md) | **active | inactive | entered-in-error | unknown**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDeviceType](SearchParameter-us-core-device-type.md) | **The type of the device**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDiagnosticreportCategory](SearchParameter-us-core-diagnosticreport-category.md) | **Which diagnostic discipline/department created the report**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDiagnosticreportCode](SearchParameter-us-core-diagnosticreport-code.md) | **The code for the report, as opposed to codes for the atomic results, which are the names on the observation resource referred to from the result**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDiagnosticreportDate](SearchParameter-us-core-diagnosticreport-date.md) | **The clinically relevant time of the report**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDiagnosticreportLastUpdated](SearchParameter-us-core-diagnosticreport-lastupdated.md) | **When the resource version last changed**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDiagnosticreportPatient](SearchParameter-us-core-diagnosticreport-patient.md) | **The subject of the report if a patient**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDiagnosticreportStatus](SearchParameter-us-core-diagnosticreport-status.md) | **The status of the report**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDocumentreferenceCategory](SearchParameter-us-core-documentreference-category.md) | **Categorization of document**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDocumentreferenceDate](SearchParameter-us-core-documentreference-date.md) | **When this document reference was created**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDocumentreferenceId](SearchParameter-us-core-documentreference-id.md) | **Logical id of this artifact**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDocumentreferencePatient](SearchParameter-us-core-documentreference-patient.md) | **Who/what is the subject of the document**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDocumentreferencePeriod](SearchParameter-us-core-documentreference-period.md) | **Time of service that is being documented**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDocumentreferenceStatus](SearchParameter-us-core-documentreference-status.md) | **current | superseded | entered-in-error**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreDocumentreferenceType](SearchParameter-us-core-documentreference-type.md) | **Kind of document (LOINC if possible)**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreEncounterClass](SearchParameter-us-core-encounter-class.md) | **Classification of patient encounter**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreEncounterDate](SearchParameter-us-core-encounter-date.md) | **A date within the period the Encounter lasted**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreEncounterDischargeDisposition](SearchParameter-us-core-encounter-discharge-disposition.md) | Returns encounters with an discharge-disposition matching the specified code. |
| [USCoreEncounterId](SearchParameter-us-core-encounter-id.md) | **Logical id of this artifact**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreEncounterIdentifier](SearchParameter-us-core-encounter-identifier.md) | **Identifier(s) by which this encounter is known**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreEncounterLastUpdated](SearchParameter-us-core-encounter-lastupdated.md) | **When the resource version last changed**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreEncounterLocation](SearchParameter-us-core-encounter-location.md) | **Location the encounter takes place**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreEncounterPatient](SearchParameter-us-core-encounter-patient.md) | **The patient or group present at the encounter**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreEncounterStatus](SearchParameter-us-core-encounter-status.md) | **planned | arrived | triaged | in-progress | onleave | finished | cancelled +**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreEncounterType](SearchParameter-us-core-encounter-type.md) | **Specific type of encounter**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreEthnicity](SearchParameter-us-core-ethnicity.md) | Returns patients with an ethnicity extension matching the specified code. |
| [USCoreFamilymemberhistoryCode](SearchParameter-us-core-familymemberhistory-code.md) | **A search by a condition code**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreFamilymemberhistoryPatient](SearchParameter-us-core-familymemberhistory-patient.md) | **The identity of a subject to list family member history items for**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreGoalDescription](SearchParameter-us-core-goal-description.md) | **The code or text describing the goal****NOTE**: This US Core SearchParameter definition extends the usage context of the[Conformance expectation extension](http://hl7.org/fhir/R4/extension-capabilitystatement-expectation.html)* multipleAnd
* multipleOr
* comparator
* modifier
* chain
 |
| [USCoreGoalLifecycleStatus](SearchParameter-us-core-goal-lifecycle-status.md) | **proposed | planned | accepted | active | on-hold | completed | cancelled | entered-in-error | rejected**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreGoalPatient](SearchParameter-us-core-goal-patient.md) | **Who this goal is intended for**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreGoalTargetDate](SearchParameter-us-core-goal-target-date.md) | **Reach goal on or before**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreImmunizationDate](SearchParameter-us-core-immunization-date.md) | **Vaccination (non)-Administration Date**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreImmunizationPatient](SearchParameter-us-core-immunization-patient.md) | **The patient for the vaccination record**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreImmunizationStatus](SearchParameter-us-core-immunization-status.md) | **Immunization event status**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreLocationAddress](SearchParameter-us-core-location-address.md) | **A (part of the) address of the location**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreLocationAddressCity](SearchParameter-us-core-location-address-city.md) | **A city specified in an address**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreLocationAddressPostalcode](SearchParameter-us-core-location-address-postalcode.md) | **A postal code specified in an address**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreLocationAddressState](SearchParameter-us-core-location-address-state.md) | **A state specified in an address**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreLocationName](SearchParameter-us-core-location-name.md) | **A portion of the location's name or alias**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreMedicationdispensePatient](SearchParameter-us-core-medicationdispense-patient.md) | **The identity of a patient to list dispenses for**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreMedicationdispenseStatus](SearchParameter-us-core-medicationdispense-status.md) | **Returns dispenses with a specified dispense status**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreMedicationdispenseType](SearchParameter-us-core-medicationdispense-type.md) | **Returns dispenses of a specific type**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreMedicationrequestAuthoredon](SearchParameter-us-core-medicationrequest-authoredon.md) | **Return prescriptions written on this date**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreMedicationrequestEncounter](SearchParameter-us-core-medicationrequest-encounter.md) | **Return prescriptions with this encounter identifier**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreMedicationrequestIntent](SearchParameter-us-core-medicationrequest-intent.md) | **Returns prescriptions with different intents**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreMedicationrequestPatient](SearchParameter-us-core-medicationrequest-patient.md) | **Returns prescriptions for a specific patient**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreMedicationrequestStatus](SearchParameter-us-core-medicationrequest-status.md) | **Status of the prescription**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
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
| [USCoreOrganizationAddress](SearchParameter-us-core-organization-address.md) | **A server defined search that may match any of the string fields in the Address, including line, city, district, state, country, postalCode, and/or text****NOTE**: This US Core SearchParameter definition extends the usage context of the[Conformance expectation extension](http://hl7.org/fhir/R4/extension-capabilitystatement-expectation.html)* multipleAnd
* multipleOr
* comparator
* modifier
* chain
 |
| [USCoreOrganizationName](SearchParameter-us-core-organization-name.md) | **A portion of the organization's name or alias****NOTE**: This US Core SearchParameter definition extends the usage context of the[Conformance expectation extension](http://hl7.org/fhir/R4/extension-capabilitystatement-expectation.html)* multipleAnd
* multipleOr
* comparator
* modifier
* chain
 |
| [USCorePatientBirthdate](SearchParameter-us-core-patient-birthdate.md) | **The patient's date of birth**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCorePatientDeathDate](SearchParameter-us-core-patient-death-date.md) | **The date of death has been provided and satisfies this search value**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCorePatientFamily](SearchParameter-us-core-patient-family.md) | **A portion of the family name of the patient**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCorePatientGiven](SearchParameter-us-core-patient-given.md) | **A portion of the given name of the patient**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCorePatientId](SearchParameter-us-core-patient-id.md) | **Logical id of this artifact**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCorePatientIdentifier](SearchParameter-us-core-patient-identifier.md) | **A patient identifier**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCorePatientName](SearchParameter-us-core-patient-name.md) | **A server defined search that may match any of the string fields in the HumanName, including family, give, prefix, suffix, suffix, and/or text**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCorePractitionerId](SearchParameter-us-core-practitioner-id.md) | **Logical id of this artifact**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCorePractitionerIdentifier](SearchParameter-us-core-practitioner-identifier.md) | **A practitioner's Identifier**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCorePractitionerName](SearchParameter-us-core-practitioner-name.md) | **A server defined search that may match any of the string fields in the HumanName, including family, give, prefix, suffix, suffix, and/or text**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCorePractitionerrolePractitioner](SearchParameter-us-core-practitionerrole-practitioner.md) | **Practitioner that is able to provide the defined services for the organization**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCorePractitionerroleSpecialty](SearchParameter-us-core-practitionerrole-specialty.md) | **The practitioner has this specialty at an organization**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreProcedureCode](SearchParameter-us-core-procedure-code.md) | **A code to identify a procedure**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreProcedureDate](SearchParameter-us-core-procedure-date.md) | **When the procedure was performed**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreProcedurePatient](SearchParameter-us-core-procedure-patient.md) | **Search by subject - a patient**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreProcedureStatus](SearchParameter-us-core-procedure-status.md) | **preparation | in-progress | not-done | on-hold | stopped | completed | entered-in-error | unknown**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreQuestionnaireresponseAuthored](SearchParameter-us-core-questionnaireresponse-authored.md) | **When the questionnaire response was last changed**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreQuestionnaireresponseId](SearchParameter-us-core-questionnaireresponse-id.md) | **Logical id of this artifact**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreQuestionnaireresponsePatient](SearchParameter-us-core-questionnaireresponse-patient.md) | **The patient that is the subject of the questionnaire response**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreQuestionnaireresponseQuestionnaire](SearchParameter-us-core-questionnaireresponse-questionnaire.md) | **The questionnaire the answers are provided for**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreQuestionnaireresponseStatus](SearchParameter-us-core-questionnaireresponse-status.md) | **The status of the questionnaire response**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreRace](SearchParameter-us-core-race.md) | Returns patients with a race extension matching the specified code. |
| [USCoreRelatedpersonId](SearchParameter-us-core-relatedperson-id.md) | **Logical id of this artifact**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreRelatedpersonName](SearchParameter-us-core-relatedperson-name.md) | **A server defined search that may match any of the string fields in the HumanName, including family, give, prefix, suffix, suffix, and/or text**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreRelatedpersonPatient](SearchParameter-us-core-relatedperson-patient.md) | **The patient this related person is related to**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreServicerequestAuthored](SearchParameter-us-core-servicerequest-authored.md) | **Date request signed**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreServicerequestCategory](SearchParameter-us-core-servicerequest-category.md) | **Classification of service**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreServicerequestCode](SearchParameter-us-core-servicerequest-code.md) | **What is being requested/ordered**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreServicerequestId](SearchParameter-us-core-servicerequest-id.md) | **Logical id of this artifact**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreServicerequestPatient](SearchParameter-us-core-servicerequest-patient.md) | **Search by subject - a patient**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreServicerequestStatus](SearchParameter-us-core-servicerequest-status.md) | **draft | active | on-hold | revoked | completed | entered-in-error | unknown**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreSpecimenId](SearchParameter-us-core-specimen-id.md) | **Logical id of this artifact**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. |
| [USCoreSpecimenPatient](SearchParameter-us-core-specimen-patient.md) | **The patient the specimen comes from**NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements:* `multipleAnd`
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
| [US Core CarePlan Profile](StructureDefinition-us-core-careplan.md) | The US Core CarePlan Profile inherits from the FHIR[CarePlan](https://hl7.org/fhir/R4/careplan.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the CarePlan resource to record, search, and fetch assessment and plan of treatment data associated with a patient. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core CareTeam Profile](StructureDefinition-us-core-careteam.md) | The US Core CareTeam Profile inherits from the FHIR[CareTeam](https://hl7.org/fhir/R4/careteam.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the CareTeam resource for identifying the Care Team members associated with a patient to promote interoperability and adoption through common implementation. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |
| [US Core Pediatric Weight for Height Observation Profile](StructureDefinition-pediatric-weight-for-height.md) | US Core Pediatric Weight for Height Observation Profile inherits from the US Core Vital Signs Profile. This profile sets minimum expectations for the Observation resource to record, search, and fetch pediatric weight-for-length per age and sex observations in FHIR with a standard LOINC code and UCUM units of measure. It specifies which**additional**core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. |

