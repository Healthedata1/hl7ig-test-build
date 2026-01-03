# US Core Encounter Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Encounter Profile**

## Resource Profile: US Core Encounter Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-encounter | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreEncounterProfile |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core Encounter Profile inherits from the FHIR[Encounter](https://hl7.org/fhir/R4/encounter.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the Encounter resource to record, search, and fetch basic encounter information for an individual patient. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. 

**Usages:**

* Refer to this Profile: [US Core DocumentReference Profile](StructureDefinition-us-core-documentreference.md), [US Core Immunization Profile](StructureDefinition-us-core-immunization.md), [US Core MedicationRequest Profile](StructureDefinition-us-core-medicationrequest.md), [US Core MedicationDispense Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-medicationdispense.html)...Show 6 more,[US Core Observation Clinical Result Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-clinical-result.html),[US Core PMO ServiceRequest Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-pmo-servicerequest.html),[US Core Condition Encounter Diagnosis Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-condition-encounter-diagnosis.html),[US Core DiagnosticReport Profile for Report and Note Exchange](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-diagnosticreport-note.html),[US Core DocumentReference Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-documentreference.html)and[US Core MedicationRequest Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-medicationrequest.html)
* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md) and [US Core Server CapabilityStatement](CapabilityStatement-us-core-server.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-encounter)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-encounter.csv), [Excel](StructureDefinition-us-core-encounter.xlsx), [Schematron](StructureDefinition-us-core-encounter.sch) 

### Notes:

-------

**Quick Start** 

-------

Below is an overview of the required Server RESTful FHIR interactions for this profile - for example, search and read operations - when supporting the US Core interactions to access this profile's information (Profile Support + Interaction Support). Note that systems that support only US Core Profiles (Profile Only Support) are not required to support these interactions. See the [US Core Server CapabilityStatement] for a complete list of supported RESTful interactions for this IG.

* See the [Scopes Format](scopes.md#scopes-format) section for a description of the SMART scopes syntax.
* See the [Search Syntax](general-guidance.md#search-syntax) section for a description of the US Core search syntax.
* See the [General Requirements] section for additional rules and expectations when a Server requires status parameters.
* See the [General Guidance] section for additional guidance on searching for multiple patients.

#### US Core Scopes

Servers providing access to encounter data **SHALL** support these [US Core SMART Scopes]:

* [resource level scopes]: `<patient|user|system>/Encounter.rs`

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-encounter.html

type = Encounter

title = US Core Encounter Profile

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support both read Encounter by`id`**AND**Encounter search using the[_id](SearchParameter-us-core-encounter-id.md)search parameter`GET [base]/Encounter?_id=[id]' or 'GET [base]/Encounter/[id]`Examples:
> 
1. GET [base]/Encounter/12354
1. GET [base]/Encounter?_id=12354

**Implementation Notes**: Fetches a single US Core Encounter Profile or a search Bundle containing an US Core Encounter Profile resource matching the id (see[Parameters for all resources](http://hl7.org/fhir/R4/search.html#all)).
1. **SHALL**support searching for all encounters for a patient using the[patient](SearchParameter-us-core-encounter-patient.md)search parameter`GET [base]/Encounter?patient={Patient/}[id]`Example:
> 
1. GET [base]/Encounter?patient=Patient/1137192

**Implementation Notes**: Fetches a bundle of all US Core Encounter Profile resources for the specified patient ( see[how to search by reference](foo.md)).
1. **SHALL**support searching for all encounters for a patient by date using the combination of the[patient](SearchParameter-us-core-encounter-patient.md)and[date](SearchParameter-us-core-encounter-date.md)search parameters
* Including optional support for **AND** search on `date` (e.g.`date=[date]&date=[date]&...`)
* Including support for these `date` comparators: "gt", "lt", "ge", "le"
`GET [base]/Encounter?patient={Patient/}[id]&date={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
> 
1. GET [base]/Encounter?patient=Patient/1137192&date=ge2019-01-01T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Encounter Profile resources matching the specified date and patient ( see[how to search by reference](foo.md)and[how to search by date](#.md)).

#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported

1. **SHOULD**support searching for an encounter by an identifier using the[identifier](SearchParameter-us-core-encounter-identifier.md)search parameter`GET [base]/Encounter?identifier={system|}[search_code]`Example:
> 
1. GET [base]/Encounter?identifier=http://hospital.smarthealthit.org|1032702

**Implementation Notes**: Fetches a bundle containing any US Core Encounter Profile resources matching the identifier ( see[how to search by token](#.md)).
1. **SHOULD**support searching for all encounter for a patient by encounter class using the combination of the[patient](SearchParameter-us-core-encounter-patient.md)and[class](SearchParameter-us-core-encounter-class.md)search parameters`GET [base]/Encounter?patient={Patient/}[id]&class={system|}[search_code]`Example:
> 
1. GET [base]/Encounter?patient=Patient/1137192&class= http://terminology.hl7.org/CodeSystem/v3-ActCode code|AMB

**Implementation Notes**: Fetches a bundle of all US Core Encounter Profile resources matching the specified class and patient ( see[how to search by reference](foo.md)and[how to search by token](#.md)).
1. **SHOULD**support searching for all encounter for a patient by encounter type using the combination of the[patient](SearchParameter-us-core-encounter-patient.md)and[type](SearchParameter-us-core-encounter-type.md)search parameters`GET [base]/Encounter?patient={Patient/}[id]&type={system|}[search_code]`Example:
> 
1. GET [base]/Encounter?patient=Patient/1137192&type=http://www.ama-assn.org/go/cpt code|99201

**Implementation Notes**: Fetches a bundle of all US Core Encounter Profile resources matching the specified patient and type ( see[how to search by reference](foo.md)and[how to search by token](#.md)).
1. **SHOULD**support searching for all encounter for a patient by encounter type using the combination of the[patient](SearchParameter-us-core-encounter-patient.md)and[location](SearchParameter-us-core-encounter-location.md)search parameters`GET [base]/Encounter?patient={Patient/}[id]&location={Type/}[id]`Example:
> 
1. GET [base]/Encounter?patient=Patient/1137192&location=Location/hospital

**Implementation Notes**: Fetches a bundle of all US Core Encounter Profile resources matching the specified patient and location ( see[how to search by reference](foo.md)).
1. **SHOULD**support searching using the combination of the[patient](SearchParameter-us-core-encounter-patient.md)and[_lastUpdated](SearchParameter-us-core-encounter-lastupdated.md)search parameters
* Including optional support for **AND** search on `_lastUpdated` (e.g.`_lastUpdated=[date]&_lastUpdated=[date]&...`)
* Including support for these `_lastUpdated` comparators: "gt", "lt", "ge", "le"
`GET [base]/Encounter?patient={Patient/}[id]&_lastUpdated=[dateTime]`Example:
> 
1. GET [base]/Encounter?patient=Patient/1137192&_lastUpdated=ge2024-01-01T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Encounter Profile resources for the specified patient and _lastUpdated. See the US Core General Guidance page for [Searching Using lastUpdated]. ( see[how to search by reference](foo.md)and[how to search by date](#.md)).
1. **SHOULD**support searching for all encounters for a patient by status (for example, all finished encounters) using the combination of the[patient](SearchParameter-us-core-encounter-patient.md)and[status](SearchParameter-us-core-encounter-status.md)search parameters`GET [base]/Encounter?patient={Patient/}[id]&status={system|}[search_code]`Example:
> 
1. GET [base]/Encounter?patient=Patient/1137192&status=finished

**Implementation Notes**: Fetches a bundle of all US Core Encounter Profile resources matching the specified patient and status ( see[how to search by reference](foo.md)and[how to search by token](#.md)).
1. **SHOULD**support searching for all encounter for a patient by status (for example, all finished encounters) using the combination of the[patient](SearchParameter-us-core-encounter-patient.md)and[discharge-disposition](SearchParameter-us-core-encounter-discharge-disposition.md)search parameters`GET [base]/Encounter?patient={Patient/}[id]&discharge-disposition={system|}[search_code]`Example:
> 
1. GET [base]/Encounter?patient=Patient/1137192&discharge-disposition=01

**Implementation Notes**: Fetches a bundle of all US Core Encounter Profile resources matching the specified patient and discharge-disposition ( see[how to search by reference](foo.md)and[how to search by token](#.md)).



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-encounter",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-encounter",
  "version" : "0.1.0",
  "name" : "USCoreEncounterProfile",
  "title" : "US Core Encounter Profile",
  "status" : "active",
  "experimental" : false,
  "date" : "2023-10-17",
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
  "description" : "The US Core Encounter Profile inherits from the FHIR [Encounter](https://hl7.org/fhir/R4/encounter.html) resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the Encounter resource to record, search, and fetch basic encounter information for an individual patient. It specifies which core elements, extensions, vocabularies, and value sets **SHALL** be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption.",
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
      "identity" : "workflow",
      "uri" : "http://hl7.org/fhir/workflow",
      "name" : "Workflow Pattern"
    },
    {
      "identity" : "rim",
      "uri" : "http://hl7.org/v3",
      "name" : "RIM Mapping"
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
    }
  ],
  "kind" : "resource",
  "abstract" : false,
  "type" : "Encounter",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/Encounter",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "Encounter",
        "path" : "Encounter",
        "mustSupport" : false
      },
      {
        "id" : "Encounter.meta",
        "path" : "Encounter.meta",
        "mustSupport" : true
      },
      {
        "id" : "Encounter.meta.lastUpdated",
        "path" : "Encounter.meta.lastUpdated",
        "short" : "When the resource last changed",
        "mustSupport" : true
      },
      {
        "id" : "Encounter.extension:interpreterRequired",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Encounter.extension",
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
        "id" : "Encounter.identifier",
        "path" : "Encounter.identifier",
        "mustSupport" : true
      },
      {
        "id" : "Encounter.identifier.system",
        "path" : "Encounter.identifier.system",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "uri"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Encounter.identifier.value",
        "path" : "Encounter.identifier.value",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "string"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Encounter.status",
        "path" : "Encounter.status",
        "mustSupport" : true
      },
      {
        "id" : "Encounter.class",
        "path" : "Encounter.class",
        "mustSupport" : true
      },
      {
        "id" : "Encounter.type",
        "path" : "Encounter.type",
        "min" : 1,
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "description" : "Valueset to describe the Encounter Type",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.113762.1.4.1267.23"
        }
      },
      {
        "id" : "Encounter.subject",
        "path" : "Encounter.subject",
        "min" : 1,
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient",
              "http://hl7.org/fhir/StructureDefinition/Group"
            ],
            "_targetProfile" : [
              {
                "extension" : [
                  {
                    "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                    "valueBoolean" : true
                  }
                ]
              },
              {
                "extension" : [
                  {
                    "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                    "valueBoolean" : false
                  }
                ]
              }
            ]
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Encounter.participant",
        "path" : "Encounter.participant",
        "mustSupport" : true
      },
      {
        "id" : "Encounter.participant.type",
        "path" : "Encounter.participant.type",
        "mustSupport" : true
      },
      {
        "id" : "Encounter.participant.period",
        "path" : "Encounter.participant.period",
        "mustSupport" : true
      },
      {
        "id" : "Encounter.participant.individual",
        "path" : "Encounter.participant.individual",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitioner",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitionerrole",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-relatedperson"
            ],
            "_targetProfile" : [
              {
                "extension" : [
                  {
                    "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                    "valueBoolean" : true
                  }
                ]
              },
              {
                "extension" : [
                  {
                    "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                    "valueBoolean" : false
                  }
                ]
              },
              {
                "extension" : [
                  {
                    "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                    "valueBoolean" : false
                  }
                ]
              }
            ]
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Encounter.period",
        "path" : "Encounter.period",
        "mustSupport" : true
      },
      {
        "id" : "Encounter.reasonCode",
        "path" : "Encounter.reasonCode",
        "mustSupport" : true
      },
      {
        "id" : "Encounter.reasonReference",
        "path" : "Encounter.reasonReference",
        "max" : "*",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-condition-problems-health-concerns",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-condition-encounter-diagnosis",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-procedure",
              "http://hl7.org/fhir/StructureDefinition/Observation",
              "http://hl7.org/fhir/StructureDefinition/ImmunizationRecommendation"
            ],
            "_targetProfile" : [
              {
                "extension" : [
                  {
                    "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                    "valueBoolean" : true
                  }
                ]
              },
              {
                "extension" : [
                  {
                    "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                    "valueBoolean" : true
                  }
                ]
              },
              {
                "extension" : [
                  {
                    "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                    "valueBoolean" : false
                  }
                ]
              },
              {
                "extension" : [
                  {
                    "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                    "valueBoolean" : false
                  }
                ]
              },
              {
                "extension" : [
                  {
                    "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                    "valueBoolean" : false
                  }
                ]
              }
            ]
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Encounter.hospitalization",
        "path" : "Encounter.hospitalization",
        "mustSupport" : true
      },
      {
        "id" : "Encounter.hospitalization.dischargeDisposition",
        "path" : "Encounter.hospitalization.dischargeDisposition",
        "mustSupport" : true,
        "binding" : {
          "strength" : "preferred",
          "description" : "[National Uniform Billing Committee](http://www.nubc.org/), manual UB-04, UB form locator 17",
          "valueSet" : "http://terminology.hl7.org/ValueSet/v3-USEncounterDischargeDisposition"
        }
      },
      {
        "id" : "Encounter.location",
        "path" : "Encounter.location",
        "mustSupport" : true
      },
      {
        "id" : "Encounter.location.location",
        "path" : "Encounter.location.location",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-location"
            ]
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Encounter.serviceProvider",
        "path" : "Encounter.serviceProvider",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization"
            ]
          }
        ],
        "mustSupport" : true
      }
    ]
  }
}

```
