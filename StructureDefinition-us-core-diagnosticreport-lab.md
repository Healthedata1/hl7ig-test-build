# US Core DiagnosticReport Profile for Laboratory Results Reporting - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core DiagnosticReport Profile for Laboratory Results Reporting**

## Resource Profile: US Core DiagnosticReport Profile for Laboratory Results Reporting 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-diagnosticreport-lab | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreDiagnosticReportProfileLaboratoryReporting |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core DiagnosticReport Profile for Laboratory Results Reporting inherits from the FHIR[DiagnosticReport](https://hl7.org/fhir/R4/diagnosticreport.html)resource; refer to it for scope and usage definitions. Laboratory results are grouped and summarized using the DiagnosticReport resource, which typically references Observation resource(s). Each Observation resource represents an individual laboratory test and result value or component result values or a nested panel (such as a microbial susceptibility panel) that references other observations. Laboratory results can also be presented in report form or as free text. This profile sets minimum expectations for the DiagnosticReport resource to record, search, and fetch laboratory results associated with a patient. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. 

**Usages:**

* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md), [US Core Server CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-server-liquid.md), [US Core Client CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-client.html) and [US Core Server CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-server.html)
* This Profile is not used by any profiles in this Implementation Guide

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-diagnosticreport-lab)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-diagnosticreport-lab.csv), [Excel](StructureDefinition-us-core-diagnosticreport-lab.xlsx), [Schematron](StructureDefinition-us-core-diagnosticreport-lab.sch) 

### Notes:

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-diagnosticreport-lab.html

type = DiagnosticReport

title = US Core DiagnosticReport Profile for Laboratory Results Reporting

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support searching for all diagnosticreports for a patient using the[patient](SearchParameter-us-core-diagnosticreport-patient.md)search parameter:`GET [base]/DiagnosticReport?patient={Patient/}[id]`Example:
1. GET [base]/DiagnosticReport?patient=1137192
**Implementation Notes**: Fetches a bundle of all US Core DiagnosticReport Profile for Laboratory Results Reporting resources for the specified patient ([how to search by reference](foo.md)).

1. **SHALL**support searching for all laboratory reports using the combination of[patient](SearchParameter-us-core-diagnosticreport-patient.md)and[category](SearchParameter-us-core-diagnosticreport-category.md)search parameters:`GET [base]/DiagnosticReport?patient={Patient/}[id]&category={system|}[search_code]`Example:
1. GET [base]/DiagnosticReport?patient=f201&category=http://terminology.hl7.org/CodeSystem/v2-0074|LAB
**Implementation Notes**: Fetches a bundle of all US Core DiagnosticReport Profile for Laboratory Results Reporting resources for the specified patient and a category code = "LAB" ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHALL**support searching for all laboratory reports by code (for example, search for all metabolic panel reports for a patient, or search for all cbcs, metabolic panels, and urinalysis panels for a patient) using the combination of[patient](SearchParameter-us-core-diagnosticreport-patient.md)and[code](SearchParameter-us-core-diagnosticreport-code.md)search parameters:
* Including optional support **OR** search on `code` (e.g.`code={system|}[code],{system|}[code],...`)
`GET [base]/DiagnosticReport?patient={Patient/}[id]&code={system|}[search_code]{,{system|}[code],...}`Example:
1. GET [base]/DiagnosticReport?patient=1032702&code=http://loinc.org|24323-8
**Implementation Notes**: Fetches a bundle of all US Core DiagnosticReport Profile for Laboratory Results Reporting resources for the specified patient and report code(s). SHOULD support search by multiple report codes. ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHALL**support searching for all laboratory reports by date using the combination of[patient](SearchParameter-us-core-diagnosticreport-patient.md)and[category](SearchParameter-us-core-diagnosticreport-category.md)and[date](SearchParameter-us-core-diagnosticreport-date.md)search parameters:
* Including optional support for **AND** search on `date` (e.g.`date=[date]&date=[date]&...`)
* Including support for these `date` comparators: "gt", "lt", "ge", "le"
`GET [base]/DiagnosticReport?patient={Patient/}[id]&category={system|}[search_code]&date={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
1. GET [base]/DiagnosticReport?patient=f201&category=http://terminology.hl7.org/CodeSystem/v2-0074|LAB&date=ge2010-01-14T00:00:00Z
**Implementation Notes**: Fetches a bundle of all US Core DiagnosticReport Profile for Laboratory Results Reporting resources for the specified patient and date and a category code = "LAB" ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).

#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported

1. **SHOULD**support searching for all laboratory reports for a patient for a given status (for example completed reports ) using the combination of[patient](SearchParameter-us-core-diagnosticreport-patient.md)and[status](SearchParameter-us-core-diagnosticreport-status.md)search parameters:
* Including support **OR** search on `status` (e.g.`status={system|}[code],{system|}[code],...`)
`GET [base]/DiagnosticReport?patient={Patient/}[id]&status={system|}[search_code]{,{system|}[code],...}`Example:
1. GET [base]/DiagnosticReport?patient=1137192&status=completed
**Implementation Notes**: Fetches a bundle of all US Core DiagnosticReport Profile for Laboratory Results Reporting resources for the specified patient and status ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHOULD**support searching using the combination of[patient](SearchParameter-us-core-diagnosticreport-patient.md)and[category](SearchParameter-us-core-diagnosticreport-category.md)and[_lastUpdated](SearchParameter-us-core-diagnosticreport-lastupdated.md)search parameters:
* Including optional support for **AND** search on `_lastUpdated` (e.g.`_lastUpdated=[date]&_lastUpdated=[date]&...`)
* Including support for these `_lastUpdated` comparators: "gt", "lt", "ge", "le"
`GET [base]/DiagnosticReport?patient={Patient/}[id]&category={system|}[search_code]&_lastUpdated=[dateTime]`Example:
1. GET [base]/DiagnosticReport?patient=f201&category=http://terminology.hl7.org/CodeSystem/v2-0074|LAB&_lastUpdated=ge2010-01-14T00:00:00Z
**Implementation Notes**: Fetches a bundle of all US Core DiagnosticReport Profile for Laboratory Results Reporting resources for the specified patient and category and _lastUpdated. See the US Core General Guidance page for [Searching Using lastUpdated]. ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).

1. **SHOULD**support searching for laboratory reports by code and date (for example, search for all metabolic panel reports since 2019 for a patient) using the combination of[patient](SearchParameter-us-core-diagnosticreport-patient.md)and[code](SearchParameter-us-core-diagnosticreport-code.md)and[date](SearchParameter-us-core-diagnosticreport-date.md)search parameters:
* Including optional support **OR** search on `code` (e.g.`code={system|}[code],{system|}[code],...`)
* Including optional support for **AND** search on `date` (e.g.`date=[date]&date=[date]&...`)
* Including support for these `date` comparators: "gt", "lt", "ge", "le"
`GET [base]/DiagnosticReport?patient={Patient/}[id]&code={system|}[search_code]{,{system|}[code],...}&date={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
1. GET [base]/DiagnosticReport?patient=f201&code=http://loinc.org|24323-8&date=ge2019-01-14T00:00:00Z
**Implementation Notes**: Fetches a bundle of all US Core DiagnosticReport Profile for Laboratory Results Reporting resources for the specified patient and date and report code(s). SHOULD support search by multiple report codes. ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-diagnosticreport-lab",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-diagnosticreport-lab",
  "version" : "0.1.0",
  "name" : "USCoreDiagnosticReportProfileLaboratoryReporting",
  "title" : "US Core DiagnosticReport Profile for Laboratory Results Reporting",
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
  "description" : "The US Core DiagnosticReport Profile for Laboratory Results Reporting inherits from the FHIR [DiagnosticReport](https://hl7.org/fhir/R4/diagnosticreport.html) resource; refer to it for scope and usage definitions. Laboratory results are grouped and summarized using the DiagnosticReport resource, which typically references Observation resource(s). Each Observation resource represents an individual laboratory test and result value or component result values or a nested panel (such as a microbial susceptibility panel) that references other observations. Laboratory results can also be presented in report form or as free text. This profile sets minimum expectations for the DiagnosticReport resource to record, search,  and fetch laboratory results associated with a patient. It specifies which core elements, extensions, vocabularies, and value sets **SHALL** be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption.",
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
    }
  ],
  "kind" : "resource",
  "abstract" : false,
  "type" : "DiagnosticReport",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/DiagnosticReport",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "DiagnosticReport",
        "path" : "DiagnosticReport",
        "alias" : ["Lab Result", "Lab Report"],
        "constraint" : [
          {
            "key" : "us-core-8",
            "severity" : "error",
            "human" : "effective[x] SHALL be present if the status is 'partial', 'preliminary', 'final', 'amended', 'corrected' or 'appended'",
            "expression" : "(status='partial' or status='preliminary' or status='final' or status='amended' or status='corrected' or status='appended' ) implies effective.exists()"
          },
          {
            "key" : "us-core-9",
            "severity" : "error",
            "human" : "issued SHALL be present if the status is 'partial', 'preliminary', 'final', 'amended', 'corrected' or 'appended'",
            "expression" : "(status='partial' or status='preliminary' or status='final' or status='amended' or status='corrected' or status='appended' ) implies issued.exists()"
          }
        ],
        "mustSupport" : false
      },
      {
        "id" : "DiagnosticReport.meta",
        "path" : "DiagnosticReport.meta",
        "mustSupport" : true
      },
      {
        "id" : "DiagnosticReport.meta.lastUpdated",
        "path" : "DiagnosticReport.meta.lastUpdated",
        "short" : "When the resource last changed",
        "mustSupport" : true
      },
      {
        "id" : "DiagnosticReport.status",
        "path" : "DiagnosticReport.status",
        "condition" : ["us-core-8", "us-core-9"],
        "mustSupport" : true,
        "binding" : {
          "strength" : "required",
          "valueSet" : "http://hl7.org/fhir/ValueSet/diagnostic-report-status"
        }
      },
      {
        "id" : "DiagnosticReport.category",
        "path" : "DiagnosticReport.category",
        "slicing" : {
          "discriminator" : [
            {
              "type" : "value",
              "path" : "$this"
            }
          ],
          "rules" : "open"
        },
        "min" : 1,
        "mustSupport" : true
      },
      {
        "id" : "DiagnosticReport.category:LaboratorySlice",
        "path" : "DiagnosticReport.category",
        "sliceName" : "LaboratorySlice",
        "min" : 1,
        "max" : "1",
        "patternCodeableConcept" : {
          "coding" : [
            {
              "system" : "http://terminology.hl7.org/CodeSystem/v2-0074",
              "code" : "LAB"
            }
          ]
        },
        "mustSupport" : true
      },
      {
        "id" : "DiagnosticReport.code",
        "path" : "DiagnosticReport.code",
        "short" : "US Core Laboratory Report Order Code",
        "definition" : "The test, panel or battery that was ordered.",
        "comment" : "UsageNote= The typical patterns for codes are:  1)  a LOINC code either as an additional coding from a \"local\" code or as a primary code, or 2)  a local code only if no suitable LOINC exists,  or 3)  both the local and the LOINC additional coding.   Systems SHALL be capable of sending the local code if one exists.",
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "description" : "LOINC codes",
          "valueSet" : "http://hl7.org/fhir/us/core/ValueSet/us-core-laboratory-test-codes"
        }
      },
      {
        "id" : "DiagnosticReport.subject",
        "path" : "DiagnosticReport.subject",
        "min" : 1,
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient",
              "http://hl7.org/fhir/StructureDefinition/Group",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-device",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-location"
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
        "id" : "DiagnosticReport.encounter",
        "path" : "DiagnosticReport.encounter",
        "short" : "Encounter associated with DiagnosticReport",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-encounter"
            ]
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "DiagnosticReport.effective[x]",
        "path" : "DiagnosticReport.effective[x]",
        "short" : "Diagnostically relevant time (typically the time of specimen collection)",
        "type" : [
          {
            "extension" : [
              {
                "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                "valueBoolean" : true
              }
            ],
            "code" : "dateTime"
          },
          {
            "code" : "Period"
          }
        ],
        "condition" : ["us-core-8"],
        "mustSupport" : true
      },
      {
        "id" : "DiagnosticReport.issued",
        "path" : "DiagnosticReport.issued",
        "short" : "When the report was released",
        "condition" : ["us-core-9"],
        "mustSupport" : true
      },
      {
        "id" : "DiagnosticReport.performer",
        "path" : "DiagnosticReport.performer",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitioner",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-careteam",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitionerrole"
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
        "id" : "DiagnosticReport.resultsInterpreter",
        "path" : "DiagnosticReport.resultsInterpreter",
        "short" : "Who analyzed and reported the conclusions and interpretations",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitioner",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization",
              "http://hl7.org/fhir/StructureDefinition/PractitionerRole",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-careteam"
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
        "id" : "DiagnosticReport.result",
        "path" : "DiagnosticReport.result",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-lab"
            ]
          }
        ],
        "mustSupport" : true
      }
    ]
  }
}

```
