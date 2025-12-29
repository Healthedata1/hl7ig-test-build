# US Core Laboratory Result Observation Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Laboratory Result Observation Profile**

## Resource Profile: US Core Laboratory Result Observation Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-lab | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreLaboratoryResultObservationProfile |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core Laboratory Result Observation Profile is based upon the US Core Observation Clinical Result Profile and, along with the US Core DiagnosticReport Profile for Laboratory Results Reporting, meets the U.S. Core Data for Interoperability (USCDI) Laboratory requirements. Laboratory results are grouped and summarized using the DiagnosticReport resource, which references Observation resources. Each Observation resource represents an individual laboratory test and result value, a “nested” panel (such as a microbial susceptibility panel) that references other observations, or rarely a laboratory test with component result values. The US Core Laboratory Result Observation Profile sets minimum expectations for the Observation resource to record, search, and fetch laboratory test results associated with a patient to promote interoperability and adoption through common implementation. It identifies which core elements, extensions, vocabularies, and value sets SHALL be present in the resource and constrains the way the elements are used when using this profile. It provides the floor for standards development for specific use cases. 

**Usages:**

* Refer to this Profile: [US Core DiagnosticReport Profile for Laboratory Results Reporting](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-diagnosticreport-lab.html) and [US Core DiagnosticReport Profile for Report and Note Exchange](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-diagnosticreport-note.html)
* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md), [US Core Server CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-server-liquid.md), [US Core Client CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-client.html) and [US Core Server CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-server.html)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-observation-lab)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-observation-lab.csv), [Excel](StructureDefinition-us-core-observation-lab.xlsx), [Schematron](StructureDefinition-us-core-observation-lab.sch) 

### Notes:

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-observation-lab.html

type = Observation

title = US Core Laboratory Result Observation Profile

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support searching for all laboratory results using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)search parameters:`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=http://terminology.hl7.org/CodeSystem/observation-category|laboratory

**Implementation Notes**: Fetches a bundle of all US Core Laboratory Result Observation Profile resources for the specified patient and a category code = "laboratory" ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHALL**support searching for all laboratory results by code (for example, search for all blood glucose lab results for a patient, or search for all blood glucose, urine glucose and urine ketones for a patient) using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[code](SearchParameter-us-core-observation-code.md)search parameters:
* Including optional support **OR** search on `code` (e.g.`code={system|}[code],{system|}[code],...`)
`GET [base]/Observation?patient={Patient/}[id]&code={system|}[search_code]{,{system|}[code],...}`Examples:
> 
1. GET [base]/Observation?patient=Patient/1137192&code=http://loinc.org|2339-0
1. GET [base]/Observation?patient=Patient/1137192&code=http://loinc.org|2339-0,http://loinc.org|25428-4,http://loinc.org|2514-8

**Implementation Notes**: Fetches a bundle of all US Core Laboratory Result Observation Profile resources for the specified patient and observation code(s). SHOULD support search by multiple report codes. The US Core Laboratory Result Observation Profile "code" parameter searches only`US Core Laboratory Result Observation Profile.code`. ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHALL**support searching for all laboratory results by date (for example, find all the laboratory results after 2018-03-14.) using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)and[date](SearchParameter-us-core-observation-date.md)search parameters:
* Including optional support for **AND** search on `date` (e.g.`date=[date]&date=[date]&...`)
* Including support for these `date` comparators: "gt", "lt", "ge", "le"
`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]&date={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=http://terminology.hl7.org/CodeSystem/observation-category|laboratory&date=ge2018-03-14T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Laboratory Result Observation Profile resources for the specified patient and date and a category code = "laboratory" ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).

#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported

1. **SHOULD**support searching for all laboratory results for a patient for a given status (for example all observations marked as final) using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)and[status](SearchParameter-us-core-observation-status.md)search parameters:
* Including support **OR** search on `status` (e.g.`status={system|}[code],{system|}[code],...`)
`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]&status={system|}[search_code]{,{system|}[code],...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&http://terminology.hl7.org/CodeSystem/observation-category|laboratory&status=final

**Implementation Notes**: Fetches a bundle of all US Core Laboratory Result Observation Profile resources for the specified patient and category = "laboratory" and status ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHOULD**support searching using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)and[_lastUpdated](SearchParameter-us-core-observation-lastupdated.md)search parameters:
* Including optional support for **AND** search on `_lastUpdated` (e.g.`_lastUpdated=[date]&_lastUpdated=[date]&...`)
* Including support for these `_lastUpdated` comparators: "gt", "lt", "ge", "le"
`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]&_lastUpdated=[dateTime]`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=http://terminology.hl7.org/CodeSystem/observation-category|laboratory&_lastUpdated=ge2024-01-01T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Laboratory Result Observation Profile resources for the specified patient and category and _lastUpdated. See the US Core General Guidance page for [Searching Using lastUpdated]. ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).

1. **SHOULD**support searching laboratory results by code and date (for example, search for all blood glucose lab results since 2019 for a patient) using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[code](SearchParameter-us-core-observation-code.md)and[date](SearchParameter-us-core-observation-date.md)search parameters:
* Including optional support **OR** search on `code` (e.g.`code={system|}[code],{system|}[code],...`)
* Including optional support for **AND** search on `date` (e.g.`date=[date]&date=[date]&...`)
* Including support for these `date` comparators: "gt", "lt", "ge", "le"
`GET [base]/Observation?patient={Patient/}[id]&code={system|}[search_code]{,{system|}[code],...}&date={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&code=http://loinc.org|2339-0&date=ge2019-01-01T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Laboratory Result Observation Profile resources for the specified patient and date and report code(s). SHOULD support search by multiple report codes. ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-observation-lab",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-lab",
  "version" : "0.1.0",
  "name" : "USCoreLaboratoryResultObservationProfile",
  "title" : "US Core Laboratory Result Observation Profile",
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
  "description" : "The US Core Laboratory Result Observation Profile is based upon the US Core Observation Clinical Result Profile and, along with the US Core DiagnosticReport Profile for Laboratory Results Reporting, meets the U.S. Core Data for Interoperability (USCDI) Laboratory requirements. Laboratory results are grouped and summarized using the DiagnosticReport resource, which references Observation resources. Each Observation resource represents an individual laboratory test and result value, a “nested” panel (such as a microbial susceptibility panel) that references other observations, or rarely a laboratory test with component result values. The US Core Laboratory Result Observation Profile sets minimum expectations for the Observation resource to record, search, and fetch laboratory test results associated with a patient to promote interoperability and adoption through common implementation. It identifies which core elements, extensions, vocabularies, and value sets SHALL be present in the resource and constrains the way the elements are used when using this profile. It provides the floor for standards development for specific use cases.",
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
  "baseDefinition" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-clinical-result",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "Observation",
        "path" : "Observation"
      },
      {
        "id" : "Observation.meta",
        "path" : "Observation.meta",
        "mustSupport" : true
      },
      {
        "id" : "Observation.meta.lastUpdated",
        "path" : "Observation.meta.lastUpdated",
        "short" : "When the resource last changed",
        "mustSupport" : true
      },
      {
        "id" : "Observation.category:us-core",
        "path" : "Observation.category",
        "sliceName" : "us-core",
        "min" : 1,
        "max" : "1",
        "patternCodeableConcept" : {
          "coding" : [
            {
              "system" : "http://terminology.hl7.org/CodeSystem/observation-category",
              "code" : "laboratory"
            }
          ]
        },
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Observation.category"
          }
        ]
      },
      {
        "id" : "Observation.code",
        "path" : "Observation.code",
        "short" : "Laboratory Test Name",
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "description" : "Laboratory LOINC Codes",
          "valueSet" : "http://hl7.org/fhir/us/core/ValueSet/us-core-laboratory-test-codes"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Observation.code"
          }
        ]
      },
      {
        "id" : "Observation.code.text",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Observation.code.text",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: The name of the test that was performed."
      },
      {
        "id" : "Observation.value[x]",
        "path" : "Observation.value[x]",
        "short" : "Result Value",
        "definition" : "The Laboratory result value.  If a coded value,  the valueCodeableConcept.code **SHOULD** be selected from [SNOMED CT](http://hl7.org/fhir/ValueSet/uslab-obs-codedresults) if the concept exists. If a numeric value, valueQuantity.code **SHALL** be selected from [UCUM](http://unitsofmeasure.org).  A FHIR [UCUM Codes value set](http://hl7.org/fhir/STU3/valueset-ucum-units.html) that defines all UCUM codes is in the FHIR specification.",
        "type" : [
          {
            "extension" : [
              {
                "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                "valueBoolean" : true
              }
            ],
            "code" : "Quantity"
          },
          {
            "extension" : [
              {
                "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                "valueBoolean" : true
              }
            ],
            "code" : "CodeableConcept"
          },
          {
            "extension" : [
              {
                "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                "valueBoolean" : true
              }
            ],
            "code" : "string"
          },
          {
            "code" : "boolean"
          },
          {
            "code" : "integer"
          },
          {
            "code" : "Range"
          },
          {
            "code" : "Ratio"
          },
          {
            "code" : "SampledData"
          },
          {
            "code" : "time"
          },
          {
            "code" : "dateTime"
          },
          {
            "code" : "Period"
          }
        ],
        "condition" : ["us-core-4"],
        "constraint" : [
          {
            "extension" : [
              {
                "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-bestpractice",
                "valueBoolean" : true
              }
            ],
            "key" : "us-core-4",
            "severity" : "warning",
            "human" : "SHOULD use SNOMED CT for coded Results",
            "expression" : "ofType(CodeableConcept).coding.system.empty() or (ofType(CodeableConcept).coding.system contains 'http://snomed.info/sct')",
            "xpath" : "not(exists(f:valueCodeableConcept/f:coding/f:system) ) or f:valueCodeableConcept/f:coding/f:system[@value='http://snomed.info/sct']"
          }
        ],
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Observation.value[x]"
          }
        ]
      },
      {
        "id" : "Observation.interpretation",
        "path" : "Observation.interpretation",
        "short" : "Result interpretation",
        "comment" : "Categorical assessment of a laboratory value, often in relation to a test's reference range. Examples include but are not limited to high, low, critical, and normal.",
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "description" : "Observation Interpretation Codes",
          "valueSet" : "http://hl7.org/fhir/ValueSet/observation-interpretation"
        }
      },
      {
        "id" : "Observation.specimen",
        "path" : "Observation.specimen",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-specimen"
            ]
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Observation.referenceRange",
        "path" : "Observation.referenceRange",
        "short" : "Result reference range",
        "comment" : "Upper and lower limit of test values expected for a designated population of individuals. Reference range values may differ by patient characteristics, laboratory test manufacturer and laboratory test performer.",
        "condition" : ["us-core-22"],
        "constraint" : [
          {
            "key" : "us-core-22",
            "severity" : "error",
            "human" : "SHALL use UCUM for coded quantity units.",
            "expression" : "(low.system.empty() or low.system = 'http://unitsofmeasure.org') and (high.system.empty() or high.system = 'http://unitsofmeasure.org')"
          }
        ],
        "mustSupport" : true
      }
    ]
  }
}

```
