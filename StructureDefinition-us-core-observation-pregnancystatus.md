# US Core Observation Pregnancy Status Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Observation Pregnancy Status Profile**

## Resource Profile: US Core Observation Pregnancy Status Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-pregnancystatus | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 4 | *Computable Name*:USCoreObservationPregnancyStatusProfile |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core Pregnancy Status Observation Profile inherits from the FHIR[Observation](https://hl7.org/fhir/R4/observation.html)resource; refer to it for scope and usage definitions. This profile meets the requirements of the U.S. Core Data for Interoperability (USCDI)**Pregnancy Status**Data Element. It sets minimum expectations for the Observation resource to record, search, and fetch the patient's state or condition of being pregnant. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. 

**Usages:**

* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md) and [US Core Server CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-server-liquid.md)
* This Profile is not used by any profiles in this Implementation Guide

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-observation-pregnancystatus)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-observation-pregnancystatus.csv), [Excel](StructureDefinition-us-core-observation-pregnancystatus.xlsx), [Schematron](StructureDefinition-us-core-observation-pregnancystatus.sch) 

### Notes:

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-observation-pregnancystatus.html

type = Observation

title = US Core Observation Pregnancy Status Profile

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support searching for all Observations using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)search parameters:`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=http://terminology.hl7.org/CodeSystem/observation-category|social-history

**Implementation Notes**: Fetches a bundle of all US Core Observation Pregnancy Status Profile resources for the specified patient and a category code = "social-history" ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHALL**support searching for all Observations by code using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[code](SearchParameter-us-core-observation-code.md)search parameters:
* Including optional support **OR** search on `code` (e.g.`code={system|}[code],{system|}[code],...`)
`GET [base]/Observation?patient={Patient/}[id]&code={system|}[search_code]{,{system|}[code],...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&code=http://loinc.org|82810-3

**Implementation Notes**: Fetches a bundle of all US Core Observation Pregnancy Status Profile resources for the specified patient and observation code(s). SHOULD support search by multiple codes. The US Core Observation Pregnancy Status Profile "code" parameter searches only`.code`and not`component.code`. ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHALL**support searching for all Observations by date (for example, results after 2018) using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)and[date](SearchParameter-us-core-observation-date.md)search parameters:
* Including optional support for **AND** search on `date` (e.g.`date=[date]&date=[date]&...`)
* Including support for these `date` comparators: "gt", "lt", "ge", "le"
`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]&date={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=http://terminology.hl7.org/CodeSystem/observation-category|social-history&date=ge2018-03-14T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Observation Pregnancy Status Profile resources for the specified patient and date and a category code = "social-history" ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).

#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported

1. **SHOULD**support searching for all Observations for a patient for a given status (for example all observations marked as final) using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)and[status](SearchParameter-us-core-observation-status.md)search parameters:
* Including support **OR** search on `status` (e.g.`status={system|}[code],{system|}[code],...`)
`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]&status={system|}[search_code]{,{system|}[code],...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=http://terminology.hl7.org/CodeSystem/observation-category|social-history&status=final

**Implementation Notes**: Fetches a bundle of all US Core Observation Pregnancy Status Profile resources for the specified patient and category = "social-history" and status ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHOULD**support searching using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)and[_lastUpdated](SearchParameter-us-core-observation-lastupdated.md)search parameters:
* Including optional support for **AND** search on `_lastUpdated` (e.g.`_lastUpdated=[date]&_lastUpdated=[date]&...`)
* Including support for these `_lastUpdated` comparators: "gt", "lt", "ge", "le"
`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]&_lastUpdated=[dateTime]`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=http://terminology.hl7.org/CodeSystem/observation-category|social-history&_lastUpdated=ge2024-01-01T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Observation Pregnancy Status Profile resources for the specified patient and category code = "social-history" and _lastUpdated. See the US Core General Guidance page for [Searching Using lastUpdated]. ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).

1. **SHOULD**support searching Observations by code and date using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[code](SearchParameter-us-core-observation-code.md)and[date](SearchParameter-us-core-observation-date.md)search parameters:
* Including optional support **OR** search on `code` (e.g.`code={system|}[code],{system|}[code],...`)
* Including optional support for **AND** search on `date` (e.g.`date=[date]&date=[date]&...`)
* Including support for these `date` comparators: "gt", "lt", "ge", "le"
`GET [base]/Observation?patient={Patient/}[id]&code={system|}[search_code]{,{system|}[code],...}&date={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&code=http://loinc.org|82810-3&date=ge2019-01-01T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Observation Pregnancy Status Profile resources for the specified patient and date and code(s). SHOULD support search by multiple codes. ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-observation-pregnancystatus",
  "extension" : [
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
      "valueInteger" : 4
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-pregnancystatus",
  "version" : "0.1.0",
  "name" : "USCoreObservationPregnancyStatusProfile",
  "title" : "US Core Observation Pregnancy Status Profile",
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
  "description" : "The  US Core Pregnancy Status Observation Profile inherits from the FHIR [Observation](https://hl7.org/fhir/R4/observation.html) resource; refer to it for scope and usage definitions. This profile meets the requirements of the U.S. Core Data for Interoperability (USCDI)  *Pregnancy Status* Data Element. It sets minimum expectations for the  Observation resource to record, search, and fetch the patient's state or condition of being pregnant. It specifies which core elements, extensions,  vocabularies, and value sets **SHALL** be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption.",
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
      "identity" : "sct-concept",
      "uri" : "http://snomed.info/conceptdomain",
      "name" : "SNOMED CT Concept Domain Binding"
    },
    {
      "identity" : "v2",
      "uri" : "http://hl7.org/v2",
      "name" : "HL7 v2 Mapping"
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
      "identity" : "sct-attr",
      "uri" : "http://snomed.org/attributebinding",
      "name" : "SNOMED CT Attribute Binding"
    }
  ],
  "kind" : "resource",
  "abstract" : false,
  "type" : "Observation",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/Observation",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "Observation",
        "path" : "Observation",
        "mustSupport" : false
      },
      {
        "id" : "Observation.status",
        "path" : "Observation.status",
        "mustSupport" : true
      },
      {
        "id" : "Observation.category",
        "path" : "Observation.category",
        "slicing" : {
          "discriminator" : [
            {
              "type" : "value",
              "path" : "$this"
            }
          ],
          "rules" : "open"
        },
        "mustSupport" : true
      },
      {
        "id" : "Observation.category:SocialHistory",
        "path" : "Observation.category",
        "sliceName" : "SocialHistory",
        "min" : 0,
        "max" : "1",
        "patternCodeableConcept" : {
          "coding" : [
            {
              "system" : "http://terminology.hl7.org/CodeSystem/observation-category",
              "code" : "social-history"
            }
          ]
        },
        "mustSupport" : true
      },
      {
        "id" : "Observation.code",
        "path" : "Observation.code",
        "short" : "Pregnancy Status",
        "patternCodeableConcept" : {
          "coding" : [
            {
              "system" : "http://loinc.org",
              "code" : "82810-3"
            }
          ]
        },
        "mustSupport" : true
      },
      {
        "id" : "Observation.subject",
        "path" : "Observation.subject",
        "min" : 1,
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient"
            ]
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Observation.effectiveDateTime",
        "path" : "Observation.effectiveDateTime",
        "min" : 1,
        "mustSupport" : true
      },
      {
        "id" : "Observation.performer",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Observation.performer",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: Who is responsible for the observation",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitioner",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient",
              "http://hl7.org/fhir/StructureDefinition/PractitionerRole",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-careteam",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-relatedperson"
            ],
            "_targetProfile" : [
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
        ]
      },
      {
        "id" : "Observation.valueCodeableConcept",
        "path" : "Observation.valueCodeableConcept",
        "short" : "Coded Responses from Pregnancy Status Value Set",
        "min" : 1,
        "type" : [
          {
            "code" : "CodeableConcept"
          }
        ],
        "mustSupport" : true,
        "binding" : {
          "strength" : "preferred",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.113762.1.4.1240.12"
        }
      }
    ]
  }
}

```
