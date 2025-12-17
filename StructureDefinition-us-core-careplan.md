# US Core CarePlan Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core CarePlan Profile**

## Resource Profile: US Core CarePlan Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-careplan | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 4 | *Computable Name*:USCoreCarePlanProfile |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core CarePlan Profile inherits from the FHIR[CarePlan](https://hl7.org/fhir/R4/careplan.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the CarePlan resource to record, search, and fetch assessment and plan of treatment data associated with a patient. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. 

**Usages:**

* CapabilityStatements using this Profile: [US Core Client CapabilityStatement](CapabilityStatement-us-core-client.md), [US Core Client CapabilityStatement2](CapabilityStatement-us-core-client2.md), [US Core Server CapabilityStatement](CapabilityStatement-us-core-server.md), [US Core Server UsCoreServerCapabilityStatement2](CapabilityStatement-us-core-server2.md)...Show 2 more,[US Core Client CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-client.html)and[US Core Server CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-server.html)
* This Profile is not used by any profiles in this Implementation Guide

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-careplan)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-careplan.csv), [Excel](StructureDefinition-us-core-careplan.xlsx), [Schematron](StructureDefinition-us-core-careplan.sch) 



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-careplan",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-careplan",
  "version" : "0.1.0",
  "name" : "USCoreCarePlanProfile",
  "title" : "US Core CarePlan Profile",
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
  "description" : "The US Core CarePlan Profile inherits from the FHIR [CarePlan](https://hl7.org/fhir/R4/careplan.html) resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the CarePlan resource to record,  search, and fetch assessment and plan of treatment data associated with a patient. It specifies which core elements, extensions, vocabularies, and value sets **SHALL** be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption.",
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
  "type" : "CarePlan",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/CarePlan",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "CarePlan",
        "path" : "CarePlan",
        "mustSupport" : false,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "CarePlan"
          }
        ]
      },
      {
        "id" : "CarePlan.text",
        "path" : "CarePlan.text",
        "short" : "Text summary of the resource, for human interpretation",
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "CarePlan.text"
          }
        ]
      },
      {
        "id" : "CarePlan.text.status",
        "path" : "CarePlan.text.status",
        "short" : "generated | additional",
        "mustSupport" : true,
        "binding" : {
          "strength" : "required",
          "description" : "Constrained value set of narrative statuses.",
          "valueSet" : "http://hl7.org/fhir/us/core/ValueSet/us-core-narrative-status"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "CarePlan.text.status"
          }
        ]
      },
      {
        "id" : "CarePlan.text.div",
        "path" : "CarePlan.text.div",
        "short" : "Limited xhtml content",
        "mustSupport" : true
      },
      {
        "id" : "CarePlan.status",
        "path" : "CarePlan.status",
        "requirements" : "Indicates whether the plan is currently being acted upon, represents future intentions or is now a historical record.",
        "mustSupport" : true,
        "binding" : {
          "strength" : "required",
          "description" : "Indicates whether the plan is currently being acted upon, represents future intentions or is now a historical record.",
          "valueSet" : "http://hl7.org/fhir/ValueSet/request-status"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "CarePlan.status"
          }
        ]
      },
      {
        "id" : "CarePlan.intent",
        "path" : "CarePlan.intent",
        "mustSupport" : true,
        "binding" : {
          "strength" : "required",
          "description" : "Codes indicating the degree of authority/intentionality associated with a care plan",
          "valueSet" : "http://hl7.org/fhir/ValueSet/care-plan-intent"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "NA (new element in STU3)"
          }
        ]
      },
      {
        "id" : "CarePlan.category",
        "path" : "CarePlan.category",
        "definition" : "Type of plan.",
        "requirements" : "Identifies what \"kind\" of plan this is to support differentiation between multiple co-existing plans; e.g., \"Home health\", \"psychiatric\", \"asthma\", \"disease management\", \"wellness plan\", etc.",
        "min" : 0,
        "mustSupport" : true,
        "binding" : {
          "strength" : "preferred",
          "valueSet" : "http://hl7.org/fhir/ValueSet/care-plan-category"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "CarePlan.category"
          }
        ]
      },
      {
        "id" : "CarePlan.subject",
        "path" : "CarePlan.subject",
        "definition" : "Who care plan is for.",
        "requirements" : "Identifies the patient or group whose intended care is described by the plan.",
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
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "CarePlan.subject"
          }
        ]
      },
      {
        "id" : "CarePlan.contributor",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "CarePlan.contributor",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: Who provided the content of the care plan",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitioner",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient",
              "http://hl7.org/fhir/StructureDefinition/PractitionerRole",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-careteam",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-relatedperson",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-device"
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
        "id" : "CarePlan.addresses",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "CarePlan.addresses",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: Health issues this plan addresses",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-condition-problems-health-concerns"
            ]
          }
        ],
        "mustSupport" : false
      }
    ]
  }
}

```
