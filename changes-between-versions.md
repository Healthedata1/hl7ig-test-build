# Versions - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* **Versions**

## Versions

| |
| :--- |
| *Page standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) |

### Introduction

With each major version of FHIR, the core data models have changed. The FHIR core specification provides a [base resource differential] to help implementers navigate version changes. However, there are additional considerations for the user and developer experience when transitioning from [FHIR Version DSTU2] to FHIR R4. Similarly, US Core undergoes annual updates, which are documented on the [US Core Roadmap] page. Each update to a new version of US Core changes the US Core Profiles and conformance expectations. The following guidance on this page is provided to ensure a smoother upgrade path. It reflects non-normative best practices established at the time of publication.

### Versioning of US Core

US Core undergoes annual updates with new guidance, requirements, profiles, and changes to existing content. The [Directory of published versions] lists the publication history with links to each version of US Core. The [Change Log](changes.md) documents the changes across the versions of US Core. The [Argonaut Data Query] guide was published separately and is not included in the directory or change log.

When a change is identified that impacts ASTP Certification, a tracker will be designated as "patch", which allows the certification tools to implement the change immediately. A new release of US Core will be considered if a large number of "patches" are required. Patches for prior US Core versions are managed by the [Cross Group Project patch process] with approved patches on this [HL7 Confluence page].

### US Core Maturity Levels

All US Core conformance and terminology artifacts are assigned a US Core Maturity Level. Implementers can use these levels to assess the level of advancement and stability of an artifact.

#### Profiles, Extensions, and Operations

The US Core Maturity Levels are assigned to US Core profiles, extensions, and operations based on the following criteria:

* **US Core Maturity Level 5**: Level 5 is assigned to US Core profiles and extensions that have been present before the publication of US Core 3.1.1 in 2020, and have been thoroughly reviewed through the HL7 ballot and other processes, and widely implemented in production systems. Many of these artifacts are also identified in regulation and subject to ASTP certification testing. These artifacts are sufficiently stable, and forward compatibility is enforced.
* **US Core Maturity Level 4**: Level 4 is assigned to US Core artifacts meeting all the US Core Maturity Level 5 Criteria, but were published after or significantly changed since US Core 3.1.1. These artifacts are sufficiently stable, and forward compatibility is enforced.
* **US Core Maturity Level 3**: Level 3 is assigned to US Core artifacts meeting all the US Core Maturity Level 4 or US Core Maturity Level 5 Criteria, but not yet widely used in production systems. Forward compatibility is not enforced.
* **US Core Maturity Level 2**: Level 2 is assigned to US Core artifacts that have not been identified in regulation or subject to ASTP certification, and not widely implemented in production systems. Forward compatibility is not enforced
* **US Core Maturity Level 1**: There are no Level 1 artifacts in US Core

#### SearchParameters

**US Core Maturity Level 5** is assigned to US Core SearchParameters. They are sufficiently stable, and forward compatibility is enforced. See the [Search Parameters and Operations] page for how SearchParameters defined in US Core are used.

#### ValueSets, CodeSystems, and CapabilityStatements

**US Core Maturity Level 3** is assigned ValueSets, CodeSystems, and CapabilityStatements. These artifacts are dynamic with each version of US Core. Therefore, forward compatibility is not enforced. For more information on ValueSet and CodeSystem versions, see the [Terminology] page.

### Cross Version Comparisons

The table below summarizes the different profiles and resource types between Argonaut Data Query and major releases of US Core.

| | | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- |
| - | Argonaut MedicationStatement Profile |  |  | 3.1.1* | US Core MedicationStatement Profile not defined in 3.1.1* |
| US Core ADI DocumentReference Profile | - | 8.0.0 |  |  |  |
| US Core AllergyIntolerance Profile | Argonaut AllergyIntolerance Profile | 3.1.1* |  |  |  |
| US Core Authentication Time Extension | - | 8.0.0 | 9.0.0 |  | Has been superseded by the standard Cross-version Extension for R5.DocumentReference.attester for use in FHIR R4 and is deprecated. |
| US Core Average Blood Pressure Profile | - | 7.0.0 |  |  |  |
| US Core BMI Profile | - | 4.0.0 |  |  | Previous to version 4.0.0, referenced the FHIR Vital Signs Profile |
| US Core Blood Pressure Profile | - | 4.0.0 |  |  | Previous to version 4.0.0, referenced the FHIR Vital Signs Profile |
| US Core Body Height Profile | - | 4.0.0 |  |  | Previous to version 4.0.0, referenced the FHIR Vital Signs Profile |
| US Core Body Temperature Profile | - | 4.0.0 |  |  | Previous to version 4.0.0, referenced the FHIR Vital Signs Profile |
| US Core Body Weight Profile | - | 4.0.0 |  |  | Previous to version 4.0.0, referenced the FHIR Vital Signs Profile |
| US Core Care Experience Preference Profile | - | 7.0.0 |  |  |  |
| US Core CarePlan Profile | Argonaut CarePlan Profile | 3.1.1* |  |  | Type changed from CarePlan in DSTU2 to CareTeam in R4 |
| US Core CareTeam Profile | Argonaut CareTeam Profile | 3.1.1* |  |  |  |
| US Core Condition Encounter Diagnosis Profile | - | 5.0.0 |  |  | In version 5.0.0 US Core Condition Profile was split into US Core Condition Encounter Diagnosis Profile and US Core Condition Problems and Health Concerns Profile |
| US Core Condition Problems and Health Concerns Profile | - | 5.0.0 |  |  | In version 5.0.0 US Core Condition Profile was split into US Core Condition Encounter Diagnosis Profile and US Core Condition Problems and Health Concerns Profile |
| US Core Condition Profile | Argonaut Condition Profile | 3.1.1* |  | 5.0.0 | In version 5.0.0 US Core Condition Profile was split into US Core Condition Encounter Diagnosis Profile and US Core Condition Problems and Health Concerns Profile |
| US Core Coverage Profile | - | 6.0.0 |  |  |  |
| US Core Device Profile | Argonaut Device Profile | 3.1.1* |  |  | in version 9.0.0 removed the term "implantable" form the official ( canonical ) URL, name, and title. |
| US Core DiagnosticReport Profile for Laboratory Results Reporting | Argonaut DiagnosticReport Profile | 3.1.1* |  |  |  |
| US Core DiagnosticReport Profile for Report and Note Exchange | - | 3.1.1* |  |  |  |
| US Core DocumentReference Profile | Argonaut DocumentReference Profile | 3.1.1* |  |  |  |
| US Core Encounter Profile | - | 3.1.1* |  |  |  |
| US Core FamilyMemberHistory Profile | - | 9.0.0 |  |  |  |
| US Core Goal Profile | Argonaut Goal Profile | 3.1.1* |  |  |  |
| US Core Head Circumference Profile | - | 4.0.0 |  |  | Previous to version 4.0.0, referenced the FHIR Vital Signs Profile |
| US Core Heart Rate Profile | - | 4.0.0 |  |  | Previous to version 4.0.0, referenced the FHIR Vital Signs Profile |
| US Core Immunization Profile | Argonaut Immunization Profile | 3.1.1* |  |  |  |
| US Core Laboratory Result Observation Profile | Argonaut Observation Results Profile | 3.1.1* |  |  | In Version 6.0.0 derived from US Core Observation Clinical Test Result Profile |
| US Core Location Profile | - | 3.1.1* |  |  |  |
| US Core Medication Profile | Argonaut Medication Profile | 3.1.1* |  |  |  |
| US Core MedicationDispense Profile | - | 6.0.0 |  |  |  |
| US Core MedicationRequest Profile | Argonaut MedicationOrder Profile | 3.1.1* |  |  |  |
| US Core Observation ADI Documentation Profile | - | 8.0.0 |  |  |  |
| US Core Observation Clinical Result Profile | - | 6.0.0 |  |  | Replaces US Core Observation Clinical Test Result Profile and US Core Observation Imaging Result Profile |
| US Core Observation Clinical Test Result Profile | - | 5.0.0 |  | 6.0.0 | Superseded by US Core Observation Clinical Result Profile in version 6.0.0 |
| US Core Observation Imaging Result Profile | - | 5.0.0 |  | 6.0.0 | Superseded by US Core Observation Clinical Result Profile in version 6.0.0 |
| US Core Observation Occupation Profile | - | 6.0.0 |  |  |  |
| US Core Observation Pregnancy Intent Profile | - | 6.0.0 |  |  |  |
| US Core Observation Pregnancy Status Profile | - | 6.0.0 |  |  |  |
| US Core Observation SDOH Assessment Profile | - | 5.0.0 |  | 6.0.0 | Superseded by US Core Observation Screening Assessment Profile in version 6.0.0 |
| US Core Observation Screening Assessment Profile | - | 6.0.0 |  |  | Replaces US Core Observation Survey Profile and US Core Observation SDOH Assessment Profile |
| US Core Observation Sexual Orientation Profile | - | 5.0.0 |  |  | After version 7.0.0 this extension is no longer a USCDI requirement. |
| US Core Observation Social History Profile | - | 5.0.0 |  | 6.0.0 | Superseded by US Core Simple Observation Profile in version 6.0.0 |
| US Core Observation Survey Profile | - | 5.0.0 |  | 6.0.0 | Superseded by US Core Observation Screening Assessment Profile in version 6.0.0 |
| US Core Organization Profile | - | 3.1.1* |  |  |  |
| US Core PMO ServiceRequest Profile | - | 9.0.0 |  |  |  |
| US Core Patient Profile | Argonaut Patient Profile | 3.1.1* |  |  |  |
| US Core Pediatric BMI for Age Observation Profile | - | 3.1.1* |  |  | 3.1.1* based on the FHIR Vital Signs Profile, 4.0.0+ based on the US Core Vital Signs Profile |
| US Core Pediatric Head Occipital Frontal Circumference Percentile Profile | - | 3.1.1* |  |  | 3.1.1* based on the FHIR Vital Signs Profile, 4.0.0+ based on the US Core Vital Signs Profile |
| US Core Pediatric Weight for Height Observation Profile | - | 3.1.1* |  |  | 3.1.1* based on the FHIR Vital Signs Profile, 4.0.0+ based on the US Core Vital Signs Profile |
| US Core Practitioner Profile | - | 3.1.1* |  |  |  |
| US Core PractitionerRole Profile | - | 3.1.1* |  |  |  |
| US Core Procedure Profile | Argonaut Procedure Profile | 3.1.1* |  |  |  |
| US Core Provenance Profile | - | 3.1.1* |  |  |  |
| US Core Pulse Oximetry Profile | - | 3.1.1* |  |  | 3.1.1* based on the FHIR Vital Signs Profile, 4.0.0+ based on the US Core Vital Signs Profile |
| US Core QuestionnaireResponse Profile | - | 5.0.0 |  |  |  |
| US Core RelatedPerson Profile | - | 5.0.0 |  |  |  |
| US Core Respiratory Rate Profile | - | 4.0.0 |  |  | Previous to version 4.0.0, referenced the FHIR Vital Signs Profile |
| US Core ServiceRequest Profile | - | 5.0.0 |  |  |  |
| US Core Simple Observation Profile | - | 6.0.0 |  |  | Replaces US Core Observation Social History Profile |
| US Core Smoking Status Observation Profile | Argonaut Smoking Status Observation Profile | 3.1.1* |  |  |  |
| US Core Specimen Profile | - | 6.0.0 |  |  |  |
| US Core Treatment Intervention Preference Profile | - | 7.0.0 |  |  |  |
| US Core Vital Signs Profile | Argonaut Vital Signs Observation Profile | 4.0.0 |  |  | Previous to version 4.0.0, referenced the FHIR Vital Signs Profile |
| **Extensions** | | | | | |
| US Core Birth Sex Extension | Sex of patient assigned at birth | 3.1.1* |  |  | After version 6.0.0 this extension is no longer a USCDI requirement. |
| US Core Direct email Extension | - | 3.1.1* |  |  |  |
| US Core Ethnicity Extension | Argonaut ethnicity Extension | 3.1.1* |  |  |  |
| US Core Extension Questionnaire URI | - | 5.0.0 |  |  |  |
| US Core FamilyMemberHistory Recorder Extension | - | 9.0.0 |  |  |  |
| US Core Gender Identity Extension | - | 5.0.0 | 8.0.0 |  | After version 7.0.0 this extension is no longer a USCDI requirement and has been deprecated. |
| US Core Individual Sex Extension | - | 8.0.1 |  |  | Supersedes the US Core Sex Extension. |
| US Core Interpreter Needed Extension | - | 8.0.0 |  |  |  |
| US Core Jurisdiction Extension | - | 6.0.0 |  |  |  |
| US Core Medication Adherence Extension | - | 7.0.0 |  |  |  |
| US Core Race Extension | Argonaut Race Extension | 3.1.1* |  |  |  |
| US Core Sex Extension | - | 6.1.0 | 8.0.1 |  | Superseded in version 8.0.1 by the US Core Individual Sex Extension. |
| US Core Tribal Affiliation Extension | - | 6.0.0 |  |  |  |
| US Core USCDI Requirement Extension | - | 6.0.0 |  |  | This extension is only used on US Core Profile StructureDefinition elements |

*3.1.1 or prior version of US Core 

Detailed comparisons between the US Core artifacts in this current 0.1.0 version of US Core and each previous major release are provided in the links below:

* [Comparison with version 8.0.1](comparison-v8.0.1/index.md)
* [Comparison with version 7.0.0](comparison-v7.0.0/index.md)
* [Comparison with version 6.1.0](comparison-v6.1.0/index.md)
* [Comparison with version 5.0.1](comparison-v5.0.1/index.md)
* [Comparison with version 4.0.0](comparison-v4.0.0/index.md)
* [Comparison with version 3.1.1](comparison-v3.1.1/index.md)
* [(Partial) Comparison with Argonaut Data Query IG](comparison-argo/index.md)

### Endpoint Discoverability

A Server may support Version DSTU2 and Argonaut Data Query or FHIR R4 and US Core ver 3.1.1+ or both. A Server may make explicit which version of Argo/US Core is on their FHIR endpoint (e.g., "DSTU2" or "R4" path component or separate files based on version). However, the best practice is to inspect the [endpoint metadata](http://hl7.org/fhir/R4/http.html) on each endpoint to discover the information about a Server's capabilities, including the FHIR version and the US Core Profile version that is supported:

`GET [base]/metadata{?mode=[mode]} {&_format=[mime-type]}`

### No Guarantee that Resource IDs are Preserved

Servers**SHOULD**maintain a stable common identifier for a resource across versions. When the FHIR resource ID or business identifier of the underlying clinical data is not maintained across FHIR versions, the Client**SHALL**use an alternative method to avoid duplication, such as the guidance provided in the[Interoperable Digital Identity and Patient Matching](https://hl7.org/fhir/us/identity-matching/)Implementation Guide.

### Expectation that Data is Preserved Between Versions 

In an upgraded R4 endpoint, any data in FHIR DSTU2 **SHOULD** be in FHIR R4. However, not all data in R4 may be available in DSTU2 because some profiles and data classes, like Clinical Notes and pediatric observations, are not part of DSTU2.

* The FHIR RESTful resource types supported in a DSTU2 implementation **SHOULD** be supported in a R4 implementation 
* Exceptions 
* MedicationStatement may be deprecated, and the data **SHOULD** be mapped to MedicationRequest. 
* See the guidance on the [Medication List] page for how to access a patient's medications
 
* Care teams as represented by CarePlan in DSTU2 **SHOULD** be replaced by and the data mapped to CareTeam in R4
 
 
* Servers **SHOULD** make available the same information in DSTU2 and R4 where the more recent standard allows. (e.g., patient Rhonda Jones is available on both) 
* Exceptions 
* MedicationStatement data mapped to MedicationRequest
* care teams, as represented by CarePlan, **SHOULD** be mapped to CareTeam in R4
 
 
* Data **SHOULD** be maintained between versions (i.e., not be degraded).
* When updating between versions, Clients **SHOULD** consider the impact of any changes to data visualization on the usability for the end user and the maintenance of data integrity.

### Authorization Across Versions

* To allow clients to use a single authorization token when accessing resources from multiple version-specific endpoints, production systems **SHOULD** use the same base authorization endpoint across versions.
* The more recent version endpoints will have additional/changed resource types and thus added scopes. For example, US Core may add a DeviceAssociation Profile when updating from FHIR R4 to FHIR R6.

