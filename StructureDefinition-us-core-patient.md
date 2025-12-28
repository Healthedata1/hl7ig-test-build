# US Core Patient Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Patient Profile**

## Resource Profile: US Core Patient Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCorePatientProfile |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core Patient Profile inherits from the FHIR[Patient](https://hl7.org/fhir/R4/patient.html)resource; refer to it for scope and usage definitions. This profile meets the requirements of the[U.S. Core Data for Interoperability (USCDI)](https://www.healthit.gov/isp/united-states-core-data-interoperability-uscdi)**Patient Demographics/Information**Data Class. It sets minimum expectations for the Patient resource to record, search, and fetch basic demographics and other administrative information about an individual patient. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. 

**Usages:**

* Refer to this Profile: [US Core DiagnosticReport Profile for Laboratory Results Reporting](StructureDefinition-us-core-diagnosticreport-lab.md), [US Core ADI DocumentReference Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-adi-documentreference.html), [US Core Average Blood Pressure Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-average-blood-pressure.html), [US Core Care Experience Preference Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-care-experience-preference.html)...Show 41 more,[US Core Coverage Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-coverage.html),[US Core Device Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-device.html),[US Core FamilyMemberHistory Recorder Extension](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-familymemberhistory-recorder.html),[US Core FamilyMemberHistory Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-familymemberhistory.html),[US Core MedicationDispense Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-medicationdispense.html),[US Core Observation ADI Documentation Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-adi-documentation.html),[US Core Observation Clinical Result Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-clinical-result.html),[US Core Observation Occupation Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-occupation.html),[US Core Observation Pregnancy Intent Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-pregnancyintent.html),[US Core Observation Pregnancy Status Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-pregnancystatus.html),[US Core Observation Screening Assessment Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-screening-assessment.html),[US Core PMO ServiceRequest Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-pmo-servicerequest.html),[US Core Simple Observation Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-simple-observation.html),[US Core Specimen Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-specimen.html),[US Core Treatment Intervention Preference Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-treatment-intervention-preference.html),[US Core AllergyIntolerance Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-allergyintolerance.html),[US Core CarePlan Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-careplan.html),[US Core CareTeam Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-careteam.html),[US Core Condition Encounter Diagnosis Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-condition-encounter-diagnosis.html),[US Core Condition Problems and Health Concerns Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-condition-problems-health-concerns.html),[US Core DiagnosticReport Profile for Laboratory Results Reporting](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-diagnosticreport-lab.html),[US Core DiagnosticReport Profile for Report and Note Exchange](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-diagnosticreport-note.html),[US Core DocumentReference Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-documentreference.html),[US Core Encounter Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-encounter.html),[US Core Goal Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-goal.html),[US Core Immunization Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-immunization.html),[US Core Implantable Device Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-implantable-device.html),[US Core MedicationRequest Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-medicationrequest.html),[US Core Observation Clinical Test Result Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-observation-clinical-test.html),[US Core Observation Imaging Result Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-observation-imaging.html),[US Core Laboratory Result Observation Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-observation-lab.html),[US Core Observation Sexual Orientation Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-observation-sexual-orientation.html),[US Core Observation Social History Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-observation-social-history.html),[US Core Observation Survey Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-observation-survey.html),[US Core Procedure Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-procedure.html),[US Core Provenance Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-provenance.html),[US Core QuestionnaireResponse Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-questionnaireresponse.html),[US Core RelatedPerson Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-relatedperson.html),[US Core ServiceRequest Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-servicerequest.html),[US Core Smoking Status Observation Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-smokingstatus.html)and[US Core Vital Signs Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-vital-signs.html)
* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md), [US Core Server CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-server-liquid.md), [US Core Client CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-client.html) and [US Core Server CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-server.html)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-patient)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-patient.csv), [Excel](StructureDefinition-us-core-patient.xlsx), [Schematron](StructureDefinition-us-core-patient.sch) 

### Notes:

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-patient.html

type = Patient

title = US Core Patient Profile

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support both read Patient by`id`**AND**Patient search using the[_id](SearchParameter-us-core-patient-id.md)search parameter:`GET [base]/Patient?_id=[id]' or 'GET [base]/Patient/[id]`Example:
1. GET [base]/Patient/1032702
1. GET [base]/Patient?_id=1032702
**Implementation Notes**: Fetches a resource or a search Bundle containing a US Core Patient Profile resources matching the id (see [Parameters for all resources]).

1. **SHALL**support searching a patient by an identifier such as an MPI using the[identifier](SearchParameter-us-core-patient-identifier.md)search parameter:`GET [base]/Patient?identifier={system|}[search_code]`Example:
1. GET [base]/Patient?identifier=http://hospital.smarthealthit.org|1032702
**Implementation Notes**: Fetches a bundle containing any US Core Patient Profile resources matching the identifier, in other words, the [logical reference] of the resource ([how to search by token]).

1. **SHALL**support searching for a patient by a server defined search that matches any of the string fields in the HumanName, including family, given, prefix, suffix, and/or text using the[name](SearchParameter-us-core-patient-name.md)search parameter:`GET [base]/Patient?name=[name]`Example:
1. GET [base]/Patient?name=Shaw
**Implementation Notes**: Fetches a bundle of all US Core Patient Profile resources matching the name ([how to search by string]).

1. **SHALL**support searching using the combination of[birthdate](SearchParameter-us-core-patient-birthdate.md)and[name](SearchParameter-us-core-patient-name.md)search parameters:`GET [base]/Patient?birthdate=[dateTime]&name=[name]`Example:
1. GET [base]/Patient?name=Shaw&birthdate=2007-03-20
**Implementation Notes**: Fetches a bundle of all resources matching the specified ([how to search by date] and ([how to search by string]).

#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported

1. **SHOULD**support searching using the combination of[birthdate](SearchParameter-us-core-patient-birthdate.md)and[family](SearchParameter-us-core-patient-family.md)search parameters:`GET [base]/Patient?birthdate=[dateTime]&family=[family]`Example:
1. GET [base]/Patient?family=Shaw&birthdate=2007-03-20
**Implementation Notes**: Fetches a bundle of all resources matching the specified ([how to search by date] and ([how to search by string]).

1. **SHOULD**support searching using the combination of[death-date](SearchParameter-us-core-patient-death-date.md)and[family](SearchParameter-us-core-patient-family.md)search parameters:`GET [base]/Patient?death-date=[dateTime]&family=[family]`Example:
1. GET [base]/Patient?family=Shaw&death-date=2022-07-22
**Implementation Notes**: Fetches a bundle of all resources matching the specified ([how to search by date] and ([how to search by string]).



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-patient",
  "extension" : [
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
      "valueInteger" : 5
    },
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
      "valueCode" : "trial-use",
      "_valueCode" : {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-conformance-derivedFrom",
            "valueCanonical" : "http://hl7.org/fhir/us/healthedata1-sandbox/ImplementationGuide/hl7.fhir.us.healthedata1-sandbox"
          }
        ]
      }
    }
  ],
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient",
  "version" : "0.1.0",
  "name" : "USCorePatientProfile",
  "title" : "US Core Patient Profile",
  "status" : "active",
  "experimental" : false,
  "date" : "2025-04-22",
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
  "description" : "The US Core Patient Profile inherits from the FHIR [Patient](https://hl7.org/fhir/R4/patient.html) resource; refer to it for scope and usage definitions. This profile meets the requirements of the [U.S. Core Data for Interoperability (USCDI)](https://www.healthit.gov/isp/united-states-core-data-interoperability-uscdi) *Patient Demographics/Information* Data Class. It sets minimum expectations for the Patient resource to record, search, and fetch basic demographics and other administrative information about an individual patient. It specifies which core elements, extensions, vocabularies, and value sets **SHALL** be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption.",
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
  "fhirVersion" : "4.0.1",
  "mapping" : [
    {
      "identity" : "rim",
      "uri" : "http://hl7.org/v3",
      "name" : "RIM Mapping"
    },
    {
      "identity" : "cda",
      "uri" : "http://hl7.org/v3/cda",
      "name" : "CDA (R2)"
    },
    {
      "identity" : "w5",
      "uri" : "http://hl7.org/fhir/fivews",
      "name" : "FiveWs Pattern Mapping"
    },
    {
      "identity" : "v2",
      "uri" : "http://hl7.org/v2",
      "name" : "HL7 v2 Mapping"
    },
    {
      "identity" : "loinc",
      "uri" : "http://loinc.org",
      "name" : "LOINC code for the element"
    }
  ],
  "kind" : "resource",
  "abstract" : false,
  "type" : "Patient",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/Patient",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "Patient",
        "path" : "Patient",
        "mustSupport" : false,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Patient"
          }
        ]
      },
      {
        "id" : "Patient.extension:race",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Patient.extension",
        "sliceName" : "race",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: US Core Race Extension. (multiple races are supported in the extension)",
        "min" : 0,
        "max" : "1",
        "type" : [
          {
            "code" : "Extension",
            "profile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-race"
            ]
          }
        ],
        "mustSupport" : false,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Patient.extension"
          }
        ]
      },
      {
        "id" : "Patient.extension:ethnicity",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Patient.extension",
        "sliceName" : "ethnicity",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: US Core ethnicity Extension (multiple ethnicities are supported in the extension)",
        "min" : 0,
        "max" : "1",
        "type" : [
          {
            "code" : "Extension",
            "profile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-ethnicity"
            ]
          }
        ],
        "mustSupport" : false,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Patient.extension"
          }
        ]
      },
      {
        "id" : "Patient.extension:tribalAffiliation",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Patient.extension",
        "sliceName" : "tribalAffiliation",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: Tribal Affiliation Extension",
        "min" : 0,
        "max" : "*",
        "type" : [
          {
            "code" : "Extension",
            "profile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-tribal-affiliation"
            ]
          }
        ],
        "mustSupport" : false
      },
      {
        "id" : "Patient.extension:sex",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Patient.extension",
        "sliceName" : "sex",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: Sex Extension",
        "min" : 0,
        "max" : "1",
        "type" : [
          {
            "code" : "Extension",
            "profile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-individual-sex"
            ]
          }
        ],
        "mustSupport" : false
      },
      {
        "id" : "Patient.extension:interpreterRequired",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Patient.extension",
        "sliceName" : "interpreterRequired",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: Whether the patient needs an interpreter",
        "min" : 0,
        "max" : "1",
        "type" : [
          {
            "code" : "Extension",
            "profile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-interpreter-needed"
            ]
          }
        ],
        "mustSupport" : false
      },
      {
        "id" : "Patient.identifier",
        "path" : "Patient.identifier",
        "min" : 1,
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Patient.identifier"
          }
        ]
      },
      {
        "id" : "Patient.identifier.system",
        "path" : "Patient.identifier.system",
        "min" : 1,
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Patient.identifier.system"
          }
        ]
      },
      {
        "id" : "Patient.identifier.value",
        "path" : "Patient.identifier.value",
        "short" : "The value that is unique within the system.",
        "min" : 1,
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Patient.identifier.value"
          }
        ]
      },
      {
        "id" : "Patient.name",
        "path" : "Patient.name",
        "min" : 1,
        "constraint" : [
          {
            "key" : "us-core-6",
            "severity" : "error",
            "human" : "At least name.given and/or name.family are present or, if neither is available, the Data Absent Reason Extension is present.",
            "expression" : "(family.exists() or given.exists()) xor extension.where(url='http://hl7.org/fhir/StructureDefinition/data-absent-reason').exists()",
            "xpath" : "(/f:extension/@url='http://hl7.org/fhir/StructureDefinition/data-absent-reason' and not(/f:family or /f:given)) or (not(/f:extension/@url='http://hl7.org/fhir/StructureDefinition/data-absent-reason') and (/f:family or /f:given))"
          }
        ],
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Patient.name"
          }
        ]
      },
      {
        "id" : "Patient.name.use",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Patient.name.use",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: usual | official | temp | nickname | anonymous | old | maiden",
        "comment" : "The [United States Core Data for Interoperability (USCDI)](https://www.healthit.gov/isp/united-states-core-data-interoperability-uscdi) Patient Demographics/Information Data Element, *Name to Use*, is represented by the code \"usual\", and, *Previous Name*, by the code \"old\"."
      },
      {
        "id" : "Patient.name.family",
        "path" : "Patient.name.family",
        "condition" : ["us-core-6"],
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Patient.name.family"
          }
        ]
      },
      {
        "id" : "Patient.name.given",
        "path" : "Patient.name.given",
        "condition" : ["us-core-6"],
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Patient.name.given"
          }
        ]
      },
      {
        "id" : "Patient.name.suffix",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Patient.name.suffix",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: Parts that come after the name",
        "mustSupport" : false,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "NA"
          }
        ]
      },
      {
        "id" : "Patient.name.period",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Patient.name.period",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: Time period when name was/is in use",
        "mustSupport" : false,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "NA"
          }
        ]
      },
      {
        "id" : "Patient.telecom",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Patient.telecom",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: A contact detail for the individual",
        "mustSupport" : false,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "NA"
          }
        ]
      },
      {
        "id" : "Patient.telecom.system",
        "path" : "Patient.telecom.system",
        "min" : 1,
        "mustSupport" : true,
        "binding" : {
          "strength" : "required",
          "description" : "Telecommunications form for contact point.",
          "valueSet" : "http://hl7.org/fhir/ValueSet/contact-point-system"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "NA"
          }
        ]
      },
      {
        "id" : "Patient.telecom.value",
        "path" : "Patient.telecom.value",
        "min" : 1,
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "NA"
          }
        ]
      },
      {
        "id" : "Patient.telecom.use",
        "path" : "Patient.telecom.use",
        "mustSupport" : true,
        "binding" : {
          "strength" : "required",
          "valueSet" : "http://hl7.org/fhir/ValueSet/contact-point-use"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "NA"
          }
        ]
      },
      {
        "id" : "Patient.birthDate",
        "path" : "Patient.birthDate",
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Patient.birthDate"
          }
        ]
      },
      {
        "id" : "Patient.deceased[x]",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Patient.deceased[x]",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: Indicates if the individual is deceased or not"
      },
      {
        "id" : "Patient.address",
        "path" : "Patient.address",
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Patient.birthDate"
          }
        ]
      },
      {
        "id" : "Patient.address.use",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Patient.address.use",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: home | work | temp | old | billing - purpose of this address"
      },
      {
        "id" : "Patient.address.line",
        "path" : "Patient.address.line",
        "example" : [
          {
            "label" : "US Core",
            "valueString" : "49 MEADOW ST"
          }
        ],
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "NA"
          }
        ]
      },
      {
        "id" : "Patient.address.city",
        "path" : "Patient.address.city",
        "example" : [
          {
            "label" : "US Core",
            "valueString" : "EVERYTOWN"
          }
        ],
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "NA"
          }
        ]
      },
      {
        "id" : "Patient.address.state",
        "path" : "Patient.address.state",
        "example" : [
          {
            "label" : "US Core",
            "valueString" : "OK"
          }
        ],
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "description" : "Two Letter USPS alphabetic codes.",
          "valueSet" : "http://terminology.hl7.org/ValueSet/USPS-State"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "NA"
          }
        ]
      },
      {
        "id" : "Patient.address.postalCode",
        "path" : "Patient.address.postalCode",
        "short" : "US Zip Codes",
        "alias" : ["Zip Code"],
        "example" : [
          {
            "label" : "US Core",
            "valueString" : "74047"
          }
        ],
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "NA"
          }
        ]
      },
      {
        "id" : "Patient.address.period",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Patient.address.period",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: Time period when address was/is in use",
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "NA"
          }
        ]
      },
      {
        "id" : "Patient.communication",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Patient.communication",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: A language which may be used to communicate with the patient about his or her health",
        "mustSupport" : false,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Patient.communication"
          }
        ]
      },
      {
        "id" : "Patient.communication.language",
        "path" : "Patient.communication.language",
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "valueSet" : "http://terminology.hl7.org/ValueSet/Languages"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Patient.communication.language"
          }
        ]
      }
    ]
  }
}

```
