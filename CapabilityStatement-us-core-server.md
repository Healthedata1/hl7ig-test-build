# US Core Server CapabilityStatement - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Server CapabilityStatement**

## CapabilityStatement: US Core Server CapabilityStatement 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/CapabilityStatement/us-core-server | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 2 | *Computable Name*:UsCoreServerCapabilityStatement |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
This Section describes the expected capabilities of the US Core Server actor which is responsible for providing responses to the queries submitted by the US Core Requestors. The complete list of FHIR profiles, RESTful operations, and search parameters supported by US Core Servers are defined. Systems implementing this capability statement should meet the ASTP 2015 Common Clinical Data Set (CCDS) access requirement for Patient Selection 170.315(g)(7) and Application Access - Data Category Request 170.315(g)(8) and the ASTP[U.S. Core Data for Interoperability (USCDI) Version 6 July 2025](https://www.healthit.gov/isp/sites/isp/files/2025-07/USCDI-Version-6-July-2025.pdf). 

 [Raw OpenAPI-Swagger Definition file](us-core-server.openapi.json) | [Download](us-core-server.openapi.json) 

### SHOULD Support the Following Implementation Guides:

* [SMART App Launch version 2.0.0 and later](https://hl7.org/fhir/smart-app-launch/index.html)

### FHIR RESTful Capabilities

The US Core Server **SHALL**:

1. Support the US Core Patient resource profile AND at least one additional resource profile from the list of US Core Profiles AND and all**Must Support**US Core Profiles and resources it references.
* A summary table listing all the **Must Support** references to other US Core Profiles and FHIR resources for each US Core Profile is located in the [Must Support - Resource References](must-support.md#must-support---resource-references) section of the guide.

1. Follow the requirements documented in the[General Requirements](general-requirements.md)and[Must Support](must-support.md)pages
1. Return the following response classes:
* (Status 400): invalid parameter
* (Status 401/4xx): unauthorized request
* (Status 403): insufficient scopes
* (Status 404): unknown resource

1. Support JSON source formats for all US Core interactions.

The US Core Server **SHOULD**:

1. Follow the guidance documented in the[General Guidance](general-guidance.md)page
1. Support XML source formats for all US Core interactions.
1. Identify the US Core profiles supported as part of the FHIR`meta.profile`attribute for each instance.

**NOTE**: US Core SearchParameters referenced in this CapabilityStatement that are derived from standard FHIR SearchParameters are only defined to document Server and Client expectations. They specify additional expectations for the following SearchParameter elements:

* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`

They **SHALL NOT** be interpreted as search parameters for search. Servers and Clients **SHOULD** use the standard FHIR SearchParameters.

**Security:**

1. See the[General Security Considerations](security.md)section for requirements and recommendations.
1. A server**SHALL**reject any unauthorized requests by returning an`HTTP 401`"Unauthorized",`HTTP 403`"Forbidden", or`HTTP 404`"Not Found"

**Summary of System Wide Interactions**

* **MAY** support the `transaction` interaction.
* **MAY** support the `batch` interaction.
* **MAY** support the `search-system` interaction.
* **MAY** support the `history-system` interaction.

### RESTful Capabilities by Resource/Profile:

#### Summary

| | | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- |
| [AllergyIntolerance](#allergyintolerance) | [US Core AllergyIntolerance Profile](StructureDefinition-us-core-allergyintolerance.md) | clinical-status, patient patient+clinical-status | - | Provenance:target | - |
| [CarePlan](#careplan) | [US Core CarePlan Profile](StructureDefinition-us-core-careplan.md) | category, date, patient, status patient+category, patient+category+status, patient+category+date, patient+category+status+date | - | Provenance:target | - |
| [CareTeam](#careteam) | [US Core CareTeam Profile](StructureDefinition-us-core-careteam.md) | patient, role, status patient+role, patient+status | CareTeam:participant:PractitionerRole, CareTeam:participant:Practitioner, CareTeam:participant:Patient, CareTeam:participant:RelatedPerson | Provenance:target | - |
| [Condition](#condition) | [US Core Condition Encounter Diagnosis Profile](StructureDefinition-us-core-condition-encounter-diagnosis.md),[US Core Condition Problems and Health Concerns Profile](StructureDefinition-us-core-condition-problems-health-concerns.md) | abatement-date, asserted-date, category, clinical-status, code, encounter, onset-date, patient, recorded-date, _lastUpdated patient+category, patient+_lastUpdated, patient+category+encounter, patient+category+clinical-status, patient+recorded-date, patient+clinical-status, patient+code, patient+asserted-date, patient+abatement-date, patient+onset-date | - | Provenance:target | - |
| [Coverage](#coverage) | [US Core Coverage Profile](StructureDefinition-us-core-coverage.md) | patient | - | Provenance:target | - |
| [Device](#device) | [US Core Device Profile](StructureDefinition-us-core-device.md) | patient, status, type patient+type, patient+status | - | Provenance:target | - |
| [DiagnosticReport](#diagnosticreport) | [US Core DiagnosticReport Profile for Report and Note exchange](StructureDefinition-us-core-diagnosticreport-note.md),[US Core DiagnosticReport Profile for Laboratory Results Reporting](StructureDefinition-us-core-diagnosticreport-lab.md) | category, code, date, _lastUpdated, patient, status patient+category, patient+status, patient+category+date, patient+code, patient+category+_lastUpdated, patient+code+date | - | Provenance:target | - |
| [DocumentReference](#documentreference) | [US Core DocumentReference Profile](StructureDefinition-us-core-documentreference.md),[US Core ADI DocumentReference Profile](StructureDefinition-us-core-adi-documentreference.md) | _id, category, date, patient, period, status, type patient+category, patient+status, patient+type, patient+category+date, patient+type+period | - | Provenance:target | docref |
| [Encounter](#encounter) | [US Core Encounter Profile](StructureDefinition-us-core-encounter.md) | _id, class, date, _lastUpdated, discharge-disposition, identifier, location, patient, status, type patient+location, patient+status, patient+_lastUpdated, patient+type, date+patient, class+patient, patient+discharge-disposition | - | Provenance:target | - |
| [Endpoint](#endpoint) | - | - | - | - | - |
| [FamilyMemberHistory](#familymemberhistory) | [US Core FamilyMemberHistory Profile](StructureDefinition-us-core-familymemberhistory.md) | patient, code patient+code | - | Provenance:target | - |
| [Goal](#goal) | [US Core Goal Profile](StructureDefinition-us-core-goal.md) | description, lifecycle-status, patient, target-date patient+lifecycle-status, patient+target-date, patient+description | - | Provenance:target | - |
| [HealthcareService](#healthcareservice) | - | - | - | - | - |
| [Immunization](#immunization) | [US Core Immunization Profile](StructureDefinition-us-core-immunization.md) | date, patient, status patient+date, patient+status | - | Provenance:target | - |
| [Location](#location) | [US Core Location Profile](StructureDefinition-us-core-location.md) | address, address-city, address-postalcode, address-state, name | - | - | - |
| [Media](#media) | - | - | - | - | - |
| [Medication](#medication) | [US Core Medication Profile](StructureDefinition-us-core-medication.md) | - | - | - | - |
| [MedicationDispense](#medicationdispense) | [US Core MedicationDispense Profile](StructureDefinition-us-core-medicationdispense.md) | patient, status, type patient+status, patient+status+type | MedicationDispense:medication | Provenance:target | - |
| [MedicationRequest](#medicationrequest) | [US Core MedicationRequest Profile](StructureDefinition-us-core-medicationrequest.md) | authoredon, encounter, intent, patient, status patient+intent+authoredon, patient+intent+status, patient+intent, patient+intent+encounter | MedicationRequest:medication | Provenance:target | - |
| [Observation](#observation) | [US Core Observation ADI Documentation Profile](StructureDefinition-us-core-observation-adi-documentation.md),[US Core Laboratory Result Observation Profile](StructureDefinition-us-core-observation-lab.md),[US Core Observation Pregnancy Status Profile](StructureDefinition-us-core-observation-pregnancystatus.md),[US Core Observation Pregnancy Intent Profile](StructureDefinition-us-core-observation-pregnancyintent.md),[US Core Observation Occupation Profile](StructureDefinition-us-core-observation-occupation.md),[US Core Respiratory Rate Profile](StructureDefinition-us-core-respiratory-rate.md),[US Core Simple Observation Profile](StructureDefinition-us-core-simple-observation.md),[US Core Treatment Intervention Preference Profile](StructureDefinition-us-core-treatment-intervention-preference.md),[US Core Care Experience Preference Profile](StructureDefinition-us-core-care-experience-preference.md),[US Core Heart Rate Profile](StructureDefinition-us-core-heart-rate.md),[US Core Body Temperature Profile](StructureDefinition-us-core-body-temperature.md),[US Core Pediatric Weight for Height Observation Profile](StructureDefinition-pediatric-weight-for-height.md),[US Core Pulse Oximetry Profile](StructureDefinition-us-core-pulse-oximetry.md),[US Core Smoking Status Observation Profile](StructureDefinition-us-core-smokingstatus.md),[US Core Observation Sexual Orientation Profile](StructureDefinition-us-core-observation-sexual-orientation.md),[US Core Head Circumference Profile](StructureDefinition-us-core-head-circumference.md),[US Core Body Height Profile](StructureDefinition-us-core-body-height.md),[US Core BMI Profile](StructureDefinition-us-core-bmi.md),[US Core Observation Screening Assessment Profile](StructureDefinition-us-core-observation-screening-assessment.md),[US Core Average Blood Pressure Profile](StructureDefinition-us-core-average-blood-pressure.md),[US Core Blood Pressure Profile](StructureDefinition-us-core-blood-pressure.md),[US Core Observation Clinical Result Profile](StructureDefinition-us-core-observation-clinical-result.md),[US Core Pediatric BMI for Age Observation Profile](StructureDefinition-pediatric-bmi-for-age.md),[US Core Pediatric Head Occipital Frontal Circumference Percentile Profile](StructureDefinition-head-occipital-frontal-circumference-percentile.md),[US Core Body Weight Profile](StructureDefinition-us-core-body-weight.md),[US Core Vital Signs Profile](StructureDefinition-us-core-vital-signs.md) | category, code, date, _lastUpdated, patient, status patient+category, patient+category+date, patient+code, patient+category+status, patient+category+_lastUpdated, patient+code+date | - | Provenance:target | - |
| [Organization](#organization) | [US Core Organization Profile](StructureDefinition-us-core-organization.md) | address, name | - | - | - |
| [Patient](#patient) | [US Core Patient Profile](StructureDefinition-us-core-patient.md) | _id, birthdate, death-date, family, given, identifier, name birthdate+name, birthdate+family, death-date+family | - | Provenance:target | - |
| [Practitioner](#practitioner) | [US Core Practitioner Profile](StructureDefinition-us-core-practitioner.md) | _id, identifier, name | - | - | - |
| [PractitionerRole](#practitionerrole) | [US Core PractitionerRole Profile](StructureDefinition-us-core-practitionerrole.md) | practitioner, specialty | PractitionerRole:endpoint, PractitionerRole:practitioner | - | - |
| [Procedure](#procedure) | [US Core Procedure Profile](StructureDefinition-us-core-procedure.md) | code, date, patient, status patient+status, patient+date, patient+code+date | - | Provenance:target | - |
| [Provenance](#provenance) | [US Core Provenance Profile](StructureDefinition-us-core-provenance.md) | - | - | - | - |
| [Questionnaire](#questionnaire) | [SDC Base Questionnaire Profile](http://hl7.org/fhir/uv/sdc/StructureDefinition/sdc-questionnaire) | - | - | - | - |
| [QuestionnaireResponse](#questionnaireresponse) | [US Core QuestionnaireResponse Profile](StructureDefinition-us-core-questionnaireresponse.md) | _id, authored, patient, questionnaire, status patient+authored, patient+status, patient+questionnaire | - | Provenance:target | - |
| [RelatedPerson](#relatedperson) | [US Core RelatedPerson Profile](StructureDefinition-us-core-relatedperson.md) | _id, name, patient patient+name | - | Provenance:target | - |
| [ServiceRequest](#servicerequest) | [US Core PMO ServiceRequest Profile](StructureDefinition-us-core-pmo-servicerequest.md),[US Core ServiceRequest Profile](StructureDefinition-us-core-servicerequest.md) | _id, authored, category, code, patient, status patient+category, patient+status, patient+code, patient+category+authored, patient+code+authored | - | Provenance:target | - |
| [Specimen](#specimen) | [US Core Specimen Profile](StructureDefinition-us-core-specimen.md) | _id, patient | - | - | - |
| [ValueSet](#valueset) | - | - | - | - | expand |

#### AllergyIntolerance

Conformance Expectation: **SHALL**

Supported Profiles:

* **SHALL** support: [US Core AllergyIntolerance Profile](StructureDefinition-us-core-allergyintolerance.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a AllergyIntolerance resource using: `GET [base]/AllergyIntolerance/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/AllergyIntolerance?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-allergyintolerance-patient.md) | reference |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHOULD** | [patient](SearchParameter-us-core-allergyintolerance-patient.md)+[clinical-status](SearchParameter-us-core-allergyintolerance-clinical-status.md) | reference+token |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.

-------

#### CarePlan

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* Additional considerations for systems aligning with [HL7 Consolidated (C-CDA)](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=492) Care Plan requirements: 
* US Core Goal **SHOULD** be present in CarePlan.goal
* US Core Condition **SHOULD** be present in CarePlan.addresses
* Assessment and Plan **MAY** be included as narrative text
 

Supported Profiles:

* **SHALL** support: [US Core CarePlan Profile](StructureDefinition-us-core-careplan.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a CarePlan resource using: `GET [base]/CarePlan/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/CarePlan?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-careplan-patient.md)+[category](SearchParameter-us-core-careplan-category.md) | reference+token |
| **SHOULD** | [patient](SearchParameter-us-core-careplan-patient.md)+[category](SearchParameter-us-core-careplan-category.md)+[status](SearchParameter-us-core-careplan-status.md) | reference+token+token |
| **SHOULD** | [patient](SearchParameter-us-core-careplan-patient.md)+[category](SearchParameter-us-core-careplan-category.md)+[date](SearchParameter-us-core-careplan-date.md) | reference+token+date |
| **SHOULD** | [patient](SearchParameter-us-core-careplan-patient.md)+[category](SearchParameter-us-core-careplan-category.md)+[status](SearchParameter-us-core-careplan-status.md)+[date](SearchParameter-us-core-careplan-date.md) | reference+token+token+date |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### CareTeam

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* In order to access care team member's names, identifiers, locations, and contact information, the CareTeam profile supports several types of care team participants. They are represented as references to other profiles and include the following four profiles which are marked as must support: 
1. US Core Practitioner Profile
1. US Core PractitionerRole Profile
1. US Core Patient Profile
1. US Core RelatedPerson Profile
 
* Although **both** US Core Practitioner Profile and US Core PractitionerRole are must support, the server system is not required to support both types of references, but **SHALL** support **at least** one of them.
* The client application **SHALL** support all four profile references.
* Bacause the **US Core PractitionerRole Profile** supplies the provider's location and contact information and a reference to the Practitioner, server systems **SHOULD** reference it instead of the **US Core Practitioner Profile**.
* Servers that support only US Core Practitioner Profile and do not support the US Core PractitionerRole Profile **SHALL** provide implementation specific guidance how to access a provider’s location and contact information using only the Practitioner resource.

Supported Profiles:

* **SHALL** support: [US Core CareTeam Profile](StructureDefinition-us-core-careteam.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a CareTeam resource using: `GET [base]/CareTeam/[id]` 
*  A Server **SHOULD** be capable of supporting the following _includes: 
*  CareTeam:participant:PractitionerRole: `GET [base]/CareTeam?[parameter=value]&_include=CareTeam:participant:PractitionerRole` 
*  CareTeam:participant:Practitioner: `GET [base]/CareTeam?[parameter=value]&_include=CareTeam:participant:Practitioner` 
*  CareTeam:participant:Patient: `GET [base]/CareTeam?[parameter=value]&_include=CareTeam:participant:Patient` 
*  CareTeam:participant:RelatedPerson: `GET [base]/CareTeam?[parameter=value]&_include=CareTeam:participant:RelatedPerson` 
 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/CareTeam?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHOULD** | [role](SearchParameter-us-core-careteam-role.md) | token |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHOULD** | [patient](SearchParameter-us-core-careteam-patient.md)+[role](SearchParameter-us-core-careteam-role.md) | reference+token |
| **SHALL** | [patient](SearchParameter-us-core-careteam-patient.md)+[status](SearchParameter-us-core-careteam-status.md) | reference+token |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### Condition

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* For Encounter Diagnosis use the **US Core Condition Encounter Diagnosis Profile**. 
* When `Condition.category` is "encounter-diagnosis" the encounter, **SHOULD** be referenced in `Condition.encounter`.
 
* For Problems and Health Concerns use the **US Core Condition Problems and Health Concerns Profile**. 
* When `Condition.category` is a "problems-list-item", the `Condition.clinicalStatus **SHOULD** be present.
 
* See the US Core General Guidance page for [Searching Using lastUpdated](general-guidance.md#searching-using-lastupdated). Updates to `Condition.meta.lastUpdated` **SHOULD** reflect: 
* New problems and health concerns
* Changes in the clinical status or verifications status of problems or health concern
 

Supported Profiles:

* **SHALL** support: [US Core Condition Encounter Diagnosis Profile](StructureDefinition-us-core-condition-encounter-diagnosis.md) 
* **SHALL** support: [US Core Condition Problems and Health Concerns Profile](StructureDefinition-us-core-condition-problems-health-concerns.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a Condition resource using: `GET [base]/Condition/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/Condition?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-condition-patient.md) | reference |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-condition-patient.md)+[category](SearchParameter-us-core-condition-category.md) | reference+token |
| **SHOULD** | [patient](SearchParameter-us-core-condition-patient.md)+[_lastUpdated](SearchParameter-us-core-condition-lastupdated.md) | reference+date |
| **SHOULD** | [patient](SearchParameter-us-core-condition-patient.md)+[category](SearchParameter-us-core-condition-category.md)+[encounter](SearchParameter-us-core-condition-encounter.md) | reference+token+reference |
| **SHOULD** | [patient](SearchParameter-us-core-condition-patient.md)+[category](SearchParameter-us-core-condition-category.md)+[clinical-status](SearchParameter-us-core-condition-clinical-status.md) | reference+token+token |
| **SHOULD** | [patient](SearchParameter-us-core-condition-patient.md)+[recorded-date](SearchParameter-us-core-condition-recorded-date.md) | reference+date |
| **SHOULD** | [patient](SearchParameter-us-core-condition-patient.md)+[clinical-status](SearchParameter-us-core-condition-clinical-status.md) | reference+token |
| **SHOULD** | [patient](SearchParameter-us-core-condition-patient.md)+[code](SearchParameter-us-core-condition-code.md) | reference+token |
| **SHOULD** | [patient](SearchParameter-us-core-condition-patient.md)+[asserted-date](SearchParameter-us-core-condition-asserted-date.md) | reference+date |
| **SHOULD** | [patient](SearchParameter-us-core-condition-patient.md)+[abatement-date](SearchParameter-us-core-condition-abatement-date.md) | reference+date |
| **SHOULD** | [patient](SearchParameter-us-core-condition-patient.md)+[onset-date](SearchParameter-us-core-condition-onset-date.md) | reference+date |

Search Parameter Requirements (When Used Alone or in Combination):

* A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* A server **SHALL** document the types of changes that can be detected using this parameter.


  A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.

-------

#### Coverage

Conformance Expectation: **SHALL**

Supported Profiles:

* **SHALL** support: [US Core Coverage Profile](StructureDefinition-us-core-coverage.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a Coverage resource using: `GET [base]/Coverage/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/Coverage?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-coverage-patient.md) | reference |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.

-------

#### Device

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* Medical devices with UDI information **SHALL** represent the UDI code in `Device.udiCarrier.carrierHRF`. All five UDI-PI elements defined in the UDI code may not always be present in every UDI instance. However, those UDI-PI elements present **SHALL** be represented in the corresponding *US Core Device Profile elements.


  UDI may not be present in all scenarios, such as historical medical devices, patient-reported implant information, payer-reported devices, or improperly documented implants. If UDI is not present and the manufacturer or model number information is available, they **SHOULD** be included to support historical reports of medical devices as follows:


  |data element|*US Core Device Profile element| |---|---| |manufacturer|`Device.manufacturer`| |model|`Device.model`| {:.grid}

Supported Profiles:

* **SHALL** support: [US Core Device Profile](StructureDefinition-us-core-device.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a Device resource using: `GET [base]/Device/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/Device?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-device-patient.md) | reference |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHOULD** | [patient](SearchParameter-us-core-device-patient.md)+[type](SearchParameter-us-core-device-type.md) | reference+token |
| **SHOULD** | [patient](SearchParameter-us-core-device-patient.md)+[status](SearchParameter-us-core-device-status.md) | reference+token |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### DiagnosticReport

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* For laboratory result reports use the **US Core DiagnosticReport Profile for Laboratory Results Reporting Profile**. 
* Updates to `.meta.lastUpdated` **SHOULD** reflect: 
* New laboratory reports
* Changes in the status of laboratory reports including events that trigger the same status (e.g., amended → amended).
 
 
* For imaging and non-laboratory clinical test result reports use the **US Core DiagnosticReport Profile for Report and Note Exchange Profile**. 
* Diagnostic imaging results in visual images requiring interpretation and clinical test results/reports may also reference images as part of the report. There is no single approach for accessing imaging studies alongside clinical data using a single authorization flow to give patients and providers access to the images. 
* The `DiagnosticReport.media.link` element **SHOULD** be used to support links to various patient-friendly content, such as jpg images of x-rays (see the DiagnosticReport Chest X-ray Report Example).
* The `DiagnosticReport.imagingStudy` element **SHOULD** be used to support exchange with systems that can view DICOM (Digital Imaging and Communications in Medicine) studies, series, and SOP (Service-Object Pair) instances referenced in the [ImagingStudy] resource.
* Alternatively, systems can use business identifiers such as accession numbers in the `identifier` element to access the source images from external sources.
 
 
* The `DiagnosticRequest.basedOn` element connects the DiagnosticReport to the originating order in the EHR. Systems that initiate the lab order **SHOULD** use this element when reporting the results.

Supported Profiles:

* **SHALL** support: [US Core DiagnosticReport Profile for Report and Note exchange](StructureDefinition-us-core-diagnosticreport-note.md) 
* **SHALL** support: [US Core DiagnosticReport Profile for Laboratory Results Reporting](StructureDefinition-us-core-diagnosticreport-lab.md) 

Profile Interaction Summary:

* **SHALL** support `create`†, `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `update`, `patch`, `delete`, `history-type`.

> create†This conformance expectation applies**only**to the**US Core DiagnosticReport Profile for Report and Note exchange**profile. The conformance expectation for the**US Core DiagnosticReport Profile for Laboratory Results Reporting**is**MAY**.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a DiagnosticReport resource using: `GET [base]/DiagnosticReport/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/DiagnosticReport?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-diagnosticreport-patient.md) | reference |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-diagnosticreport-patient.md)+[category](SearchParameter-us-core-diagnosticreport-category.md) | reference+token |
| **SHOULD** | [patient](SearchParameter-us-core-diagnosticreport-patient.md)+[status](SearchParameter-us-core-diagnosticreport-status.md) | reference+token |
| **SHALL** | [patient](SearchParameter-us-core-diagnosticreport-patient.md)+[category](SearchParameter-us-core-diagnosticreport-category.md)+[date](SearchParameter-us-core-diagnosticreport-date.md) | reference+token+date |
| **SHALL** | [patient](SearchParameter-us-core-diagnosticreport-patient.md)+[code](SearchParameter-us-core-diagnosticreport-code.md) | reference+token |
| **SHOULD** | [patient](SearchParameter-us-core-diagnosticreport-patient.md)+[category](SearchParameter-us-core-diagnosticreport-category.md)+[_lastUpdated](SearchParameter-us-core-diagnosticreport-lastupdated.md) | reference+token+date |
| **SHOULD** | [patient](SearchParameter-us-core-diagnosticreport-patient.md)+[code](SearchParameter-us-core-diagnosticreport-code.md)+[date](SearchParameter-us-core-diagnosticreport-date.md) | reference+token+date |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* A server **SHALL** document the types of changes that can be detected using this parameter.


  A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### DocumentReference

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* For Advance Directive Information (ADI) documents use the **US Core ADI DocumentReference Profile**.
* For other clinical documents use the **US Core DiagnosticReport Profile for Report and Note Exchange**. 
* See the [Clinical Notes](clinical-notes.md) page for important definitions, requirements, and guidance on creating, using, and sharing Clinical Notes.
* The `DocumentReference.type` binding Must Support at a minimum the [10 Common Clinical Notes](ValueSet-us-core-clinical-note-type.md) and may extend to the full US Core DocumentReference Type Value Set
 
* The DocumentReference resources can represent the referenced content using either an address where the document can be retrieved using `DocumentReference.attachment.url` or the content as inline base64 encoded data using `DocumentReference.attachment.data`. 
* Although both are marked as must support, the server system is not required to support an address, and inline base64 encoded data, but **SHALL** support at least one of these elements.
* The client application **SHALL** support both elements.
* The `content.attachment.url` may refer to a FHIR Binary Resource (i.e. [base]/Binary/[id]), FHIR Document Bundle (i.e [base]/Bundle/[id] or another endpoint.
* If there are multiple `DocumentReference.content` element repetitions, these **SHALL** all represent the same document in different format or attachment metadata. The content element **SHALL NOT** contain different versions of the same content. For version handling use multiple DocumentReferences with `DocumentReference.relatesTo`
 
* Every DocumentReference must have a responsible Organization. The organization responsible for the DocumentReference **SHALL** be present either in `DocumentReference.custodian` or accessible in the Provenance resource targeting the DocumentReference using `Provenance.agent.who` or `Provenance.agent.onBehalfOf`.

Supported Profiles:

* **SHALL** support: [US Core DocumentReference Profile](StructureDefinition-us-core-documentreference.md) 
* **SHALL** support: [US Core ADI DocumentReference Profile](StructureDefinition-us-core-adi-documentreference.md) 

Profile Interaction Summary:

* **SHALL** support `create`, `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `update`, `patch`, `delete`, `history-type`.

Operation Summary:

* A server **SHALL** be capable of responding to a $docref operation and capable of returning at least a reference to a generated CCD document, if available. **MAY** provide references to other 'on-demand' and 'stable' documents (or 'delayed/deferred assembly') that meet the query parameters as well. If a context date range is supplied the server ** SHOULD** provide references to any document that falls within the date range. If no date range is supplied, then the server **SHALL** provide references to last or current document(s). **SHOULD** document what resources, if any, are returned as included resources


  `GET [base]/DocumentReference/$docref?patient=[id]`

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a DocumentReference resource using: `GET [base]/DocumentReference/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/DocumentReference?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [_id](SearchParameter-us-core-documentreference-id.md) | token |
| **SHALL** | [patient](SearchParameter-us-core-documentreference-patient.md) | reference |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-documentreference-patient.md)+[category](SearchParameter-us-core-documentreference-category.md) | reference+token |
| **SHOULD** | [patient](SearchParameter-us-core-documentreference-patient.md)+[status](SearchParameter-us-core-documentreference-status.md) | reference+token |
| **SHALL** | [patient](SearchParameter-us-core-documentreference-patient.md)+[type](SearchParameter-us-core-documentreference-type.md) | reference+token |
| **SHALL** | [patient](SearchParameter-us-core-documentreference-patient.md)+[category](SearchParameter-us-core-documentreference-category.md)+[date](SearchParameter-us-core-documentreference-date.md) | reference+token+date |
| **SHOULD** | [patient](SearchParameter-us-core-documentreference-patient.md)+[type](SearchParameter-us-core-documentreference-type.md)+[period](SearchParameter-us-core-documentreference-period.md) | reference+token+date |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### Encounter

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* The Encounter resource can represent a reason using either a code with `Encounter.reasonCode`, or a reference with `Encounter.reasonReference` to Condition or other resource.
* The location address can be represented by either by the Location referenced by `Encounter.location.location` or indirectly through the Organization referenced by `Encounter.serviceProvider`.
* If the event facility/location differs from the `Encounter.location`, systems **SHOULD** reference it directly:
* Servers can use the US Core Interpreter Needed Extension on this profile or the [US Core Patient Profile] to communicate whether a patient needs an interpreter. Although the extension is marked as an **Additional USCDI Requirements** on both US Core Patient and US Core Encounter Profiles, the certifying Server system is not required to support the extension on both profiles, but **SHALL** support the extension on at least one. The certifying Client application **SHALL** support the extension on both profiles.
* Updates to `.meta.lastUpdated` **SHOULD** reflect:

Supported Profiles:

* **SHALL** support: [US Core Encounter Profile](StructureDefinition-us-core-encounter.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a Encounter resource using: `GET [base]/Encounter/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/Encounter?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [_id](SearchParameter-us-core-encounter-id.md) | token |
| **SHOULD** | [identifier](SearchParameter-us-core-encounter-identifier.md) | token |
| **SHALL** | [patient](SearchParameter-us-core-encounter-patient.md) | reference |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHOULD** | [patient](SearchParameter-us-core-encounter-patient.md)+[location](SearchParameter-us-core-encounter-location.md) | reference+reference |
| **SHOULD** | [patient](SearchParameter-us-core-encounter-patient.md)+[status](SearchParameter-us-core-encounter-status.md) | reference+token |
| **SHOULD** | [patient](SearchParameter-us-core-encounter-patient.md)+[_lastUpdated](SearchParameter-us-core-encounter-lastupdated.md) | reference+date |
| **SHOULD** | [patient](SearchParameter-us-core-encounter-patient.md)+[type](SearchParameter-us-core-encounter-type.md) | reference+token |
| **SHALL** | [date](SearchParameter-us-core-encounter-date.md)+[patient](SearchParameter-us-core-encounter-patient.md) | date+reference |
| **SHOULD** | [class](SearchParameter-us-core-encounter-class.md)+[patient](SearchParameter-us-core-encounter-patient.md) | token+reference |
| **SHOULD** | [patient](SearchParameter-us-core-encounter-patient.md)+[discharge-disposition](SearchParameter-us-core-encounter-discharge-disposition.md) | reference+token |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* A server **SHALL** document the types of changes that can be detected using this parameter.


  A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### Endpoint

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> The Media Resource is a Must Support referenced resource when using the US Core PractitionerRole Profile.

Profile Interaction Summary:

* **SHOULD** support `read`, `vread`.
* **MAY** support `create`, `search-type`, `update`, `patch`, `delete`, `history-instance`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHOULD** be capable of returning a Endpoint resource using: `GET [base]/Endpoint/[id]` 

-------

#### FamilyMemberHistory

Conformance Expectation: **SHALL**

Supported Profiles:

* **SHALL** support: [US Core FamilyMemberHistory Profile](StructureDefinition-us-core-familymemberhistory.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a FamilyMemberHistory resource using: `GET [base]/FamilyMemberHistory/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/FamilyMemberHistory?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-familymemberhistory-patient.md) | reference |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHOULD** | [patient](SearchParameter-us-core-familymemberhistory-patient.md)+[code](SearchParameter-us-core-familymemberhistory-code.md) | reference+token |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### Goal

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* Although both `Goal.startDate` and `Goal.target.dueDate` are marked as must support, the server system is not required to support both, but **SHALL** support at least one of these elements. The client application **SHALL** support both elements.

Supported Profiles:

* **SHALL** support: [US Core Goal Profile](StructureDefinition-us-core-goal.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a Goal resource using: `GET [base]/Goal/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/Goal?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-goal-patient.md) | reference |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHOULD** | [patient](SearchParameter-us-core-goal-patient.md)+[lifecycle-status](SearchParameter-us-core-goal-lifecycle-status.md) | reference+token |
| **SHOULD** | [patient](SearchParameter-us-core-goal-patient.md)+[target-date](SearchParameter-us-core-goal-target-date.md) | reference+date |
| **SHOULD** | [patient](SearchParameter-us-core-goal-patient.md)+[description](SearchParameter-us-core-goal-description.md) | reference+token |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* A client **SHALL** provide a value precise to the **day**.


  A server **SHALL** support a value a value precise to the **day**.

-------

#### HealthcareService

Conformance Expectation: **MAY**

Resource Specific Documentation:

> The HealthcareService Resource is a referenced resource when using the US Core PractitionerRole Profile and subject to constraint us-core-13: "SHALL have a practitioner, an organization, a healthcare service, or a location."

Profile Interaction Summary:

* **SHOULD** support `read`, `vread`.
* **MAY** support `create`, `search-type`, `update`, `patch`, `delete`, `history-instance`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHOULD** be capable of returning a HealthcareService resource using: `GET [base]/HealthcareService/[id]` 

-------

#### Immunization

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* Based upon the ASTP U.S. Core Data for Interoperability (USCDI) requirements, CVX vaccine codes are required and the NDC vaccine codes **SHOULD** be supported as an additional code.

Supported Profiles:

* **SHALL** support: [US Core Immunization Profile](StructureDefinition-us-core-immunization.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a Immunization resource using: `GET [base]/Immunization/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/Immunization?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-immunization-patient.md) | reference |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHOULD** | [patient](SearchParameter-us-core-immunization-patient.md)+[date](SearchParameter-us-core-immunization-date.md) | reference+date |
| **SHOULD** | [patient](SearchParameter-us-core-immunization-patient.md)+[status](SearchParameter-us-core-immunization-status.md) | reference+token |

Search Parameter Requirements (When Used Alone or in Combination):

* A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### Location

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* Systems **SHOULD** enable the user who enters the address to follow the Project US@ Technical Specification for Patient Addresses Final Version 1.0 as the standard style guide for `Location.address.line` and `Location.address.city`.

Supported Profiles:

* **SHALL** support: [US Core Location Profile](StructureDefinition-us-core-location.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a Location resource using: `GET [base]/Location/[id]` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [address](SearchParameter-us-core-location-address.md) | string |
| **SHOULD** | [address-city](SearchParameter-us-core-location-address-city.md) | string |
| **SHOULD** | [address-postalcode](SearchParameter-us-core-location-address-postalcode.md) | string |
| **SHOULD** | [address-state](SearchParameter-us-core-location-address-state.md) | string |
| **SHALL** | [name](SearchParameter-us-core-location-name.md) | string |

-------

#### Media

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> The Media Resource is a Must Support referenced resource when using the US Core DiagnosticReport Profile for Report and Note Exchange.

Profile Interaction Summary:

* **SHOULD** support `read`, `vread`.
* **MAY** support `create`, `search-type`, `update`, `patch`, `delete`, `history-instance`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHOULD** be capable of returning a Media resource using: `GET [base]/Media/[id]` 

-------

#### Medication

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* The MedicationRequest resource can represent a medication, using an external reference to a Medication resource. If an external Medication Resource is used in a MedicationRequest, then the READ **SHALL** be supported.

Supported Profiles:

* **SHALL** support: [US Core Medication Profile](StructureDefinition-us-core-medication.md) 

Profile Interaction Summary:

* **SHALL** support `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `search-type`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a Medication resource using: `GET [base]/Medication/[id]` 

-------

#### MedicationDispense

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* This Profile can represent a medication using a code or reference a Medication resource. 
* The Server systems are not required to support both a code and a reference, but **SHALL** support at least one of these methods.
* The Client application **SHALL** support all methods.
* Systems that primarily rely on NDC codes instead of RxNorm to represent medications can use the National Library of Medicine's (NLM) NDC to RxNorm mappings to aid in additional codings.
* When referencing a Medication resource in `.medicationReference`, the resource may be contained or an external resource. If an external reference to a Medication resource is used, the Server **SHALL** support the `_include` parameter for searching this element.
 

Supported Profiles:

* **SHALL** support: [US Core MedicationDispense Profile](StructureDefinition-us-core-medicationdispense.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a MedicationDispense resource using: `GET [base]/MedicationDispense/[id]` 
*  A Server **SHOULD** be capable of supporting the following _includes: 
*  MedicationDispense:medication: `GET [base]/MedicationDispense?[parameter=value]&_include=MedicationDispense:medication` 
 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/MedicationDispense?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-medicationdispense-patient.md) | reference |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHOULD** | [patient](SearchParameter-us-core-medicationdispense-patient.md)+[status](SearchParameter-us-core-medicationdispense-status.md) | reference+token |
| **SHOULD** | [patient](SearchParameter-us-core-medicationdispense-patient.md)+[status](SearchParameter-us-core-medicationdispense-status.md)+[type](SearchParameter-us-core-medicationdispense-type.md) | reference+token+token |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### MedicationRequest

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* This Profile can represent a medication using a code or reference a Medication resource.
* The MedicationRequest resource can represent that information is from a secondary source using either a boolean flag or reference in `MedicationRequest.reportedBoolean`, or a reference using `MedicationRequest.reportedReference` to Practitioner or other resource.
* When recording “self-prescribed” medication, requester **SHOULD** be used to indicate the Patient or RelatedPerson as the prescriber. (See the Medication List section for guidance on accessing a patient medications including over the counter (OTC) medication and other substances taken for medical and recreational use.)
* The MedicationRequest resource can communicate the reason or indication for treatment using either a code in MedicationRequest.reasonCode or a reference using MedicationRequest.reasonReference.

Supported Profiles:

* **SHALL** support: [US Core MedicationRequest Profile](StructureDefinition-us-core-medicationrequest.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a MedicationRequest resource using: `GET [base]/MedicationRequest/[id]` 
*  A Server **SHOULD** be capable of supporting the following _includes: 
*  MedicationRequest:medication: `GET [base]/MedicationRequest?[parameter=value]&_include=MedicationRequest:medication` 
 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/MedicationRequest?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHOULD** | [patient](SearchParameter-us-core-medicationrequest-patient.md)+[intent](SearchParameter-us-core-medicationrequest-intent.md)+[authoredon](SearchParameter-us-core-medicationrequest-authoredon.md) | reference+token+date |
| **SHALL** | [patient](SearchParameter-us-core-medicationrequest-patient.md)+[intent](SearchParameter-us-core-medicationrequest-intent.md)+[status](SearchParameter-us-core-medicationrequest-status.md) | reference+token+token |
| **SHALL** | [patient](SearchParameter-us-core-medicationrequest-patient.md)+[intent](SearchParameter-us-core-medicationrequest-intent.md) | reference+token |
| **SHOULD** | [patient](SearchParameter-us-core-medicationrequest-patient.md)+[intent](SearchParameter-us-core-medicationrequest-intent.md)+[encounter](SearchParameter-us-core-medicationrequest-encounter.md) | reference+token+reference |

Search Parameter Requirements (When Used Alone or in Combination):

* A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### Observation

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* Systems **SHOULD** support `Observation.effectivePeriod` to accurately represent tests that are collected over a period of time (for example, a 24-Hour Urine Collection test).
* An Observation without a value, **SHALL** include a reason why the data is absent unless there are component observations, or references to other Observations that are grouped within it 
* Systems that never provide an observation without a value are not required to support `Observation.dataAbsentReason`
 
* An `Observation.component` without a value, **SHALL** include a reason why the data is absent. 
* Systems that never provide an component observation without a component value are not required to support `Observation.component.dataAbsentReason`.
 
* There are multiple Observation profiles. Refer to the specific profile page for profile specific conformance rules and guidance

Supported Profiles:

* **SHALL** support: [US Core Observation ADI Documentation Profile](StructureDefinition-us-core-observation-adi-documentation.md) 
* **SHALL** support: [US Core Laboratory Result Observation Profile](StructureDefinition-us-core-observation-lab.md) 
* **SHALL** support: [US Core Observation Pregnancy Status Profile](StructureDefinition-us-core-observation-pregnancystatus.md) 
* **SHALL** support: [US Core Observation Pregnancy Intent Profile](StructureDefinition-us-core-observation-pregnancyintent.md) 
* **SHALL** support: [US Core Observation Occupation Profile](StructureDefinition-us-core-observation-occupation.md) 
* **SHALL** support: [US Core Respiratory Rate Profile](StructureDefinition-us-core-respiratory-rate.md) 
* **SHALL** support: [US Core Simple Observation Profile](StructureDefinition-us-core-simple-observation.md) 
* **SHALL** support: [US Core Treatment Intervention Preference Profile](StructureDefinition-us-core-treatment-intervention-preference.md) 
* **SHALL** support: [US Core Care Experience Preference Profile](StructureDefinition-us-core-care-experience-preference.md) 
* **SHALL** support: [US Core Heart Rate Profile](StructureDefinition-us-core-heart-rate.md) 
* **SHALL** support: [US Core Body Temperature Profile](StructureDefinition-us-core-body-temperature.md) 
* **SHALL** support: [US Core Pediatric Weight for Height Observation Profile](StructureDefinition-pediatric-weight-for-height.md) 
* **SHALL** support: [US Core Pulse Oximetry Profile](StructureDefinition-us-core-pulse-oximetry.md) 
* **SHALL** support: [US Core Smoking Status Observation Profile](StructureDefinition-us-core-smokingstatus.md) 
* **MAY** support: [US Core Observation Sexual Orientation Profile](StructureDefinition-us-core-observation-sexual-orientation.md) 
* **SHALL** support: [US Core Head Circumference Profile](StructureDefinition-us-core-head-circumference.md) 
* **SHALL** support: [US Core Body Height Profile](StructureDefinition-us-core-body-height.md) 
* **SHALL** support: [US Core BMI Profile](StructureDefinition-us-core-bmi.md) 
* **SHALL** support: [US Core Observation Screening Assessment Profile](StructureDefinition-us-core-observation-screening-assessment.md) 
* **SHALL** support: [US Core Average Blood Pressure Profile](StructureDefinition-us-core-average-blood-pressure.md) 
* **SHALL** support: [US Core Blood Pressure Profile](StructureDefinition-us-core-blood-pressure.md) 
* **SHALL** support: [US Core Observation Clinical Result Profile](StructureDefinition-us-core-observation-clinical-result.md) 
* **SHALL** support: [US Core Pediatric BMI for Age Observation Profile](StructureDefinition-pediatric-bmi-for-age.md) 
* **SHALL** support: [US Core Pediatric Head Occipital Frontal Circumference Percentile Profile](StructureDefinition-head-occipital-frontal-circumference-percentile.md) 
* **SHALL** support: [US Core Body Weight Profile](StructureDefinition-us-core-body-weight.md) 
* **SHALL** support: [US Core Vital Signs Profile](StructureDefinition-us-core-vital-signs.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a Observation resource using: `GET [base]/Observation/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/Observation?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-observation-patient.md)+[category](SearchParameter-us-core-observation-category.md) | reference+token |
| **SHALL** | [patient](SearchParameter-us-core-observation-patient.md)+[category](SearchParameter-us-core-observation-category.md)+[date](SearchParameter-us-core-observation-date.md) | reference+token+date |
| **SHALL** | [patient](SearchParameter-us-core-observation-patient.md)+[code](SearchParameter-us-core-observation-code.md) | reference+token |
| **SHOULD** | [patient](SearchParameter-us-core-observation-patient.md)+[category](SearchParameter-us-core-observation-category.md)+[status](SearchParameter-us-core-observation-status.md) | reference+token+token |
| **SHOULD** | [patient](SearchParameter-us-core-observation-patient.md)+[category](SearchParameter-us-core-observation-category.md)+[_lastUpdated](SearchParameter-us-core-observation-lastupdated.md) | reference+token+date |
| **SHOULD** | [patient](SearchParameter-us-core-observation-patient.md)+[code](SearchParameter-us-core-observation-code.md)+[date](SearchParameter-us-core-observation-date.md) | reference+token+date |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* A server **SHALL** document the types of changes that can be detected using this parameter.


  A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### Organization

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* Systems **SHALL** support National Provider Identifier (NPI) for organizations and **SHOULD** support Clinical Laboratory Improvement Amendments (CLIA) and the National Association of Insurance Commissioners NAIC Company code (sometimes called "NAIC Number" or "cocode") for `Organization.Identifier`.
* Systems **SHOULD** enable the user who enters the address to follow the Project US@ Technical Specification for Patient Addresses Final Version 1.0 as the standard style guide for `Organization.address.line` and `Organization.address.city`.

Supported Profiles:

* **SHALL** support: [US Core Organization Profile](StructureDefinition-us-core-organization.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a Organization resource using: `GET [base]/Organization/[id]` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [address](SearchParameter-us-core-organization-address.md) | string |
| **SHALL** | [name](SearchParameter-us-core-organization-name.md) | string |

-------

#### Patient

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* The Patient's Social Security Numbers **SHOULD NOT** be used as a patient identifier in `Patient.identifier.value`.
* The Complex Extensions for Race and Ethnicity allow for one or more codes of which: Must Support at least one category code from the OMB Race and Ethnicity Category Value Sets that draw from the Race & Ethnicity - CDC (CDCREC] code system. 
* **MAY** include additional codes from the detailed ethnicity and detailed race value sets drawn from the Race & Ethnicity - CDC (CDCREC) code system
* **SHALL** include a text description
 
* Although Patient.deceased[x] is marked as 𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜, certifying systems are not required to support both choices, but **SHALL** support at least `Patient.deceasedDateTime`.
* Servers can use the US Core Interpreter Needed Extension on this profile or the US Core Encounter Profile to communicate whether a patient needs an interpreter. Although the extension is marked as an **Additional USCDI Requirement** on both US Core Patient and US Core Encounter Profiles, the certifying Server system is not required to support the extension on both profiles but **SHALL** support the extension on at least one. The certifying Client application **SHALL** support the extension on both profiles. 
* Systems **SHOULD** designate the patient's preferred language in the `Patient.communication.preferred` element.
 
* Certifying systems **SHALL** and non-certifying systems **SHOULD** enable the user who enters the address to follow the Project US@ Technical Specification for Patient Addresses Final Version 1.0 as the standard style guide for `Patient.address.line` and `Patient.address.city` for new and updated records.

Supported Profiles:

* **SHALL** support: [US Core Patient Profile](StructureDefinition-us-core-patient.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a Patient resource using: `GET [base]/Patient/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/Patient?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [_id](SearchParameter-us-core-patient-id.md) | token |
| **SHALL** | [identifier](SearchParameter-us-core-patient-identifier.md) | token |
| **SHALL** | [name](SearchParameter-us-core-patient-name.md) | string |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [birthdate](SearchParameter-us-core-patient-birthdate.md)+[name](SearchParameter-us-core-patient-name.md) | date+string |
| **SHOULD** | [birthdate](SearchParameter-us-core-patient-birthdate.md)+[family](SearchParameter-us-core-patient-family.md) | date+string |
| **SHOULD** | [death-date](SearchParameter-us-core-patient-death-date.md)+[family](SearchParameter-us-core-patient-family.md) | date+string |

Search Parameter Requirements (When Used Alone or in Combination):

* A client **SHALL** provide a value precise to the **day**.


  A server **SHALL** support a value a value precise to the **day**.
* A client **SHALL** provide a value precise to the **day**.


  A server **SHALL** support a value a value precise to the **day**.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### Practitioner

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* Servers that support only US Core Practitioner Profile and do not support the US Core PractitionerRole Profile **SHALL** provide implementation specific guidance how to access a provider’s location and contact information using only the Practitioner resource. 
* Although Practitioner.address is marked as Must Support, the server system is not required to support it if they support the US Core PractitionerRole Profile, but **SHALL** support it if they do not support the US Core PractitionerRole Profile. The client application **SHALL** support both.
 
* To balance the privacy of healthcare workers with the patient's right to access information. Only professional/work contact information about the practitioner **SHOULD** be available to the patient (such as a work address or office telephone number).
* Systems **SHOULD** enable the user who enters the address to follow the Project US@ Technical Specification for Patient Addresses Final Version 1.0 as the standard style guide for `Practitioner.address.line` and `Practitioner.address.city`.

Supported Profiles:

* **SHALL** support: [US Core Practitioner Profile](StructureDefinition-us-core-practitioner.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a Practitioner resource using: `GET [base]/Practitioner/[id]` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHOULD** | [_id](SearchParameter-us-core-practitioner-id.md) | token |
| **SHALL** | [identifier](SearchParameter-us-core-practitioner-identifier.md) | token |
| **SHALL** | [name](SearchParameter-us-core-practitioner-name.md) | string |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### PractitionerRole

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* Due to implementer feedback, some US Core Profiles reference the PractitionerRole resource instead of the US Core PractitionerRole Profile. However the US Core PractitionerRole Profile **SHOULD** be used as the default profile if referenced by another US Core profile.

Supported Profiles:

* **SHALL** support: [US Core PractitionerRole Profile](StructureDefinition-us-core-practitionerrole.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a PractitionerRole resource using: `GET [base]/PractitionerRole/[id]` 
*  A Server **SHOULD** be capable of supporting the following _includes: 
*  PractitionerRole:endpoint: `GET [base]/PractitionerRole?[parameter=value]&_include=PractitionerRole:endpoint` 
*  PractitionerRole:practitioner: `GET [base]/PractitionerRole?[parameter=value]&_include=PractitionerRole:practitioner` 
 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [practitioner](SearchParameter-us-core-practitionerrole-practitioner.md) | reference |
| **SHALL** | [specialty](SearchParameter-us-core-practitionerrole-specialty.md) | token |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### Procedure

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* Procedure codes can be taken from SNOMED-CT, CPT, HCPCS II, ICD-10-PCS, CDT. LOINC. 
* Only LOINC concepts that reflect actual procedures **SHOULD** be used
 
* A procedure including a medical device **SHOULD** use `Procedure.focalDevice` with a reference to the **US Core Device Profile**.
* Servers and Clients **SHALL** support both US Core ServiceRequest and US Core Procedure Profiles for communicating the reason or justification for a referral as Additional USCDI Requirements. Typically, the reason or justification for a referral or consultation is communicated through `Procedure.basedOn` linking the Procedure to the US Core ServiceRequest Profile that includes either `ServiceRequest.reasonCode` or `ServiceRequest.reasonReference`. When the Procedure does not have an associated ServiceRequest, it is communicated through the US Core Procedure Profile's `Procedure.reasonCode` or `Procedure.reasonReference`. Depending on the procedure being documented, a server will select the appropriate Profile to use. 
* Although both `Procedure.reasonCode` and `Procedure.reasonReference` are marked as Additional USCDI Requirements. The certifying server system is not required to support both but **SHALL** support at least one of these elements. The certifying client application **SHALL** support both elements. 
* when using `Procedure.reasonReference`: 
* Servers **SHALL** support **at least one** target resource in `Procedure.reasonReference`. Clients **SHALL** support all target resources .
* The referenced resources **SHOULD** be a US Core Profile.
 
 
 

Supported Profiles:

* **SHALL** support: [US Core Procedure Profile](StructureDefinition-us-core-procedure.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a Procedure resource using: `GET [base]/Procedure/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/Procedure?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-procedure-patient.md) | reference |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHOULD** | [patient](SearchParameter-us-core-procedure-patient.md)+[status](SearchParameter-us-core-procedure-status.md) | reference+token |
| **SHALL** | [patient](SearchParameter-us-core-procedure-patient.md)+[date](SearchParameter-us-core-procedure-date.md) | reference+date |
| **SHOULD** | [patient](SearchParameter-us-core-procedure-patient.md)+[code](SearchParameter-us-core-procedure-code.md)+[date](SearchParameter-us-core-procedure-date.md) | reference+token+date |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### Provenance

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* The US Core Provenance resource **SHALL** be supported for these US Core resources: 
* AllergyIntolerance
* CarePlan
* CareTeam
* Condition
* Coverage
* Device
* DiagnosticReport
* DocumentReference
* Encounter
* FamilyMemberHistory
* Goal
* Immunization
* MedicationDispense
* MedicationRequest
* Observation
* Patient
* Procedure
* QuestionnaireResponse
* RelatedPerson
* ServiceRequest
 
* If a system receives a provider in `Provenance.agent.who` as free text they must capture who sent them the information as the organization. On request they **SHALL** provide this organization as the source and **MAY** include the free text provider.
* Systems that need to know the activity has occurred **SHOULD** populate the activity.

Supported Profiles:

* **SHALL** support: [US Core Provenance Profile](StructureDefinition-us-core-provenance.md) 

Profile Interaction Summary:

* **SHALL** support `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `search-type`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a Provenance resource using: `GET [base]/Provenance/[id]` 

-------

#### Questionnaire

Conformance Expectation: **SHOULD**

Resource Specific Documentation:

> 
* US Core defines two ways to represent the questions and responses to screening and assessment instruments:
* US Core Servers **SHALL** support US Core Observation Screening Assessment Profile and **SHOULD** support the SDC Base Questionnaire Profile/US Core QuestionnaireResponse Profile

Supported Profiles:

* **SHALL** support: [SDC Base Questionnaire Profile](http://hl7.org/fhir/uv/sdc/StructureDefinition/sdc-questionnaire) 

Profile Interaction Summary:

* **SHOULD** support `read`, `vread`.
* **MAY** support `create`, `search-type`, `update`, `patch`, `delete`, `history-instance`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHOULD** be capable of returning a Questionnaire resource using: `GET [base]/Questionnaire/[id]` 

-------

#### QuestionnaireResponse

Conformance Expectation: **SHOULD**

Resource Specific Documentation:

> 
* US Core defines two ways to represent the questions and responses to screening and assessment instruments:
* US Core Servers **SHALL** support US Core Observation Screening Assessment Profile and **SHOULD** support the SDC Base Questionnaire Profile/US Core QuestionnaireResponse Profile

Supported Profiles:

* **SHALL** support: [US Core QuestionnaireResponse Profile](StructureDefinition-us-core-questionnaireresponse.md) 

Profile Interaction Summary:

* **SHOULD** support `search-type`, `read`, `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHOULD** be capable of returning a QuestionnaireResponse resource using: `GET [base]/QuestionnaireResponse/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/QuestionnaireResponse?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [_id](SearchParameter-us-core-questionnaireresponse-id.md) | token |
| **SHALL** | [patient](SearchParameter-us-core-questionnaireresponse-patient.md) | reference |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHOULD** | [patient](SearchParameter-us-core-questionnaireresponse-patient.md)+[authored](SearchParameter-us-core-questionnaireresponse-authored.md) | reference+date |
| **SHOULD** | [patient](SearchParameter-us-core-questionnaireresponse-patient.md)+[status](SearchParameter-us-core-questionnaireresponse-status.md) | reference+token |
| **SHOULD** | [patient](SearchParameter-us-core-questionnaireresponse-patient.md)+[questionnaire](SearchParameter-us-core-questionnaireresponse-questionnaire.md) | reference+reference |

Search Parameter Requirements (When Used Alone or in Combination):

* A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### RelatedPerson

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* Systems **SHOULD** enable the user who enters the address to follow the Project US@ Technical Specification for Patient Addresses Final Version 1.0 as the standard style guide for `RelatedPerson.address.line` and `RelatedPerson.address.city`.

Supported Profiles:

* **SHALL** support: [US Core RelatedPerson Profile](StructureDefinition-us-core-relatedperson.md) 

Profile Interaction Summary:

* **SHALL** support `search-type`, `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a RelatedPerson resource using: `GET [base]/RelatedPerson/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/RelatedPerson?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [_id](SearchParameter-us-core-relatedperson-id.md) | token |
| **SHOULD** | [name](SearchParameter-us-core-relatedperson-name.md) | string |
| **SHOULD** | [patient](SearchParameter-us-core-relatedperson-patient.md) | reference |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHOULD** | [patient](SearchParameter-us-core-relatedperson-patient.md)+[name](SearchParameter-us-core-relatedperson-name.md) | reference+string |

Search Parameter Requirements (When Used Alone or in Combination):

* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.

-------

#### ServiceRequest

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* The Must Support `ServiceRequest.category` is bound, **at a minimum**, to the [US Core ServiceRequest Category Codes](ValueSet-us-core-servicerequest-category.md), and other category codes can be used. API consumers can query by category when accessing patient information. For the USCDI **Laboratory Order**, **Imaging Order**, **Clinical Test Order**, and **Procedure Order** Data Elements, implementers **SHOULD** use the corresponding category codes listed in the table on the US Core ServiceRequest Profile page. For example, laboratory orders would have the category code "108252007" (Laboratory procedure).
* The `ServiceRequest.code` value set is broad to accommodate a wide variety of use cases and **SHOULD** be constrained to a subset for a particular use case or domain. These value sets contain concepts that span many use cases and are not bound to any USCDI Data Element. However, the table on the US Core ServiceRequest Profile page identifies **additional** value set bindings for the USCDI **Laboratory Order, Imaging Order and Clinical Test Order** Data Elements. Implementers **SHOULD** conform to the binding strengths for each USCDI Order context listed in the table. For example, laboratory orders are extensibly bound to the LOINC Common Laboratory Orders Value Set. Note that the USCDI Class **Procedure Order** Data Element has no additional binding.
* Servers and Clients **SHALL** support both US Core ServiceRequest and US Core Procedure Profiles for communicating the reason or justification for a referral as Additional USCDI Requirements. Typically, the reason or justification for a referral or consultation is communicated through `Procedure.basedOn` linking the Procedure to the US Core ServiceRequest Profile that includes either `ServiceRequest.reasonCode` or `ServiceRequest.reasonReference`. When the Procedure does not have an associated ServiceRequest, it is communicated through the US Core Procedure Profile's `Procedure.reasonCode` or `Procedure.reasonReference`. Depending on the procedure being documented, a server will select the appropriate Profile to use.

Supported Profiles:

* **SHALL** support: [US Core PMO ServiceRequest Profile](StructureDefinition-us-core-pmo-servicerequest.md) 
* **SHALL** support: [US Core ServiceRequest Profile](StructureDefinition-us-core-servicerequest.md) 

Profile Interaction Summary:

* **SHALL** support `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `search-type`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a ServiceRequest resource using: `GET [base]/ServiceRequest/[id]` 
*  A Server **SHALL** be capable of supporting the following _revincludes: Provenance:target - `GET [base]/ServiceRequest?[parameter=value]&_revinclude=Provenance:target` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [_id](SearchParameter-us-core-servicerequest-id.md) | token |
| **SHALL** | [patient](SearchParameter-us-core-servicerequest-patient.md) | reference |

Search Parameter Combination Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [patient](SearchParameter-us-core-servicerequest-patient.md)+[category](SearchParameter-us-core-servicerequest-category.md) | reference+token |
| **SHOULD** | [patient](SearchParameter-us-core-servicerequest-patient.md)+[status](SearchParameter-us-core-servicerequest-status.md) | reference+token |
| **SHALL** | [patient](SearchParameter-us-core-servicerequest-patient.md)+[code](SearchParameter-us-core-servicerequest-code.md) | reference+token |
| **SHALL** | [patient](SearchParameter-us-core-servicerequest-patient.md)+[category](SearchParameter-us-core-servicerequest-category.md)+[authored](SearchParameter-us-core-servicerequest-authored.md) | reference+token+date |
| **SHOULD** | [patient](SearchParameter-us-core-servicerequest-patient.md)+[code](SearchParameter-us-core-servicerequest-code.md)+[authored](SearchParameter-us-core-servicerequest-authored.md) | reference+token+date |

Search Parameter Requirements (When Used Alone or in Combination):

* A client **SHALL** provide a value precise to the **second + time offset**.


  A server **SHALL** support a value precise to the **second + time offset**.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.


  The server **SHALL** support both.
* The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.


  The server **SHALL** support both.

-------

#### Specimen

Conformance Expectation: **SHALL**

Resource Specific Documentation:

> 
* Although both `Specimen.identifier` and `Specimen.accessionIdentifier` are marked as Must Support, the server system is not required to support both, but **SHALL** support at least one of these elements. The client application **SHALL** support both.

Supported Profiles:

* **SHALL** support: [US Core Specimen Profile](StructureDefinition-us-core-specimen.md) 

Profile Interaction Summary:

* **SHALL** support `read`.
* **SHOULD** support `vread`, `history-instance`.
* **MAY** support `create`, `search-type`, `update`, `patch`, `delete`, `history-type`.

Fetch and Search Criteria:

*  A Server **SHALL** be capable of returning a Specimen resource using: `GET [base]/Specimen/[id]` 

Search Parameter Summary:

| | | |
| :--- | :--- | :--- |
| **SHALL** | [_id](SearchParameter-us-core-specimen-id.md) | token |
| **SHOULD** | [patient](SearchParameter-us-core-specimen-patient.md) | reference |

-------

#### ValueSet

Conformance Expectation: **SHOULD**

Operation Summary:

* If a server supports DocumentReference for creating, using, and sharing clinical notes, it **SHOULD** also support the `context` and `contextdirection` parameters of the $expand operation to enable clients to determine the supported note and report types, as well as the supported read/write formats for notes on the server.

-------



## Resource Content

```json
{
  "resourceType" : "CapabilityStatement",
  "id" : "us-core-server",
  "url" : "http://hl7.org/fhir/us/core/CapabilityStatement/us-core-server",
  "version" : "0.1.0",
  "name" : "UsCoreServerCapabilityStatement",
  "title" : "US Core Server CapabilityStatement",
  "status" : "active",
  "experimental" : false,
  "date" : "2025-11-21T14:02:50.502938-08:00",
  "publisher" : "HL7 International / Cross-Group Projects",
  "contact" : [
    {
      "name" : "HL7 International / Cross-Group Projects",
      "telecom" : [
        {
          "system" : "url",
          "value" : "http://www.hl7.org/Special/committees/cgp"
        },
        {
          "system" : "email",
          "value" : "cgp@lists.HL7.org"
        }
      ]
    }
  ],
  "description" : "This Section describes the expected capabilities of the US Core Server actor which is responsible for providing responses to the queries submitted by the US Core Requestors. The complete list of FHIR profiles, RESTful operations, and search parameters supported by US Core Servers are defined. Systems implementing this capability statement should meet the ASTP 2015 Common Clinical Data Set (CCDS) access requirement for Patient Selection 170.315(g)(7) and Application Access - Data Category Request 170.315(g)(8) and the ASTP [U.S. Core Data for Interoperability (USCDI) Version 6 July 2025](https://www.healthit.gov/isp/sites/isp/files/2025-07/USCDI-Version-6-July-2025.pdf).",
  "jurisdiction" : [
    {
      "coding" : [
        {
          "system" : "urn:iso:std:iso:3166",
          "code" : "US"
        }
      ]
    }
  ],
  "copyright" : "Used by permission of HL7 International, all rights reserved Creative Commons License",
  "kind" : "requirements",
  "fhirVersion" : "4.0.1",
  "format" : ["json", "xml"],
  "_format" : [
    {
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
          "valueCode" : "SHALL"
        }
      ]
    },
    {
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
          "valueCode" : "SHOULD"
        }
      ]
    }
  ],
  "patchFormat" : ["application/json-patch+json"],
  "_patchFormat" : [
    {
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
          "valueCode" : "SHOULD"
        }
      ]
    }
  ],
  "implementationGuide" : [
    "http://hl7.org/fhir/smart-app-launch/ImplementationGuide/hl7.fhir.uv.smart-app-launch"
  ],
  "_implementationGuide" : [
    {
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
          "valueCode" : "SHOULD"
        }
      ]
    }
  ],
  "rest" : [
    {
      "mode" : "server",
      "documentation" : "The US Core Server **SHALL**:\n\n1. Support the US Core Patient resource profile AND at least one additional resource profile from the list of US Core Profiles AND and all *Must Support* US Core Profiles and resources it references.\n     -  A summary table listing all the *Must Support* references to other US Core Profiles and FHIR resources for each US Core Profile is located in the [Must Support - Resource References](must-support.html#must-support---resource-references) section of the guide.\n1. Follow the requirements documented in the [General Requirements](general-requirements.html) and [Must Support](must-support.html) pages\n1. Return the following response classes:\n   - (Status 400): invalid parameter\n   - (Status 401/4xx): unauthorized request\n   - (Status 403): insufficient scopes\n   - (Status 404): unknown resource\n1. Support JSON source formats for all US Core interactions.\n\nThe US Core Server **SHOULD**:\n\n1. Follow the guidance documented in the [General Guidance](general-guidance.html) page\n1. Support XML source formats for all US Core interactions.\n1. Identify the US Core profiles supported as part of the FHIR `meta.profile` attribute for each instance.\n\n\n**NOTE**: US Core SearchParameters referenced in this CapabilityStatement that are derived from standard FHIR SearchParameters are only defined to document Server and Client expectations. They specify additional expectations for the following SearchParameter elements:\n \n- `multipleAnd`\n- `multipleOr`\n- `comparator`\n- `modifier`\n- `chain`\n\nThey **SHALL NOT** be interpreted as search parameters for search. Servers and Clients **SHOULD** use the standard FHIR SearchParameters.",
      "security" : {
        "description" : "1. See the [General Security Considerations](security.html) section for requirements and recommendations.\n1. A server **SHALL** reject any unauthorized requests by returning an `HTTP 401` \"Unauthorized\", `HTTP 403` \"Forbidden\", or `HTTP 404` \"Not Found\""
      },
      "resource" : [
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "clinical-status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "AllergyIntolerance",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-allergyintolerance|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "clinical-status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-allergyintolerance-clinical-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-allergyintolerance-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                },
                {
                  "url" : "required",
                  "valueString" : "status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                },
                {
                  "url" : "required",
                  "valueString" : "date"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                },
                {
                  "url" : "required",
                  "valueString" : "status"
                },
                {
                  "url" : "required",
                  "valueString" : "date"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "CarePlan",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-careplan|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* Additional considerations for systems aligning with [HL7 Consolidated (C-CDA)](http://www.hl7.org/implement/standards/product_brief.cfm?product_id=492) Care Plan requirements:\n\n    - US Core Goal **SHOULD** be present in CarePlan.goal\n\n    - US Core Condition **SHOULD** be present in\nCarePlan.addresses\n\n    - Assessment and Plan **MAY** be included as narrative\ntext",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "category",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-careplan-category",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "date",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-careplan-date",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-careplan-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-careplan-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "role"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "CareTeam",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-careteam|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* In order to access care team member's names, identifiers, locations, and contact information, the CareTeam profile supports several types of care team participants. They are represented as references to other profiles and include the following four profiles which are marked as must support:\n\n  1. US Core Practitioner Profile\n\n  1. US Core PractitionerRole Profile\n\n  1. US Core Patient Profile\n\n  1. US Core RelatedPerson Profile\n\n* Although *both* US Core Practitioner Profile and US Core PractitionerRole are must support, the server system is not required to support both types of references, but **SHALL** support *at least* one of them.\n* The client application **SHALL** support all four profile references.\n* Bacause the *US Core PractitionerRole Profile* supplies the provider's location and contact information and a reference to the Practitioner, server systems **SHOULD** reference it instead of the *US Core Practitioner Profile*.\n* Servers that support only US Core Practitioner Profile and do not support the US Core PractitionerRole Profile **SHALL** provide implementation specific guidance how to access a provider’s location and contact information using only the Practitioner resource.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchInclude" : [
            "CareTeam:participant:PractitionerRole",
            "CareTeam:participant:Practitioner",
            "CareTeam:participant:Patient",
            "CareTeam:participant:RelatedPerson"
          ],
          "_searchInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ]
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-careteam-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "name" : "role",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-careteam-role",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-careteam-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "_lastUpdated"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                },
                {
                  "url" : "required",
                  "valueString" : "encounter"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                },
                {
                  "url" : "required",
                  "valueString" : "clinical-status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "recorded-date"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "clinical-status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "code"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "asserted-date"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "abatement-date"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "onset-date"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "Condition",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-condition-encounter-diagnosis|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-condition-problems-health-concerns|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* For Encounter Diagnosis use the *US Core Condition Encounter Diagnosis Profile*.\n\n  * When `Condition.category` is \"encounter-diagnosis\" the\nencounter, **SHOULD** be referenced in `Condition.encounter`.\n* For Problems and Health Concerns use the *US Core Condition Problems and Health Concerns Profile*.\n\n  * When `Condition.category` is a \"problems-list-item\", the\n`Condition.clinicalStatus **SHOULD** be present.\n\n * See the US Core General Guidance page for [Searching Using\nlastUpdated](general-guidance.html#searching-using-lastupdated). Updates to `Condition.meta.lastUpdated` **SHOULD** reflect:\n\n    * New problems and health concerns\n\n    * Changes in the clinical status or verifications status\nof problems or health concern",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type",
              "documentation" : "Foo Bar Baz"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "abatement-date",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-condition-abatement-date",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "asserted-date",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-condition-asserted-date",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "category",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-condition-category",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "clinical-status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-condition-clinical-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "code",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-condition-code",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "encounter",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-condition-encounter",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "onset-date",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-condition-onset-date",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-condition-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "recorded-date",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-condition-recorded-date",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "_lastUpdated",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-condition-lastupdated",
              "type" : "date",
              "documentation" : "A server **SHALL** document the types of changes that can be detected using this parameter.\n\n\nA client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            }
          ],
          "type" : "Coverage",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-coverage|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-coverage-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "type"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "Device",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-device|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* Medical devices with UDI information **SHALL** represent the UDI code in `Device.udiCarrier.carrierHRF`. All five UDI-PI elements defined in the UDI code may not always be present in every UDI instance. However, those UDI-PI elements present **SHALL** be represented in the corresponding *US Core Device Profile elements.\n\n\n\n   UDI may not be present in all scenarios, such as\nhistorical medical devices, patient-reported implant information, payer-reported devices, or improperly documented implants. If UDI is not present and the manufacturer or model number information is available, they **SHOULD** be included to support historical reports of medical devices as follows:\n\n\n\n   |data element|*US Core Device Profile element|\n\n   |---|---|\n\n   |manufacturer|`Device.manufacturer`|\n\n   |model|`Device.model`|\n\n   {:.grid}",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-device-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-device-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "type",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-device-type",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                },
                {
                  "url" : "required",
                  "valueString" : "date"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "code"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                },
                {
                  "url" : "required",
                  "valueString" : "_lastUpdated"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "code"
                },
                {
                  "url" : "required",
                  "valueString" : "date"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "DiagnosticReport",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-diagnosticreport-note|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-diagnosticreport-lab|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* For laboratory result reports use the *US Core DiagnosticReport Profile for Laboratory Results Reporting Profile*.\n\n  * Updates to `.meta.lastUpdated` **SHOULD** reflect:\n\n    * New laboratory reports\n\n    * Changes in the status of laboratory reports including\nevents that trigger the same status (e.g., amended → amended).\n* For imaging and non-laboratory clinical test result reports use the *US Core DiagnosticReport Profile for Report and Note Exchange Profile*.\n\n  * Diagnostic imaging results in visual images requiring\ninterpretation and clinical test results/reports may also reference images as part of the report. There is no single approach for accessing imaging studies alongside clinical data using a single authorization flow to give patients and providers access to the images.\n\n     * The `DiagnosticReport.media.link` element **SHOULD**\nbe used to support links to various patient-friendly content, such as jpg images of x-rays (see the DiagnosticReport Chest X-ray Report Example).\n\n     * The `DiagnosticReport.imagingStudy` element **SHOULD**\nbe used to support exchange with systems that can view DICOM (Digital Imaging and Communications in Medicine) studies, series, and SOP (Service-Object Pair) instances referenced in the [ImagingStudy] resource.\n\n     * Alternatively, systems can use business identifiers\nsuch as accession numbers in the `identifier` element to access the source images from external sources.\n* The `DiagnosticRequest.basedOn` element connects the DiagnosticReport to the originating order in the EHR. Systems that initiate the lab order **SHOULD** use this element when reporting the results.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "create",
              "documentation" : "This conformance expectation applies **only**  to the *US Core DiagnosticReport Profile for Report and Note exchange* profile.  The conformance expectation for the *US Core DiagnosticReport Profile for Laboratory Results Reporting* is  **MAY**."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "category",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-diagnosticreport-category",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "code",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-diagnosticreport-code",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "date",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-diagnosticreport-date",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "_lastUpdated",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-diagnosticreport-lastupdated",
              "type" : "date",
              "documentation" : "A server **SHALL** document the types of changes that can be detected using this parameter.\n\n\nA client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-diagnosticreport-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-diagnosticreport-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "type"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                },
                {
                  "url" : "required",
                  "valueString" : "date"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "type"
                },
                {
                  "url" : "required",
                  "valueString" : "period"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "DocumentReference",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-documentreference|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-adi-documentreference|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* For Advance Directive Information (ADI) documents use the *US Core ADI DocumentReference Profile*.\n* For other clinical documents use the *US Core DiagnosticReport Profile for Report and Note Exchange*.\n\n  * See the [Clinical Notes](clinical-notes.html) page for\nimportant definitions, requirements, and guidance on creating, using, and sharing Clinical Notes.\n\n  * The `DocumentReference.type` binding Must Support at\na minimum the [10 Common Clinical Notes](ValueSet-us-core-clinical-note-type.html) and may extend to the full US Core DocumentReference Type Value Set\n* The DocumentReference resources can represent the referenced content using either an address where the document can be retrieved using `DocumentReference.attachment.url` or the content as inline base64 encoded data using `DocumentReference.attachment.data`.\n\n    *  Although both are marked as must support, the server\nsystem is not required to support an address, and inline base64 encoded data, but **SHALL** support at least one of these elements.\n\n    *  The client application **SHALL** support both\nelements.\n\n    *  The `content.attachment.url` may refer to a FHIR\nBinary Resource (i.e. [base]/Binary/[id]), FHIR Document Bundle (i.e [base]/Bundle/[id] or another endpoint.\n\n   * If there are multiple `DocumentReference.content`\nelement repetitions, these **SHALL** all represent the same document in different format or attachment metadata. The content element **SHALL NOT** contain different versions of the same content. For version handling use multiple DocumentReferences with `DocumentReference.relatesTo`\n* Every DocumentReference must have a responsible Organization. The organization responsible for the DocumentReference **SHALL** be present either in `DocumentReference.custodian` or accessible in the Provenance resource targeting the DocumentReference using `Provenance.agent.who` or `Provenance.agent.onBehalfOf`.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "_id",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-documentreference-id",
              "type" : "token"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "category",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-documentreference-category",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "date",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-documentreference-date",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-documentreference-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "period",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-documentreference-period",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-documentreference-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "type",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-documentreference-type",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            }
          ],
          "operation" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "docref",
              "definition" : "http://hl7.org/fhir/us/core/OperationDefinition/docref",
              "documentation" : "A server **SHALL** be capable of responding to a $docref operation and  capable of returning at least a reference to a generated CCD document, if available. **MAY** provide references to other 'on-demand' and 'stable' documents (or 'delayed/deferred assembly') that meet the query parameters as well. If a context date range is supplied the server ** SHOULD**  provide references to any document that falls within the date range.  If no date range is supplied, then the server **SHALL** provide references to last or current document(s).  **SHOULD** document what resources, if any, are returned as included resources\n\n\n`GET [base]/DocumentReference/$docref?patient=[id]`"
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "location"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "_lastUpdated"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "type"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "date"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "class"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "discharge-disposition"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "Encounter",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-encounter|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* The Encounter resource can represent a reason using either a code with `Encounter.reasonCode`, or a reference with `Encounter.reasonReference` to  Condition or other resource.\n\n   * Although both are marked as must support, the server\nsystems are not required to support both a code and a reference, but they **SHALL** support *at least one* of these elements.\n\n   * The client application **SHALL** support both elements.\n\n   * if `Encounter.reasonReference` references an\nObservation, it **SHOULD** conform to a US Core Observation if applicable. (for example, a laboratory result should conform to the US Core Laboratory Result Observation Profile)\n\n\n* The location address can be represented by either by the Location referenced by `Encounter.location.location` or indirectly through the Organization referenced by `Encounter.serviceProvider`.\n\n   * Although both are marked as must support, the server\nsystems are not required to support both `Encounter.location.location` and `Encounter.serviceProvider`, but they **SHALL** support *at least one* of these elements.\n\n   * The client application **SHALL** support both elements.\n\n* If the event facility/location differs from the `Encounter.location`, systems **SHOULD** reference it directly:\n* Servers can use the US Core Interpreter Needed Extension on this profile or the [US Core Patient Profile] to communicate whether a patient needs an interpreter. Although the extension is marked as an *Additional USCDI Requirements* on both US Core Patient and US Core Encounter Profiles, the certifying Server system is not required to support the extension on both profiles, but **SHALL** support the extension on at least one. The certifying Client application **SHALL** support the extension on both profiles.\n\n  - Systems **SHOULD** designate the patient's preferred\nlanguage in the `Patient.communication.preferred` element.\n* Updates to `.meta.lastUpdated` **SHOULD** reflect:\n\n  - New encounters/visits\n\n  - Changes in the status of encounters, including events\nthat trigger the same status (e.g., in-progress → in-progress). These status changes correspond to events that can initiate [HL7 V2] ADT messages.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "_id",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-encounter-id",
              "type" : "token"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "class",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-encounter-class",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "date",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-encounter-date",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "_lastUpdated",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-encounter-lastupdated",
              "type" : "date",
              "documentation" : "A server **SHALL** document the types of changes that can be detected using this parameter.\n\n\nA client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "discharge-disposition",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-encounter-discharge-disposition",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "name" : "identifier",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-encounter-identifier",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "location",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-encounter-location",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-encounter-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-encounter-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "type",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-encounter-type",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            }
          ],
          "type" : "Endpoint",
          "documentation" : "The Media Resource is a Must Support referenced resource when using the US Core PractitionerRole Profile.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "code"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "FamilyMemberHistory",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-familymemberhistory|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-familymemberhistory-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "code",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-familymemberhistory-code",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "lifecycle-status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "target-date"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "description"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "Goal",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-goal|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* Although both `Goal.startDate` and `Goal.target.dueDate` are marked as must support, the server system is not required to support both, but **SHALL** support at least one of these elements. The client application **SHALL** support both elements.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "description",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-goal-description",
              "type" : "token"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "lifecycle-status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-goal-lifecycle-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-goal-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "target-date",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-goal-target-date",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *day*.\n\n\nA server **SHALL** support a value a value precise to the *day*."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "MAY"
            }
          ],
          "type" : "HealthcareService",
          "documentation" : "The HealthcareService Resource is a referenced resource when using the US Core PractitionerRole Profile and subject to constraint us-core-13: \"SHALL have a practitioner, an organization, a healthcare service, or a location.\"",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "date"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "Immunization",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-immunization|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* Based upon the ASTP U.S. Core Data for Interoperability (USCDI) requirements, CVX vaccine codes are required and the NDC vaccine codes **SHOULD** be supported as an additional code.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "date",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-immunization-date",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-immunization-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-immunization-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            }
          ],
          "type" : "Location",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-location|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* Systems **SHOULD** enable the user who enters the address to follow the Project US@ Technical Specification for Patient Addresses Final Version 1.0 as the standard style guide for `Location.address.line` and  `Location.address.city`.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "address",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-location-address",
              "type" : "string"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "name" : "address-city",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-location-address-city",
              "type" : "string"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "name" : "address-postalcode",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-location-address-postalcode",
              "type" : "string"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "name" : "address-state",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-location-address-state",
              "type" : "string"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "name",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-location-name",
              "type" : "string"
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            }
          ],
          "type" : "Media",
          "documentation" : "The Media Resource is a Must Support referenced resource when using the US Core DiagnosticReport Profile for Report and Note Exchange.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            }
          ],
          "type" : "Medication",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-medication|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* The  MedicationRequest resource can represent a medication, using an external reference to a Medication resource. If an external Medication Resource is used in a MedicationRequest, then the READ  **SHALL**  be supported.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "status"
                },
                {
                  "url" : "required",
                  "valueString" : "type"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "MedicationDispense",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-medicationdispense|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* This Profile can represent a medication using a code or reference a Medication resource.\n\n  * The Server systems are not required to support both\na code and a reference, but **SHALL** support at least one of these methods.\n\n  * The Client application **SHALL** support all methods.\n\n  * Systems that primarily rely on NDC codes instead of\nRxNorm to represent medications can use the National Library of Medicine's (NLM) NDC to RxNorm mappings to aid in additional codings.\n\n  * When referencing a Medication resource in\n`.medicationReference`, the resource may be contained or an external resource. If an external reference to a Medication resource is used, the Server **SHALL** support the `_include` parameter for searching this element.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchInclude" : ["MedicationDispense:medication"],
          "_searchInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ]
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-medicationdispense-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-medicationdispense-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "type",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-medicationdispense-type",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "intent"
                },
                {
                  "url" : "required",
                  "valueString" : "authoredon"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "intent"
                },
                {
                  "url" : "required",
                  "valueString" : "status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "intent"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "intent"
                },
                {
                  "url" : "required",
                  "valueString" : "encounter"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "MedicationRequest",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-medicationrequest|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* This Profile can represent a medication using a code or reference a Medication resource.\n  * The Server systems are not required to support both a code and a reference, but **SHALL** support at least one of these methods.\n  * The Client application **SHALL** support all methods.\n  * Systems that primarily rely on NDC codes instead of RxNorm to represent medications can use the National Library of Medicine's (NLM) NDC to RxNorm mappings to aid in additional codings.\n  * When referencing a Medication resource in `.medicationReference`, the resource may be contained or an external resource. If an external reference to a Medication resource is used, the Server **SHALL** support the `_include` parameter for searching this element. \n\n* The MedicationRequest resource can represent that information is from a secondary source using either a boolean flag or reference in `MedicationRequest.reportedBoolean`, or a reference using `MedicationRequest.reportedReference` to Practitioner or other resource.\n   *  Although both are marked as must support, the server systems are not required to support both a boolean and a reference, but **SHALL** choose to support at least one of these elements.\n   *  The client application **SHALL** support both elements.\n\n* When recording “self-prescribed” medication, requester **SHOULD** be used to indicate the Patient or RelatedPerson as the prescriber. (See the Medication List section for guidance on accessing a patient medications including over the counter (OTC) medication and other substances taken for medical and recreational use.)\n\n* The MedicationRequest resource can communicate the reason or indication for treatment using either a code in MedicationRequest.reasonCode or a reference using MedicationRequest.reasonReference.\n  * Although both `MedicationRequest.reasonCode` and `MedicationRequest.reasonReference` are marked as Additional USCDI Requirements. The certifying server system is not required to support both but **SHALL** support at least one of these elements. The certifying client application **SHALL** support both elements.\n  * when using MedicationRequest.reasonReference:\n      * Servers **SHALL** support at least one target resource in `MedicationRequest.reasonReference`. Clients **SHALL** support all target resources.\n      * The referenced resources **SHOULD** be a US Core Profile as documented in Referencing US Core Profiles.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchInclude" : ["MedicationRequest:medication"],
          "_searchInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ]
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "authoredon",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-medicationrequest-authoredon",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "encounter",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-medicationrequest-encounter",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "intent",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-medicationrequest-intent",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-medicationrequest-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-medicationrequest-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                },
                {
                  "url" : "required",
                  "valueString" : "date"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "code"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                },
                {
                  "url" : "required",
                  "valueString" : "status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                },
                {
                  "url" : "required",
                  "valueString" : "_lastUpdated"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "code"
                },
                {
                  "url" : "required",
                  "valueString" : "date"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "Observation",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-adi-documentation|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-lab|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-pregnancystatus|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-pregnancyintent|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-occupation|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-respiratory-rate|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-simple-observation|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-treatment-intervention-preference|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-care-experience-preference|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-heart-rate|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-body-temperature|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/pediatric-weight-for-height|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-pulse-oximetry|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-smokingstatus|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-sexual-orientation|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-head-circumference|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-body-height|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-bmi|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-screening-assessment|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-average-blood-pressure|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-blood-pressure|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-clinical-result|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/pediatric-bmi-for-age|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/head-occipital-frontal-circumference-percentile|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-body-weight|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-vital-signs|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* Systems **SHOULD** support `Observation.effectivePeriod` to accurately represent tests that are collected over a period of time (for example, a 24-Hour Urine Collection test).\n* An Observation without a value, **SHALL** include a reason why the data is absent unless there are component observations, or references to other Observations that are grouped within it\n    * Systems that never provide an observation without a value are not required to support `Observation.dataAbsentReason`\n*  An `Observation.component` without a value, **SHALL** include a reason why the data is absent.\n    * Systems that never provide an component observation without a component value are not required to support `Observation.component.dataAbsentReason`.\n * There are multiple Observation profiles.  Refer to the specific profile page for profile specific conformance rules and guidance ",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "category",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-observation-category",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "code",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-observation-code",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "date",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-observation-date",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "_lastUpdated",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-observation-lastupdated",
              "type" : "date",
              "documentation" : "A server **SHALL** document the types of changes that can be detected using this parameter.\n\n\nA client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-observation-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-observation-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            }
          ],
          "type" : "Organization",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* Systems **SHALL** support National Provider Identifier (NPI) for organizations and **SHOULD** support Clinical Laboratory Improvement Amendments (CLIA) and the National Association of Insurance Commissioners NAIC Company code (sometimes called \"NAIC Number\" or \"cocode\")  for `Organization.Identifier`.\n* Systems **SHOULD** enable the user who enters the address to follow the Project US@ Technical Specification for Patient Addresses Final Version 1.0 as the standard style guide for `Organization.address.line` and  `Organization.address.city`.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "address",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-organization-address",
              "type" : "string"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "name",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-organization-name",
              "type" : "string"
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "birthdate"
                },
                {
                  "url" : "required",
                  "valueString" : "name"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "birthdate"
                },
                {
                  "url" : "required",
                  "valueString" : "family"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "death-date"
                },
                {
                  "url" : "required",
                  "valueString" : "family"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "Patient",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* The Patient's Social Security Numbers **SHOULD NOT** be used as a patient identifier in `Patient.identifier.value`.\n*  The Complex Extensions for Race and Ethnicity allow for one or more codes of which: Must Support at least one category code from the OMB Race and Ethnicity Category Value Sets that draw from the Race & Ethnicity - CDC (CDCREC] code system.\n    - **MAY** include additional codes from the detailed ethnicity and detailed race value sets drawn from the Race & Ethnicity - CDC (CDCREC) code system\n    - **SHALL** include a text description\n* Although Patient.deceased[x] is marked as 𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜, certifying systems are not required to support both choices, but **SHALL** support at least `Patient.deceasedDateTime`.\n*  Servers can use the US Core Interpreter Needed Extension on this profile or the US Core Encounter Profile to communicate whether a patient needs an interpreter. Although the extension is marked as an *Additional USCDI Requirement* on both US Core Patient and US Core Encounter Profiles, the certifying Server system is not required to support the extension on both profiles but **SHALL** support the extension on at least one. The certifying Client application **SHALL** support the extension on both profiles.\n     - Systems **SHOULD** designate the patient's preferred language in the `Patient.communication.preferred` element.\n* Certifying systems **SHALL** and non-certifying systems **SHOULD** enable the user who enters the address to follow the Project US@ Technical Specification for Patient Addresses Final Version 1.0 as the standard style guide for `Patient.address.line` and  `Patient.address.city` for new and updated records.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "_id",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-patient-id",
              "type" : "token"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "birthdate",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-patient-birthdate",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *day*.\n\n\nA server **SHALL** support a value a value precise to the *day*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "death-date",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-patient-death-date",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *day*.\n\n\nA server **SHALL** support a value a value precise to the *day*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "family",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-patient-family",
              "type" : "string"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "given",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-patient-given",
              "type" : "string"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "identifier",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-patient-identifier",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "name",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-patient-name",
              "type" : "string"
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            }
          ],
          "type" : "Practitioner",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitioner|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* Servers that support only US Core Practitioner Profile and do not support the US Core PractitionerRole Profile **SHALL** provide implementation specific guidance how to access a provider’s location and contact information using only the Practitioner resource.\n\n   * Although Practitioner.address is marked as Must Support,\nthe server system is not required to support it if they support the US Core PractitionerRole Profile, but **SHALL** support it if they do not support the US Core PractitionerRole Profile. The client application **SHALL** support both.\n* To balance the privacy of healthcare workers with the patient's right to access information. Only professional/work contact information about the practitioner **SHOULD** be available to the patient (such as a work address or office telephone number).\n* Systems **SHOULD** enable the user who enters the address to follow the Project US@ Technical Specification for Patient Addresses Final Version 1.0 as the standard style guide for `Practitioner.address.line` and  `Practitioner.address.city`.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "name" : "_id",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-practitioner-id",
              "type" : "token"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "identifier",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-practitioner-identifier",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "name",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-practitioner-name",
              "type" : "string"
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            }
          ],
          "type" : "PractitionerRole",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitionerrole|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* Due to implementer feedback, some US Core Profiles reference the PractitionerRole resource instead of the US Core PractitionerRole Profile. However the US Core PractitionerRole Profile **SHOULD** be used as the default profile if referenced by another US Core profile.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchInclude" : ["PractitionerRole:endpoint", "PractitionerRole:practitioner"],
          "_searchInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "practitioner",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-practitionerrole-practitioner",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "specialty",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-practitionerrole-specialty",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "date"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "code"
                },
                {
                  "url" : "required",
                  "valueString" : "date"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "Procedure",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-procedure|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* Procedure codes can be taken from SNOMED-CT, CPT, HCPCS II, ICD-10-PCS, CDT. LOINC.\n\n  * Only LOINC concepts that reflect actual procedures\n**SHOULD** be used\n* A procedure including a medical device **SHOULD** use `Procedure.focalDevice` with a reference to the *US Core Device Profile*.\n* Servers and Clients **SHALL** support both US Core ServiceRequest and US Core Procedure Profiles for communicating the reason or justification for a referral as Additional USCDI Requirements. Typically, the reason or justification for a referral or consultation is communicated through `Procedure.basedOn` linking the Procedure to the US Core ServiceRequest Profile that includes either `ServiceRequest.reasonCode` or `ServiceRequest.reasonReference`. When the Procedure does not have an associated ServiceRequest, it is communicated through the US Core Procedure Profile's `Procedure.reasonCode` or `Procedure.reasonReference`.  Depending on the procedure being documented, a server will select the appropriate Profile to use.\n\n   * Although both `Procedure.reasonCode` and\n`Procedure.reasonReference` are marked as Additional USCDI Requirements. The certifying server system is not required to support both but **SHALL** support at least one of these elements. The certifying client application **SHALL** support both elements.\n\n      * when using  `Procedure.reasonReference`:\n\n         * Servers **SHALL** support *at least one* target\nresource in `Procedure.reasonReference`. Clients **SHALL** support all target resources .\n\n         * The referenced resources **SHOULD** be a US Core\nProfile.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "code",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-procedure-code",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "date",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-procedure-date",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-procedure-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-procedure-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            }
          ],
          "type" : "Provenance",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-provenance|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* The US Core Provenance resource **SHALL** be supported for these US Core resources:\n\n    * AllergyIntolerance\n\n    * CarePlan\n\n    * CareTeam\n\n    * Condition\n\n    * Coverage\n\n    * Device\n\n    * DiagnosticReport\n\n    * DocumentReference\n\n    * Encounter\n\n    * FamilyMemberHistory\n\n    * Goal\n\n    * Immunization\n\n    * MedicationDispense\n\n    * MedicationRequest\n\n    * Observation\n\n    * Patient\n\n    * Procedure\n\n    * QuestionnaireResponse\n\n    * RelatedPerson\n\n    * ServiceRequest\n\n* If a system receives a provider in `Provenance.agent.who` as free text they must capture who sent them the information as the organization. On request they **SHALL** provide this organization as the source and **MAY** include the free text provider.\n* Systems that need to know the activity has occurred **SHOULD** populate the activity.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHOULD"
            }
          ],
          "type" : "Questionnaire",
          "supportedProfile" : [
            "http://hl7.org/fhir/uv/sdc/StructureDefinition/sdc-questionnaire"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* US Core defines two ways to represent the questions and responses to screening and assessment instruments:\n\n\n\n  - Observation: US Core Observation Screening Assessment\nProfile\n\n  - Questionnaire/QuestionnaireResponse: SDC Base\nQuestionnaire/US Core QuestionnaireResponse Profile\n\n\n* US Core Servers **SHALL** support US Core Observation Screening Assessment Profile and **SHOULD** support the  SDC Base Questionnaire Profile/US Core QuestionnaireResponse Profile",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHOULD"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "authored"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "questionnaire"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "QuestionnaireResponse",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-questionnaireresponse|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* US Core defines two ways to represent the questions and responses to screening and assessment instruments:\n\n\n\n  - Observation: US Core Observation Screening Assessment\nProfile\n\n  - Questionnaire/QuestionnaireResponse: SDC Base\nQuestionnaire/US Core QuestionnaireResponse Profile\n\n\n* US Core Servers **SHALL** support US Core Observation Screening Assessment Profile and **SHOULD** support the  SDC Base Questionnaire Profile/US Core QuestionnaireResponse Profile",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "_id",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-questionnaireresponse-id",
              "type" : "token"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "authored",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-questionnaireresponse-authored",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-questionnaireresponse-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "questionnaire",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-questionnaireresponse-questionnaire",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-questionnaireresponse-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "name"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "RelatedPerson",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-relatedperson|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* Systems **SHOULD** enable the user who enters the address to follow the Project US@ Technical Specification for Patient Addresses Final Version 1.0 as the standard style guide for `RelatedPerson.address.line` and  `RelatedPerson.address.city`.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "_id",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-relatedperson-id",
              "type" : "token"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "name" : "name",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-relatedperson-name",
              "type" : "string"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-relatedperson-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "status"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "code"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "category"
                },
                {
                  "url" : "required",
                  "valueString" : "authored"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                },
                {
                  "url" : "required",
                  "valueString" : "patient"
                },
                {
                  "url" : "required",
                  "valueString" : "code"
                },
                {
                  "url" : "required",
                  "valueString" : "authored"
                }
              ],
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-search-parameter-combination"
            }
          ],
          "type" : "ServiceRequest",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-pmo-servicerequest|9.0.0-ballot",
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-servicerequest|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* The Must Support `ServiceRequest.category` is bound, *at a minimum*, to the [US Core ServiceRequest Category Codes](ValueSet-us-core-servicerequest-category.html), and other category codes can be used. API consumers can query by category when accessing patient information. For the USCDI *Laboratory Order*, *Imaging Order*, *Clinical Test Order*, and *Procedure Order* Data Elements, implementers **SHOULD** use the corresponding category codes listed in the table on the US Core ServiceRequest Profile page. For example, laboratory orders would have the category code \"108252007\" (Laboratory procedure).\n\n\n* The `ServiceRequest.code` value set is broad to accommodate a wide variety of use cases and **SHOULD** be constrained to a subset for a particular use case or domain.  These value sets contain concepts that span many use cases and are not bound to any USCDI Data Element. However, the table on the US Core ServiceRequest Profile page identifies *additional* value set bindings for the USCDI *Laboratory Order, Imaging Order and Clinical Test Order* Data Elements. Implementers **SHOULD** conform to the binding strengths for each USCDI Order context listed in the table. For example, laboratory orders are extensibly bound to the LOINC Common Laboratory Orders Value Set. Note that the USCDI Class *Procedure Order* Data Element has no additional binding.\n\n\n* Servers and Clients **SHALL** support both US Core ServiceRequest and US Core Procedure Profiles for communicating the reason or justification for a referral as Additional USCDI Requirements. Typically, the reason or justification for a referral or consultation is communicated through `Procedure.basedOn` linking the Procedure to the US Core ServiceRequest Profile that includes either `ServiceRequest.reasonCode` or `ServiceRequest.reasonReference`. When the Procedure does not have an associated ServiceRequest, it is communicated through the US Core Procedure Profile's `Procedure.reasonCode` or `Procedure.reasonReference`. Depending on the procedure being documented, a server will select the appropriate Profile to use.\n\n   * Although both `ServiceRequest.reasonCode` and\n`ServiceRequest.reasonReference` are marked as Additional USCDI Requirements, the certifying server system is not required to support both, but **SHALL** support at least one of these elements. The certifying client application **SHALL** support both elements.\n\n     * when using  `ServiceRequest.reasonReference`:\n\n       * Servers **SHALL** support *at least one* target\nresource in `ServiceRequest.reasonReference`. Clients **SHALL** support all target resources.\n\n       * The referenced resources **SHOULD** be a US Core\nProfile as documented in Referencing US Core Profiles.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchRevInclude" : ["Provenance:target"],
          "_searchRevInclude" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "_id",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-servicerequest-id",
              "type" : "token"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "authored",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-servicerequest-authored",
              "type" : "date",
              "documentation" : "A client **SHALL** provide a value precise to the *second + time offset*.\n\n\nA server **SHALL** support a value precise to the *second + time offset*."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "category",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-servicerequest-category",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "code",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-servicerequest-code",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-servicerequest-patient",
              "type" : "reference",
              "documentation" : "The client **SHALL** provide at least a id value and **MAY** provide both the Type and id values.\n\n\nThe server **SHALL** support both."
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "name" : "status",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-servicerequest-status",
              "type" : "token",
              "documentation" : "The client **SHALL** provide at least a code value and **MAY** provide both the system and code values.\n\n\nThe server **SHALL** support both."
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHALL"
            }
          ],
          "type" : "Specimen",
          "supportedProfile" : [
            "http://hl7.org/fhir/us/core/StructureDefinition/us-core-specimen|9.0.0-ballot"
          ],
          "_supportedProfile" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ]
            }
          ],
          "documentation" : "* Although both `Specimen.identifier` and `Specimen.accessionIdentifier` are marked as Must Support, the server system is not required to support both, but **SHALL** support at least one of these elements. The client application **SHALL** support both.",
          "interaction" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "create"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "search-type"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "code" : "read"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "vread"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "update"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "patch"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "delete"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "code" : "history-instance"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "MAY"
                }
              ],
              "code" : "history-type"
            }
          ],
          "searchParam" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHALL"
                }
              ],
              "name" : "_id",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-specimen-id",
              "type" : "token"
            },
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "name" : "patient",
              "definition" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-specimen-patient",
              "type" : "reference"
            }
          ]
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "SHOULD"
            }
          ],
          "type" : "ValueSet",
          "operation" : [
            {
              "extension" : [
                {
                  "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
                  "valueCode" : "SHOULD"
                }
              ],
              "name" : "expand",
              "definition" : "http://hl7.org/fhir/OperationDefinition/ValueSet-expand",
              "documentation" : "If a server supports DocumentReference for creating, using, and sharing clinical notes, it **SHOULD** also support the `context` and `contextdirection` parameters of the $expand operation to enable clients to determine the supported note and report types, as well as the supported read/write formats for notes on the server."
            }
          ]
        }
      ],
      "interaction" : [
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "MAY"
            }
          ],
          "code" : "transaction"
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "MAY"
            }
          ],
          "code" : "batch"
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "MAY"
            }
          ],
          "code" : "search-system"
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
              "valueCode" : "MAY"
            }
          ],
          "code" : "history-system"
        }
      ]
    }
  ]
}

```
