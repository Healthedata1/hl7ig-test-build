# US Core Vital Signs Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Vital Signs Profile**

## Resource Profile: US Core Vital Signs Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-vital-signs | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreVitalSignsProfile |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
This profile is based on the base[FHIR Vital Signs Profile](http://hl7.org/fhir/R4/observation-vitalsigns.html)and defines**additional**constraints on the Observation resource to represent vital signs observations. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. This US Core profiles that are derived from this profile are listed below. 

**Usages:**

* Derived from this Profile: [US Core Heart Rate Profile](StructureDefinition-us-core-heart-rate.md), [US Core Pediatric Head Occipital-frontal Circumference Percentile Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-head-occipital-frontal-circumference-percentile.html), [US Core Pediatric BMI for Age Observation Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-pediatric-bmi-for-age.html), [US Core Pediatric Weight for Height Observation Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-pediatric-weight-for-height.html)...Show 9 more,[US Core Blood Pressure Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-blood-pressure.html),[US Core BMI Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-bmi.html),[US Core Body Height Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-body-height.html),[US Core Body Temperature Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-body-temperature.html),[US Core Body Weight Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-body-weight.html),[US Core Head Circumference Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-head-circumference.html),[US Core Heart Rate Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-heart-rate.html),[US Core Pulse Oximetry Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-pulse-oximetry.html)and[US Core Respiratory Rate Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-respiratory-rate.html)
* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md), [US Core Server CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-server-liquid.md), [US Core Client CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-client.html) and [US Core Server CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-server.html)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-vital-signs)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-vital-signs.csv), [Excel](StructureDefinition-us-core-vital-signs.xlsx), [Schematron](StructureDefinition-us-core-vital-signs.sch) 

### Notes:

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-vital-signs.html

type = Observation

title = US Core Vital Signs Profile

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support searching for all Observations using the combination of[patient](http://hl7.org/fhir/R4/patient.html)and[category](SearchParameter-us-core-observation-category.md)search parameters:`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=http://terminology.hl7.org/CodeSystem/observation-category|vital-signs

**Implementation Notes**: Fetches a bundle of all US Core Vital Signs Profile resources for the specified patient and a category code = "vital-signs" ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHALL**support searching for all Observations by code using the combination of[patient](http://hl7.org/fhir/R4/patient.html)and[code](SearchParameter-us-core-observation-code.md)search parameters:
* Including optional support **OR** search on `code` (e.g.`code={system|}[code],{system|}[code],...`)
`GET [base]/Observation?patient={Patient/}[id]&code={system|}[search_code]{,{system|}[code],...}`Examples:
> 
1. GET [base]/Observation?patient=Patient/1137192&code=http://loinc.org|8867-4
1. GET [base]/Observation?patient=Patient/1137192&code=http://loinc.org|8867-4,http://loinc.org|9279-1,http://loinc.org|85354-9

**Implementation Notes**: Fetches a bundle of all US Core Vital Signs Profile resources for the specified patient and observation code(s). SHOULD support search by multiple codes. The US Core Vital Signs Profile "code" parameter searches only`.code`and not`component.code`. ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHALL**support searching for all Observations by date (for example, results after 2018) using the combination of[patient](http://hl7.org/fhir/R4/patient.html)and[category](SearchParameter-us-core-observation-category.md)and[date](SearchParameter-us-core-observation-date.md)search parameters:
* Including optional support for **AND** search on `date` (e.g.`date=[date]&date=[date]&...`)
* Including support for these `date` comparators: "gt", "lt", "ge", "le"
`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]&date={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=http://terminology.hl7.org/CodeSystem/observation-category|vital-signs&date=ge2018-03-14T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Vital Signs Profile resources for the specified patient and date and a category code = "vital-signs" ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).

#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported

1. **SHOULD**support searching for all Observations for a patient for a given status (for example all observations marked as final) using the combination of[patient](http://hl7.org/fhir/R4/patient.html)and[category](SearchParameter-us-core-observation-category.md)and[status](SearchParameter-us-core-observation-status.md)search parameters:
* Including support **OR** search on `status` (e.g.`status={system|}[code],{system|}[code],...`)
`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]&status={system|}[search_code]{,{system|}[code],...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=http://terminology.hl7.org/CodeSystem/observation-category|vital-signs&status=final

**Implementation Notes**: Fetches a bundle of all US Core Vital Signs Profile resources for the specified patient and category = "vital-signs" and status ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHOULD**support searching using the combination of[patient](http://hl7.org/fhir/R4/patient.html)and[category](SearchParameter-us-core-observation-category.md)and[_lastUpdated](SearchParameter-us-core-observation-lastupdated.md)search parameters:
* Including optional support for **AND** search on `_lastUpdated` (e.g.`_lastUpdated=[date]&_lastUpdated=[date]&...`)
* Including support for these `_lastUpdated` comparators: "gt", "lt", "ge", "le"
`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]&_lastUpdated=[dateTime]`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=http://terminology.hl7.org/CodeSystem/observation-category|vital-signs&_lastUpdated=ge2024-01-01T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Vital Signs Profile resources for the specified patient and category code = "vital-signs" and _lastUpdated. See the US Core General Guidance page for [Searching Using lastUpdated]. ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).

1. **SHOULD**support searching Observations by code and date using the combination of[patient](http://hl7.org/fhir/R4/patient.html)and[code](SearchParameter-us-core-observation-code.md)and[date](SearchParameter-us-core-observation-date.md)search parameters:
* Including optional support **OR** search on `code` (e.g.`code={system|}[code],{system|}[code],...`)
* Including optional support for **AND** search on `date` (e.g.`date=[date]&date=[date]&...`)
* Including support for these `date` comparators: "gt", "lt", "ge", "le"
`GET [base]/Observation?patient={Patient/}[id]&code={system|}[search_code]{,{system|}[code],...}&date={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&code=http://loinc.org|8867-4&date=ge2019-01-01T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Vital Signs Profile resources for the specified patient and date and code(s). SHOULD support search by multiple codes. ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-vital-signs",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-vital-signs",
  "version" : "0.1.0",
  "name" : "USCoreVitalSignsProfile",
  "title" : "US Core Vital Signs Profile",
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
  "description" : "This profile is based on the base [FHIR Vital Signs Profile](http://hl7.org/fhir/R4/observation-vitalsigns.html)  and defines *additional* constraints on the Observation resource to represent vital  signs observations. It specifies which core elements, extensions,  vocabularies, and value sets **SHALL** be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption.  This US Core profiles that are derived from this profile  are listed below.",
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
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/vitalsigns",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "Observation",
        "path" : "Observation",
        "short" : "US Core Vital Signs Profile"
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
              "path" : "coding.code"
            },
            {
              "type" : "value",
              "path" : "coding.system"
            }
          ],
          "ordered" : false,
          "rules" : "open"
        },
        "min" : 1,
        "max" : "*",
        "type" : [
          {
            "code" : "CodeableConcept"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Observation.category:VSCat",
        "path" : "Observation.category",
        "sliceName" : "VSCat",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "CodeableConcept"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Observation.category:VSCat.coding",
        "path" : "Observation.category.coding",
        "min" : 1,
        "max" : "*",
        "type" : [
          {
            "code" : "Coding"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Observation.category:VSCat.coding.system",
        "path" : "Observation.category.coding.system",
        "short" : "Identity of the terminology system",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "uri"
          }
        ],
        "fixedUri" : "http://terminology.hl7.org/CodeSystem/observation-category",
        "mustSupport" : true
      },
      {
        "id" : "Observation.category:VSCat.coding.code",
        "path" : "Observation.category.coding.code",
        "short" : "Symbol in syntax defined by the system",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "code"
          }
        ],
        "fixedCode" : "vital-signs",
        "mustSupport" : true
      },
      {
        "id" : "Observation.code",
        "path" : "Observation.code",
        "short" : "Coded vital sign result type",
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "description" : "Vital sign result types",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.113883.3.88.12.80.62"
        }
      },
      {
        "id" : "Observation.subject",
        "path" : "Observation.subject",
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
        "id" : "Observation.effective[x]",
        "path" : "Observation.effective[x]",
        "short" : "Often just a dateTime for Vital Signs",
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
        "mustSupport" : true
      },
      {
        "id" : "Observation.performer",
        "path" : "Observation.performer",
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
        ],
        "mustSupport" : true
      },
      {
        "id" : "Observation.value[x]",
        "path" : "Observation.value[x]",
        "short" : "Vital Signs Value",
        "definition" : "Vital Signs value are typically recorded using the Quantity data type.",
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
            "code" : "CodeableConcept"
          },
          {
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
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "description" : "Common UCUM units for recording Vital Signs.",
          "valueSet" : "http://hl7.org/fhir/ValueSet/ucum-vitals-common|4.0.1"
        }
      },
      {
        "id" : "Observation.dataAbsentReason",
        "path" : "Observation.dataAbsentReason",
        "mustSupport" : true
      },
      {
        "id" : "Observation.component",
        "path" : "Observation.component",
        "short" : "Component observations",
        "definition" : "Used when reporting component observation such as systolic and diastolic blood pressure.",
        "mustSupport" : true
      },
      {
        "id" : "Observation.component.code",
        "path" : "Observation.component.code",
        "short" : "Coded vital sign result type",
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "description" : "Vital sign result types",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.113883.3.88.12.80.62"
        }
      },
      {
        "id" : "Observation.component.value[x]",
        "path" : "Observation.component.value[x]",
        "short" : "Vital Sign Component Value",
        "definition" : "Vital Signs value are typically recorded using the Quantity data type. For supporting observations such as cuff size could use other datatypes such as CodeableConcept.",
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
            "code" : "CodeableConcept"
          },
          {
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
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "description" : "Common UCUM units for recording Vital Signs.",
          "valueSet" : "http://hl7.org/fhir/ValueSet/ucum-vitals-common|4.0.1"
        }
      },
      {
        "id" : "Observation.component.dataAbsentReason",
        "path" : "Observation.component.dataAbsentReason",
        "mustSupport" : true
      }
    ]
  }
}

```
