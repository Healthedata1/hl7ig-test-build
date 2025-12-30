# US Core Heart Rate Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Heart Rate Profile**

## Resource Profile: US Core Heart Rate Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-heart-rate | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreHeartRateProfile |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core Heart Rate Profile inherits from the US Core Vital Signs Profile. This profile sets minimum expectations for the Observation resource to record, search, and fetch heart rate observations with a standard LOINC code and UCUM units of measure. It specifies which**additional**core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. 

**Usages:**

* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md), [US Core Server CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-server-liquid.md), [US Core Client CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-client.html) and [US Core Server CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-server.html)
* This Profile is not used by any profiles in this Implementation Guide

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-heart-rate)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-heart-rate.csv), [Excel](StructureDefinition-us-core-heart-rate.xlsx), [Schematron](StructureDefinition-us-core-heart-rate.sch) 

### Notes:

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-heart-rate.html

type = Observation

title = US Core Heart Rate Profile

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support searching for all Observations using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)search parameters:`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=http://terminology.hl7.org/CodeSystem/observation-category|vital-signs

**Implementation Notes**: Fetches a bundle of all US Core Heart Rate Profile resources for the specified patient and a category code = "vital-signs" ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHALL**support searching for all Observations by code using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[code](SearchParameter-us-core-observation-code.md)search parameters:
* Including optional support **OR** search on `code` (e.g.`code={system|}[code],{system|}[code],...`)
`GET [base]/Observation?patient={Patient/}[id]&code={system|}[search_code]{,{system|}[code],...}`Examples:
> 
1. GET [base]/Observation?patient=Patient/1137192&code=http://loinc.org|8867-4
1. GET [base]/Observation?patient=Patient/1137192&code=http://loinc.org|8867-4,http://loinc.org|9279-1,http://loinc.org|85354-9

**Implementation Notes**: Fetches a bundle of all US Core Heart Rate Profile resources for the specified patient and observation code(s). SHOULD support search by multiple codes. The US Core Heart Rate Profile "code" parameter searches only`.code`and not`component.code`. ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHALL**support searching for all Observations by date (for example, results after 2018) using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)and[date](SearchParameter-us-core-observation-date.md)search parameters:
* Including optional support for **AND** search on `date` (e.g.`date=[date]&date=[date]&...`)
* Including support for these `date` comparators: "gt", "lt", "ge", "le"
`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]&date={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=http://terminology.hl7.org/CodeSystem/observation-category|vital-signs&date=ge2018-03-14T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Heart Rate Profile resources for the specified patient and date and a category code = "vital-signs" ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).

#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported

1. **SHOULD**support searching for all Observations for a patient for a given status (for example all observations marked as final) using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)and[status](SearchParameter-us-core-observation-status.md)search parameters:
* Including support **OR** search on `status` (e.g.`status={system|}[code],{system|}[code],...`)
`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]&status={system|}[search_code]{,{system|}[code],...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=http://terminology.hl7.org/CodeSystem/observation-category|vital-signs&status=final

**Implementation Notes**: Fetches a bundle of all US Core Heart Rate Profile resources for the specified patient and category = "vital-signs" and status ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHOULD**support searching using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)and[_lastUpdated](SearchParameter-us-core-observation-lastupdated.md)search parameters:
* Including optional support for **AND** search on `_lastUpdated` (e.g.`_lastUpdated=[date]&_lastUpdated=[date]&...`)
* Including support for these `_lastUpdated` comparators: "gt", "lt", "ge", "le"
`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]&_lastUpdated=[dateTime]`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=http://terminology.hl7.org/CodeSystem/observation-category|vital-signs&_lastUpdated=ge2024-01-01T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Heart Rate Profile resources for the specified patient and category code = "vital-signs" and _lastUpdated. See the US Core General Guidance page for [Searching Using lastUpdated]. ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).

1. **SHOULD**support searching Observations by code and date using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[code](SearchParameter-us-core-observation-code.md)and[date](SearchParameter-us-core-observation-date.md)search parameters:
* Including optional support **OR** search on `code` (e.g.`code={system|}[code],{system|}[code],...`)
* Including optional support for **AND** search on `date` (e.g.`date=[date]&date=[date]&...`)
* Including support for these `date` comparators: "gt", "lt", "ge", "le"
`GET [base]/Observation?patient={Patient/}[id]&code={system|}[search_code]{,{system|}[code],...}&date={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&code=http://loinc.org|8867-4&date=ge2019-01-01T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Heart Rate Profile resources for the specified patient and date and code(s). SHOULD support search by multiple codes. ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-heart-rate",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-heart-rate",
  "version" : "0.1.0",
  "name" : "USCoreHeartRateProfile",
  "title" : "US Core Heart Rate Profile",
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
  "description" : "The US Core Heart Rate Profile inherits from the US Core Vital Signs Profile. This profile sets minimum expectations for the Observation resource to record, search,  and fetch heart rate observations with a standard LOINC code and UCUM units of measure. It specifies which *additional*  core elements, extensions,  vocabularies, and value sets **SHALL** be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption.",
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
  "baseDefinition" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-vital-signs",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "Observation",
        "path" : "Observation",
        "short" : "US Core Heart Rate Profile"
      },
      {
        "id" : "Observation.code",
        "path" : "Observation.code",
        "short" : "Heart Rate",
        "type" : [
          {
            "code" : "CodeableConcept"
          }
        ],
        "patternCodeableConcept" : {
          "coding" : [
            {
              "system" : "http://loinc.org",
              "code" : "8867-4"
            }
          ]
        },
        "mustSupport" : true
      },
      {
        "id" : "Observation.valueQuantity",
        "path" : "Observation.valueQuantity",
        "short" : "Vital Signs Value",
        "min" : 0,
        "max" : "1",
        "mustSupport" : true
      },
      {
        "id" : "Observation.valueQuantity.value",
        "path" : "Observation.valueQuantity.value",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "decimal"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Observation.valueQuantity.unit",
        "path" : "Observation.valueQuantity.unit",
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
        "id" : "Observation.valueQuantity.system",
        "path" : "Observation.valueQuantity.system",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "uri"
          }
        ],
        "fixedUri" : "http://unitsofmeasure.org",
        "mustSupport" : true
      },
      {
        "id" : "Observation.valueQuantity.code",
        "path" : "Observation.valueQuantity.code",
        "short" : "Coded responses from the common UCUM units for vital signs value set.",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "code"
          }
        ],
        "fixedCode" : "/min",
        "mustSupport" : true
      }
    ]
  }
}

```
