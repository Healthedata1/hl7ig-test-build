# US Core DocumentReference Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core DocumentReference Profile**

## Resource Profile: US Core DocumentReference Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-documentreference | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreDocumentReferenceProfile |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core DocumentReference Profile inherits from the FHIR[DocumentReference](https://hl7.org/fhir/R4/documentreference.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for searching and fetching patient documents including Clinical Notes using the DocumentReference resource. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. Before reviewing this profile, implementers are encouraged to read the Clinical Notes Guidance to understand the overlap of the US Core DiagnosticReport Profile for Report and Note exchange and the US Core DocumentReference Profile. 

**Usages:**

* Refer to this Profile: [US Core Observation Screening Assessment Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-screening-assessment.html), [US Core PMO ServiceRequest Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-pmo-servicerequest.html), [US Core Simple Observation Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-simple-observation.html) and [US Core Observation Survey Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-observation-survey.html)
* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md), [US Core Server CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-server-liquid.md), [US Core Client CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-client.html) and [US Core Server CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-server.html)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-documentreference)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-documentreference.csv), [Excel](StructureDefinition-us-core-documentreference.xlsx), [Schematron](StructureDefinition-us-core-documentreference.sch) 

### Notes:

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-documentreference.html

type = DocumentReference

title = US Core DocumentReference Profile

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support both read DocumentReference by`id`**AND**DocumentReference search using the[_id](SearchParameter-us-core-documentreference-id.md)search parameter:`GET [base]/DocumentReference?_id=[id]' or 'GET [base]/DocumentReference/[id]`Examples:
> 
1. GET [base]/DocumentReference/2169591
1. GET [base]/DocumentReference?_id=2169591

**Implementation Notes**: Fetches a single US Core DocumentReference Profile or a search Bundle containing a US Core DocumentReference Profile resource matching the id. The document itself is represented as a base64 encoded binary data element or retrieved using the link provided by the resource. If the document is a relative link to a [Binary] resource like a resource reference, it can be subsequently retrieved using:`GET [base]/Binary/[id]`. (see [Parameters for all resources]).

1. **SHALL**support searching for all documentreferences for a patient using the[patient](SearchParameter-us-core-documentreference-patient.md)search parameter:`GET [base]/DocumentReference?patient={Patient/}[id]`Example:
> 
1. GET [base]/DocumentReference?patient=Patient/1137192

**Implementation Notes**: Fetches a bundle of all US Core DocumentReference Profile resources for the specified patient. See the implementation notes above for how to access the actual document. ([how to search by reference](foo.md)).

1. **SHALL**support searching for all clinical notes for a given patient using the combination of[patient](SearchParameter-us-core-documentreference-patient.md)and[category](SearchParameter-us-core-documentreference-category.md)search parameters:`GET [base]/DocumentReference?patient={Patient/}[id]&category={system|}[search_code]`Example:
> 
1. GET [base]/DocumentReference?patient=Patient/1137192&category=http://hl7.org/fhir/us/core/CodeSystem/us-core-documentreference-category|clinical-note

**Implementation Notes**: Fetches a bundle of all US Core DocumentReference Profile resources for the specified patient and category = "clinical-note". See the implementation notes above for how to access the actual document. ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHALL**support searching for all clinical notes for a given patient by date (for example, since 2019) using the combination of[patient](SearchParameter-us-core-documentreference-patient.md)and[category](SearchParameter-us-core-documentreference-category.md)and[date](SearchParameter-us-core-documentreference-date.md)search parameters:
* Including optional support for **AND** search on `date` (e.g.`date=[date]&date=[date]&...`)
* Including support for these `date` comparators: "gt", "lt", "ge", "le"
`GET [base]/DocumentReference?patient={Patient/}[id]&category={system|}[search_code]&date={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
> 
1. GET [base]/DocumentReference?patient=Patient/1137192&category=http://hl7.org/fhir/us/core/CodeSystem/us-core-documentreference-category|clinical-note&date=ge2020-01-01T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core DocumentReference Profile resources for the specified patient and category = "clinical-note" and date. See the implementation notes above for how to access the actual document. ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).

1. **SHALL**support searching for a specific note type for a patient using the combination of[patient](SearchParameter-us-core-documentreference-patient.md)and[type](SearchParameter-us-core-documentreference-type.md)search parameters:`GET [base]/DocumentReference?patient={Patient/}[id]&type={system|}[search_code]`Example:
> 
1. GET [base]/DocumentReference?patient=Patient/1137192&type=http://loinc.org|18842-5

**Implementation Notes**: Fetches a bundle of all US Core DocumentReference Profile resources for the specified patient and type. See the implementation notes above for how to access the actual document. ([how to search by reference](foo.md)and ([how to search by token]).

#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported

1. **SHOULD**support searching for all documents for a patient for a given status (for example completed reports ) using the combination of[patient](SearchParameter-us-core-documentreference-patient.md)and[status](SearchParameter-us-core-documentreference-status.md)search parameters:
* Including support **OR** search on `status` (e.g.`status={system|}[code],{system|}[code],...`)
`GET [base]/DocumentReference?patient={Patient/}[id]&status={system|}[search_code]{,{system|}[code],...}`Example:
> 
1. GET [base]/DocumentReference?patient=Patient/1137192&status=completed

**Implementation Notes**: Fetches a bundle of all US Core DocumentReference Profile resources for the specified patient and status. See the implementation notes above for how to access the actual document. ([how to search by reference](foo.md)and ([how to search by token]).

1. **SHOULD**support searching for a document for a patient by type and a clinically relevent date using the combination of[patient](SearchParameter-us-core-documentreference-patient.md)and[type](SearchParameter-us-core-documentreference-type.md)and[period](SearchParameter-us-core-documentreference-period.md)search parameters:
* Including optional support for **AND** search on `period` (e.g.`period=[date]&period=[date]&...`)
* Including support for these `period` comparators: "gt", "lt", "ge", "le"
`GET [base]/DocumentReference?patient={Patient/}[id]&type={system|}[search_code]&period={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
> 
1. GET [base]/DocumentReference?patient=Patient/1137192&type=http://loinc.org|18842-5&period=ge2020-01-01T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core DocumentReference Profile resources for the specified patient and type and period. See the implementation notes above for how to access the actual document. ([how to search by reference](foo.md)and ([how to search by token] and ([how to search by date]).



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-documentreference",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-documentreference",
  "version" : "0.1.0",
  "name" : "USCoreDocumentReferenceProfile",
  "title" : "US Core DocumentReference Profile",
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
  "description" : "The US Core DocumentReference Profile inherits from the FHIR [DocumentReference](https://hl7.org/fhir/R4/documentreference.html) resource; refer to it for scope and usage definitions. This profile sets minimum expectations for searching and fetching patient documents including Clinical Notes using the DocumentReference resource.  It specifies which core elements, extensions, vocabularies, and value sets **SHALL** be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. Before reviewing this profile, implementers are encouraged to read the Clinical Notes Guidance to understand the overlap of the US Core DiagnosticReport Profile for Report and Note exchange and the US Core DocumentReference Profile.",
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
      "identity" : "fhircomposition",
      "uri" : "http://hl7.org/fhir/composition",
      "name" : "FHIR Composition"
    },
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
      "identity" : "xds",
      "uri" : "http://ihe.net/xds",
      "name" : "XDS metadata equivalent"
    }
  ],
  "kind" : "resource",
  "abstract" : false,
  "type" : "DocumentReference",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/DocumentReference",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "DocumentReference",
        "path" : "DocumentReference",
        "mustSupport" : false
      },
      {
        "id" : "DocumentReference.identifier",
        "path" : "DocumentReference.identifier",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.status",
        "path" : "DocumentReference.status",
        "mustSupport" : true,
        "binding" : {
          "strength" : "required",
          "valueSet" : "http://hl7.org/fhir/ValueSet/document-reference-status"
        }
      },
      {
        "id" : "DocumentReference.type",
        "path" : "DocumentReference.type",
        "min" : 1,
        "mustSupport" : true,
        "binding" : {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-minValueSet",
              "valueCanonical" : "http://hl7.org/fhir/us/core/ValueSet/us-core-clinical-note-type"
            }
          ],
          "strength" : "required",
          "description" : "All LOINC  values whose SCALE is \"Doc\" in the LOINC database and the HL7 v3 Code System NullFlavor concept 'unknown'",
          "valueSet" : "http://hl7.org/fhir/us/core/ValueSet/us-core-documentreference-type"
        }
      },
      {
        "id" : "DocumentReference.category",
        "path" : "DocumentReference.category",
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
        "id" : "DocumentReference.category:uscore",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "DocumentReference.category",
        "sliceName" : "uscore",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: Categorization of document",
        "binding" : {
          "strength" : "required",
          "description" : "The US Core DocumentReferences Type Value Set is a \"starter set\" of categories supported for fetching and storing clinical notes. Note that other codes are permitted, see [Required Bindings When Slicing by Value Sets](general-requirements.html#required-bindings-when-slicing-by-valuesets)",
          "valueSet" : "http://hl7.org/fhir/us/core/ValueSet/us-core-documentreference-category"
        }
      },
      {
        "id" : "DocumentReference.subject",
        "path" : "DocumentReference.subject",
        "min" : 1,
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient",
              "http://hl7.org/fhir/StructureDefinition/Practitioner",
              "http://hl7.org/fhir/StructureDefinition/Group",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-device"
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
        "id" : "DocumentReference.date",
        "path" : "DocumentReference.date",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.author",
        "path" : "DocumentReference.author",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitioner",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitionerrole",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-relatedperson",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-device"
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
        "id" : "DocumentReference.content",
        "path" : "DocumentReference.content",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.content.attachment",
        "path" : "DocumentReference.content.attachment",
        "definition" : "The document and format referenced.",
        "comment" : "If there are multiple `DocumentReference.content` element repetitions, these **SHALL** all represent the same document in different format or attachment metadata. The content element **SHALL NOT** contain different versions of the same content. For version handling use multiple DocumentReferences with `DocumentReference.relatesTo`.",
        "constraint" : [
          {
            "key" : "us-core-6",
            "severity" : "error",
            "human" : "DocumentReference.content.attachment.url or DocumentReference.content.attachment.data or both SHALL be present.",
            "expression" : "url.exists() or data.exists()",
            "xpath" : "f:url or f:content"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.content.attachment.contentType",
        "path" : "DocumentReference.content.attachment.contentType",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.content.attachment.data",
        "path" : "DocumentReference.content.attachment.data",
        "min" : 0,
        "condition" : ["us-core-6"],
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.content.attachment.url",
        "path" : "DocumentReference.content.attachment.url",
        "min" : 0,
        "condition" : ["us-core-6"],
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.content.format",
        "path" : "DocumentReference.content.format",
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "valueSet" : "http://terminology.hl7.org/ValueSet/v3-HL7FormatCodes|2.1.0"
        }
      },
      {
        "id" : "DocumentReference.context",
        "path" : "DocumentReference.context",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.context.encounter",
        "path" : "DocumentReference.context.encounter",
        "max" : "1",
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
        "id" : "DocumentReference.context.period",
        "path" : "DocumentReference.context.period",
        "mustSupport" : true
      }
    ]
  }
}

```
