# US Core Specimen Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Specimen Profile**

## Resource Profile: US Core Specimen Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-specimen | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 3 | *Computable Name*:USCoreSpecimenProfile |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core Specimen Profile inherits from the FHIR[Specimen](https://hl7.org/fhir/R4/specimen.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the Specimen resource to record, search, and fetch information about substances associated with a patient being sampled or tested (such as nasopharyngeal swab, whole blood, or serum). It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. 

**Usages:**

* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md) and [US Core Server CapabilityStatement](CapabilityStatement-us-core-server.md)
* This Profile is not used by any profiles in this Implementation Guide

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-specimen)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-specimen.csv), [Excel](StructureDefinition-us-core-specimen.xlsx), [Schematron](StructureDefinition-us-core-specimen.sch) 

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

Servers providing access to specimen data **SHALL** support these [US Core SMART Scopes]:

* [resource level scopes]: `<patient|user|system>/Specimen.rs`

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-specimen.html

type = Specimen

title = US Core Specimen Profile

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support both read Specimen by`id`**AND**Specimen search using the[_id](SearchParameter-us-core-specimen-id.md)search parameter`GET [base]/Specimen?_id=[id]' or 'GET [base]/Specimen/[id]`Example:
> 
1. GET [base]/Specimen?_id=123

**Implementation Notes**: (see[Parameters for all resources](#.md)).

#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported

1. **SHOULD**support searching for all specimen's for a patient using the[patient](SearchParameter-us-core-specimen-patient.md)search parameter`GET [base]/Specimen?patient={Patient/}[id]`Example:
> 
1. GET [base]/Specimen?patient=1137192

**Implementation Notes**: Fetches a bundle of all US Core Specimen Profile resources for the specified patient ( see[how to search by reference](foo.md)).

#### Including Specimen when searching for an Observation or DiagnosticReport

Servers **MAY** support the [`_include`](http://hl7.org/fhir/R4/search.html#include) parameter to request that additional resources be included in the response of a search query. For example, when searching for an Observation or DiagnosticReport that references Specimen, the Client can use the `_include` parameter to retrieve information about a specimen associated with the search results. The syntax for querying an Observation and the associated Specimen is:

`GET [base]/[Resource-type]?[parameter1]=[value1]{&...}&_include=Observation:specimen`

Example:

GET [base]/Observation?_id=9163726&_include=Observation:specimen



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-specimen",
  "extension" : [
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
      "valueInteger" : 3
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-specimen",
  "version" : "0.1.0",
  "name" : "USCoreSpecimenProfile",
  "title" : "US Core Specimen Profile",
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
  "description" : "The US Core Specimen Profile inherits from the FHIR [Specimen](https://hl7.org/fhir/R4/specimen.html) resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the Specimen resource to record, search, and fetch information about substances associated with a patient being sampled or tested (such as nasopharyngeal swab, whole blood,  or serum). It specifies which core elements, extensions, vocabularies, and value sets **SHALL** be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption.",
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
  "type" : "Specimen",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/Specimen",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "Specimen",
        "path" : "Specimen",
        "mustSupport" : false
      },
      {
        "id" : "Specimen.identifier",
        "path" : "Specimen.identifier",
        "short" : "Specimen identifier",
        "mustSupport" : true
      },
      {
        "id" : "Specimen.accessionIdentifier",
        "path" : "Specimen.accessionIdentifier",
        "mustSupport" : true
      },
      {
        "id" : "Specimen.type",
        "path" : "Specimen.type",
        "min" : 1,
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.113762.1.4.1099.54"
        }
      },
      {
        "id" : "Specimen.subject",
        "path" : "Specimen.subject",
        "short" : "The patient where the specimen came from.",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient",
              "http://hl7.org/fhir/StructureDefinition/Group",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-device",
              "http://hl7.org/fhir/StructureDefinition/Substance",
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
        "id" : "Specimen.collection",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Specimen.collection",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: Collection details"
      },
      {
        "id" : "Specimen.collection.bodySite",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Specimen.collection.bodySite",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: Specimen Source Site",
        "comment" : "Body location from where a specimen was obtained. Examples include but are not limited to right internal jugular, left arm, and right eye.",
        "binding" : {
          "strength" : "extensible",
          "valueSet" : "http://hl7.org/fhir/ValueSet/body-site"
        }
      },
      {
        "id" : "Specimen.condition",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "Specimen.condition",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: Specimen condition",
        "binding" : {
          "strength" : "extensible",
          "valueSet" : "http://hl7.org/fhir/us/core/ValueSet/us-core-specimen-condition"
        }
      }
    ]
  }
}

```
