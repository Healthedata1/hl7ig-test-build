# US Core Observation ADI Documentation Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Observation ADI Documentation Profile**

## Resource Profile: US Core Observation ADI Documentation Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-adi-documentation | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 2 | *Computable Name*:USCoreObservationADIDocumentationProfile |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core Observation Advance Directive Information (ADI) Documentation Profile inherits from the FHIR[Observation](https://hl7.org/fhir/R4/observation.html)resource; refer to it for scope and usage definitions. This profile and the[US Core Observation ADI DocumentationReference Profile](StructureDefinition-us-core-adi-documentreference.md)meet the[U.S. Core Data for Interoperability (USCDI)](https://www.healthit.gov/isp/united-states-core-data-interoperability-uscdi)**Advance Directive Observation**Data Element requirements. It is used to communicate whether a person has advance directive information (ADI) and, if one or more documents exist, their location. Examples of advance healthcare directive documents include physician order for life sustaining treatment (POLST), do not resuscitate order (DNR), and medical power of attorney. To communicate the type of advance directive document, the author, the verifier, and other properties, see the US Core ADI DocumentReference Profile. This profile sets minimum expectations for the Observation resource to record, search, and fetch findings about the presence of a patient's advance directives. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. 

**Usages:**

* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md) and [US Core Server CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-server-liquid.md)
* This Profile is not used by any profiles in this Implementation Guide

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-observation-adi-documentation)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-observation-adi-documentation.csv), [Excel](StructureDefinition-us-core-observation-adi-documentation.xlsx), [Schematron](StructureDefinition-us-core-observation-adi-documentation.sch) 

### Notes:

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-observation-adi-documentation.html

type = Observation

title = US Core Observation ADI Documentation Profile

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support searching for all laboratory results using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)search parameters:`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=advance-directive-observation

**Implementation Notes**: Fetches a bundle of all US Core Observation ADI Documentation Profile resources for the specified patient and a category code = "laboratory" ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHALL**support searching for all laboratory results by code (for example, search for all blood glucose lab results for a patient, or search for all blood glucose, urine glucose and urine ketones for a patient) using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[code](SearchParameter-us-core-observation-code.md)search parameters:
* Including optional support **OR** search on `code` (e.g.`code={system|}[code],{system|}[code],...`)
`GET [base]/Observation?patient={Patient/}[id]&code={system|}[search_code]{,{system|}[code],...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&code=http://loinc.org|42348-3

**Implementation Notes**: Fetches a bundle of all US Core Observation ADI Documentation Profile resources for the specified patient and observation code(s). SHOULD support search by multiple report codes. The US Core Observation ADI Documentation Profile "code" parameter searches only`US Core Observation ADI Documentation Profile.code`. ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHALL**support searching for all laboratory results by date (for example, find all the laboratory results after 2018-03-14.) using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)and[date](SearchParameter-us-core-observation-date.md)search parameters:
* Including optional support for **AND** search on `date` (e.g.`date=[date]&date=[date]&...`)
* Including support for these `date` comparators: "gt", "lt", "ge", "le"
`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]&date={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=advance-directive-observation&date=ge2018-03-14T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Observation ADI Documentation Profile resources for the specified patient and date and a category code = "laboratory" ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).

#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported

1. **SHOULD**support searching for all laboratory results for a patient for a given status (for example all observations marked as final) using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)and[status](SearchParameter-us-core-observation-status.md)search parameters:
* Including support **OR** search on `status` (e.g.`status={system|}[code],{system|}[code],...`)
`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]&status={system|}[search_code]{,{system|}[code],...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&advance-directive-observation&status=final

**Implementation Notes**: Fetches a bundle of all US Core Observation ADI Documentation Profile resources for the specified patient and category = "laboratory" and status ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHOULD**support searching using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[category](SearchParameter-us-core-observation-category.md)and[_lastUpdated](SearchParameter-us-core-observation-lastupdated.md)search parameters:
* Including optional support for **AND** search on `_lastUpdated` (e.g.`_lastUpdated=[date]&_lastUpdated=[date]&...`)
* Including support for these `_lastUpdated` comparators: "gt", "lt", "ge", "le"
`GET [base]/Observation?patient={Patient/}[id]&category={system|}[search_code]&_lastUpdated=[dateTime]`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&category=advance-directive-observation&_lastUpdated=ge2024-01-01T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Observation ADI Documentation Profile resources for the specified patient and category and _lastUpdated. See the US Core General Guidance page for [Searching Using lastUpdated]. ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).

1. **SHOULD**support searching laboratory results by code and date (for example, search for all blood glucose lab results since 2019 for a patient) using the combination of[patient](SearchParameter-us-core-observation-patient.md)and[code](SearchParameter-us-core-observation-code.md)and[date](SearchParameter-us-core-observation-date.md)search parameters:
* Including optional support **OR** search on `code` (e.g.`code={system|}[code],{system|}[code],...`)
* Including optional support for **AND** search on `date` (e.g.`date=[date]&date=[date]&...`)
* Including support for these `date` comparators: "gt", "lt", "ge", "le"
`GET [base]/Observation?patient={Patient/}[id]&code={system|}[search_code]{,{system|}[code],...}&date={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
> 
1. GET [base]/Observation?patient=Patient/1137192&code=http://loinc.org|42348-3&date=ge2019-01-01T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Observation ADI Documentation Profile resources for the specified patient and date and report code(s). SHOULD support search by multiple report codes. ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-observation-adi-documentation",
  "extension" : [
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
      "valueInteger" : 2
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-observation-adi-documentation",
  "version" : "0.1.0",
  "name" : "USCoreObservationADIDocumentationProfile",
  "title" : "US Core Observation ADI Documentation Profile",
  "status" : "active",
  "experimental" : false,
  "date" : "2024-09-13",
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
  "description" : "The US Core Observation Advance Directive Information (ADI) Documentation Profile inherits from the FHIR [Observation](https://hl7.org/fhir/R4/observation.html) resource; refer to it for scope and usage definitions. This profile and the [US Core Observation ADI DocumentationReference Profile](StructureDefinition-us-core-adi-documentreference.html) meet the [U.S. Core Data for Interoperability (USCDI)](https://www.healthit.gov/isp/united-states-core-data-interoperability-uscdi) *Advance Directive Observation* Data Element requirements. It is used to communicate whether a person has advance directive information (ADI) and, if one or more documents exist, their location. Examples of advance healthcare directive documents include physician order for life sustaining treatment (POLST), do not resuscitate order (DNR), and medical power of attorney. To communicate the type of advance directive document, the author, the verifier, and other properties, see the US Core ADI DocumentReference Profile. This profile sets minimum expectations for the Observation resource to record, search, and fetch findings about the presence of a patient's advance directives. It specifies which core elements, extensions,  vocabularies, and value sets **SHALL** be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption.",
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
        "short" : "US Core Observation ADI Presence Profile"
      },
      {
        "id" : "Observation.extension:supporting-info",
        "path" : "Observation.extension",
        "sliceName" : "supporting-info",
        "short" : "Relevant ADI documents and information",
        "min" : 0,
        "max" : "*",
        "type" : [
          {
            "code" : "Extension",
            "profile" : [
              "http://hl7.org/fhir/StructureDefinition/workflow-supportingInfo"
            ]
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Observation.extension:supporting-info.value[x]",
        "path" : "Observation.extension.value[x]",
        "short" : "Reference to patient or provider authored ADI documents",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-adi-documentreference",
              "http://hl7.org/fhir/StructureDefinition/Resource"
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
        "mustSupport" : true,
        "binding" : {
          "strength" : "preferred",
          "description" : "FHIR and US Core codes for high level observation categories.",
          "valueSet" : "http://hl7.org/fhir/us/core/ValueSet/us-core-simple-observation-category"
        }
      },
      {
        "id" : "Observation.category:us-core",
        "path" : "Observation.category",
        "sliceName" : "us-core",
        "min" : 0,
        "max" : "1",
        "patternCodeableConcept" : {
          "coding" : [
            {
              "system" : "http://hl7.org/fhir/us/core/CodeSystem/us-core-category",
              "code" : "observation-adi-documentation"
            }
          ]
        },
        "mustSupport" : true,
        "binding" : {
          "strength" : "preferred",
          "description" : "FHIR and US Core codes for high level observation categories.",
          "valueSet" : "http://hl7.org/fhir/us/core/ValueSet/us-core-simple-observation-category"
        }
      },
      {
        "id" : "Observation.code",
        "path" : "Observation.code",
        "short" : "Observation ADI Documentation code",
        "type" : [
          {
            "code" : "CodeableConcept"
          }
        ],
        "patternCodeableConcept" : {
          "coding" : [
            {
              "system" : "http://loinc.org",
              "code" : "45473-6"
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
        "id" : "Observation.issued",
        "path" : "Observation.issued",
        "short" : "Date/Time this observation was made available",
        "mustSupport" : true
      },
      {
        "id" : "Observation.performer",
        "path" : "Observation.performer",
        "comment" : "An `Observation.performer` of type Practitioner or Organization typically made the Observation, and an `Observation.performer` of Patient or RelatedPerson usually is the source of information (for example, a next of kin who answers questions about the patient's advance directives) Systems may use the standard [Performer function Extension ](http://hl7.org/fhir/StructureDefinition/event-performerFunction) to distinguish the type of involvement of the performer in the Observation.",
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
        "type" : [
          {
            "code" : "CodeableConcept"
          }
        ],
        "mustSupport" : true,
        "binding" : {
          "strength" : "required",
          "description" : "Answer Set with Yes No and Unknowns",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.113762.1.4.1267.16"
        }
      }
    ]
  }
}

```
