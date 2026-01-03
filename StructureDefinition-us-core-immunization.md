# US Core Immunization Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Immunization Profile**

## Resource Profile: US Core Immunization Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-immunization | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreImmunizationProfile |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core Immunization Profile inherits from the FHIR[Immunization](https://hl7.org/fhir/R4/immunization.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the Immunization resource to record, search, and fetch immunization history associated with a patient. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. 

**Usages:**

* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md), [US Core Server CapabilityStatement](CapabilityStatement-us-core-server.md), [US Core Client CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-client.html) and [US Core Server CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-server.html)
* This Profile is not used by any profiles in this Implementation Guide

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-immunization)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-immunization.csv), [Excel](StructureDefinition-us-core-immunization.xlsx), [Schematron](StructureDefinition-us-core-immunization.sch) 

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

Servers providing access to immunization data **SHALL** support these [US Core SMART Scopes]:

* [resource level scopes]: `<patient|user|system>/Immunization.rs`

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-immunization.html

type = Immunization

title = US Core Immunization Profile

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support searching for all immunizations for a patient using the[patient](SearchParameter-us-core-immunization-patient.md)search parameter`GET [base]/Immunization?patient={Patient/}[id]`Example:
> 
1. GET [base]/Immunization?patient=Patient/1137192

**Implementation Notes**: Fetches a bundle of all US Core Immunization Profile resources for the specified patient ( see[how to search by reference](foo.md)).

#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported

1. **SHOULD**support searching for all immunizations for a patient for a specified time period using the combination of the[patient](SearchParameter-us-core-immunization-patient.md)and[date](SearchParameter-us-core-immunization-date.md)search parameters
* Including optional support for **AND** search on `date` (e.g.`date=[date]&date=[date]&...`)
* Including support for these `date` comparators: "gt", "lt", "ge", "le"
`GET [base]/Immunization?patient={Patient/}[id]&date={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
> 
1. GET [base]/Immunization?patient=Patient/1137192&date=ge2019-01-14T00:00:00Z

**Implementation Notes**: Fetches a bundle of all US Core Immunization Profile resources for the specified patient and date ( see[how to search by reference](foo.md)and[how to search by date](#.md)).
1. **SHOULD**support searching for all administered immunizations for a patient using the combination of the[patient](SearchParameter-us-core-immunization-patient.md)and[status](SearchParameter-us-core-immunization-status.md)search parameters`GET [base]/Immunization?patient={Patient/}[id]&status={system|}[search_code]`Example:
> 
1. GET [base]/Immunization?patient=Patient/1137192&status=completed

**Implementation Notes**: Fetches a bundle of all US Core Immunization Profile resources for the specified patient and status ( see[how to search by reference](foo.md)and[how to search by token](#.md)).

-------

1 Although the CVX code system contains some concepts that are procedures, medications, or substances rather than immunizations, the value set defined in VSAC has removed those and retained only the vaccine codes (see the exclusion definition in VSAC for more detail)



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-immunization",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-immunization",
  "version" : "0.1.0",
  "name" : "USCoreImmunizationProfile",
  "title" : "US Core Immunization Profile",
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
  "description" : "The US Core Immunization Profile inherits from the FHIR [Immunization](https://hl7.org/fhir/R4/immunization.html) resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the Immunization resource to record, search, and fetch immunization history associated with a patient. It specifies which core elements, extensions, vocabularies, and value sets **SHALL** be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption.",
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
    },
    {
      "identity" : "cda",
      "uri" : "http://hl7.org/v3/cda",
      "name" : "CDA (R2)"
    }
  ],
  "kind" : "resource",
  "abstract" : false,
  "type" : "Immunization",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/Immunization",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "Immunization",
        "path" : "Immunization",
        "constraint" : [
          {
            "extension" : [
              {
                "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-bestpractice",
                "valueBoolean" : true
              }
            ],
            "key" : "us-core-5",
            "severity" : "warning",
            "human" : "SHOULD have an additional coding to the NDC value set",
            "expression" : "vaccineCode.coding.where(system='http://hl7.org/fhir/sid/cvx').exists() implies vaccineCode.coding.where(system='http://hl7.org/fhir/sid/ndc').exists()",
            "xpath" : "(exists(f:vaccineCode/f:coding/f:system[@value='http://hl7.org/fhir/sid/ndc']) and exists(f:vaccineCode/f:coding/f:system[@value='http://hl7.org/fhir/sid/cvx'])) or exists(f:vaccineCode/f:coding/f:system[@value='http://hl7.org/fhir/sid/cvx'])not()"
          }
        ],
        "mustSupport" : false,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Immunization"
          }
        ]
      },
      {
        "id" : "Immunization.status",
        "path" : "Immunization.status",
        "mustSupport" : true,
        "binding" : {
          "strength" : "required",
          "valueSet" : "http://hl7.org/fhir/ValueSet/immunization-status"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Immunization.status"
          }
        ]
      },
      {
        "id" : "Immunization.statusReason",
        "path" : "Immunization.statusReason",
        "mustSupport" : true,
        "binding" : {
          "strength" : "example",
          "valueSet" : "http://hl7.org/fhir/ValueSet/immunization-status-reason"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Immunization.wasNotGiven"
          }
        ]
      },
      {
        "id" : "Immunization.vaccineCode",
        "path" : "Immunization.vaccineCode",
        "short" : "Vaccine Product Type (bind to CVX)",
        "condition" : ["us-core-5"],
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.113762.1.4.1010.6"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Immunization.vaccineCode"
          }
        ]
      },
      {
        "id" : "Immunization.patient",
        "path" : "Immunization.patient",
        "alias" : ["Patient"],
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient"
            ]
          }
        ],
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Immunization.patient"
          }
        ]
      },
      {
        "id" : "Immunization.encounter",
        "path" : "Immunization.encounter",
        "short" : "Encounter the immunization was part of",
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
        "id" : "Immunization.occurrence[x]",
        "path" : "Immunization.occurrence[x]",
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
            "code" : "string"
          }
        ],
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Immunization.date"
          }
        ]
      },
      {
        "id" : "Immunization.primarySource",
        "path" : "Immunization.primarySource",
        "definition" : "Indicates whether the data contained in the resource was captured by the individual/organization which was responsible for the administration of the vaccine rather than as 'secondary reported' data  documented by a third party. A value of 'true' means this data originated with the individual/organization which was responsible for the administration of the vaccine.",
        "comment" : "This updated definition is adopted from the FHIR R5 Immunization resource.",
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "Immunization.reported"
          }
        ]
      },
      {
        "id" : "Immunization.location",
        "path" : "Immunization.location",
        "short" : "Where the vaccine was administered",
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
        "id" : "Immunization.lotNumber",
        "path" : "Immunization.lotNumber",
        "mustSupport" : true
      },
      {
        "id" : "Immunization.performer",
        "path" : "Immunization.performer",
        "mustSupport" : true
      },
      {
        "id" : "Immunization.performer.actor",
        "path" : "Immunization.performer.actor",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitioner",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitionerrole",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization"
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
      }
    ]
  }
}

```
