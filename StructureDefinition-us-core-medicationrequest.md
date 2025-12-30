# US Core MedicationRequest Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core MedicationRequest Profile**

## Resource Profile: US Core MedicationRequest Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-medicationrequest | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreMedicationRequestProfile |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core MedicationRequest Profile inherits from the FHIR[MedicationRequest](https://hl7.org/fhir/R4/medicationrequest.html)resource; refer to it for scope and usage definitions. This profile meets the requirements of the[U.S. Core Data for Interoperability (USCDI)](https://www.healthit.gov/isp/united-states-core-data-interoperability-uscdi)**Medications**Data Class. This profile sets minimum expectations for the MedicationRequest resource to record, search, and fetch a patient's medication prescriptions or orders. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. 

**Usages:**

* Refer to this Profile: [US Core MedicationDispense Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-medicationdispense.html)
* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md), [US Core Server CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-server-liquid.md), [US Core Client CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-client.html) and [US Core Server CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-server.html)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-medicationrequest)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-medicationrequest.csv), [Excel](StructureDefinition-us-core-medicationrequest.xlsx), [Schematron](StructureDefinition-us-core-medicationrequest.sch) 

### Notes:

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-medicationrequest.html

type = MedicationRequest

title = US Core MedicationRequest Profile

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support searching for all medications that have been prescribed to a patient. See the [Medication List Guidance] section for guidance on accessing a patient medications. The server application represents the medication using either an inline code or a contained or external reference to the Medication resource. using the combination of the[patient](SearchParameter-us-core-medicationrequest-patient.md)and[intent](SearchParameter-us-core-medicationrequest-intent.md)search parameters
* Including optional support for these `_include` parameters: `MedicationRequest:medication`
* Including support **OR** search on `intent` (e.g.`intent={system|}[code],{system|}[code],...`)
`GET [base]/MedicationRequest?patient={Patient/}[id]&intent={system|}[search_code]{,{system|}[code],...}`Examples:
> 
1. GET [base]/MedicationRequest?patient=Patient/1137192&intent=order,plan
1. GET [base]/MedicationRequest?patient=Patient/1137192&intent=order,plan&_include=MedicationRequest:medication

**Implementation Notes**: Fetches a bundle of all US Core MedicationRequest Profile resources for the specified patient and intent code = "order,plan" ( see[how to search by reference](foo.md)and[how to search by token](#.md)).
1. **SHALL**support searching for all prescriptions for a patient for a given status (for example all active prescriptions) using the combination of the[patient](SearchParameter-us-core-medicationrequest-patient.md)and[intent](SearchParameter-us-core-medicationrequest-intent.md)and[status](SearchParameter-us-core-medicationrequest-status.md)search parameters
* Including optional support for these `_include` parameters: `MedicationRequest:medication`
* Including support **OR** search on `intent` (e.g.`intent={system|}[code],{system|}[code],...`)
* Including support **OR** search on `status` (e.g.`status={system|}[code],{system|}[code],...`)
`GET [base]/MedicationRequest?patient={Patient/}[id]&intent={system|}[search_code]{,{system|}[code],...}&status={system|}[search_code]{,{system|}[code],...}`Examples:
> 
1. GET [base]/MedicationRequest?patient=Patient/1137192&intent=order,plan&status=active
1. GET [base]/MedicationRequest?patient=Patient/1137192&intent=order,plan&status=active&_include=MedicationRequest:medication

**Implementation Notes**: Fetches a bundle of all US Core MedicationRequest Profile resources for the specified patient and intent code = "order,plan" and status ( see[how to search by reference](foo.md)and[how to search by token](#.md)).

#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported

1. **SHOULD**support searching for all prescriptions for a patient for a given status (for example all active prescriptions) using the combination of the[patient](SearchParameter-us-core-medicationrequest-patient.md)and[intent](SearchParameter-us-core-medicationrequest-intent.md)and[encounter](SearchParameter-us-core-medicationrequest-encounter.md)search parameters
* Including optional support for these `_include` parameters: `MedicationRequest:medication`
* Including support **OR** search on `intent` (e.g.`intent={system|}[code],{system|}[code],...`)
`GET [base]/MedicationRequest?patient={Patient/}[id]&intent={system|}[search_code]{,{system|}[code],...}&encounter={Type/}[id]`Examples:
> 
1. GET [base]/MedicationRequest?patient=Patient/1137192&intent=order,plan&status=active&encounter=Encounter/123
1. GET [base]/MedicationRequest?patient=Patient/1137192&intent=order,plan&status=active&&encounter=Encounter/123&_include=MedicationRequest:medication

**Implementation Notes**: Fetches a bundle of all US Core MedicationRequest Profile resources for the specified patient and intent code = "order,plan" and encounter ( see[how to search by reference](foo.md)and[how to search by token](#.md)).
1. **SHOULD**support searching for all prescriptions for a patient by date using the combination of the[patient](SearchParameter-us-core-medicationrequest-patient.md)and[intent](SearchParameter-us-core-medicationrequest-intent.md)and[authoredon](SearchParameter-us-core-medicationrequest-authoredon.md)search parameters
* Including optional support for these `_include` parameters: `MedicationRequest:medication`
* Including support **OR** search on `intent` (e.g.`intent={system|}[code],{system|}[code],...`)
* Including optional support for **AND** search on `authoredon` (e.g.`authoredon=[date]&authoredon=[date]&...`)
* Including support for these `authoredon` comparators: "gt", "lt", "ge", "le"
`GET [base]/MedicationRequest?patient={Patient/}[id]&intent={system|}[search_code]{,{system|}[code],...}&authoredon={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Examples:
> 
1. GET [base]/MedicationRequest?patient=Patient/1137192&intent=order,plan&authoredon=ge2019-01-01T00:00:00Z
1. GET [base]/MedicationRequest?patient=Patient/1137192&intent=order,plan&authoredon=ge2019-01-01T00:00:00Z&_include=MedicationRequest:medication

**Implementation Notes**: Fetches a bundle of all US Core MedicationRequest Profile resources for the specified patient and intent code = "order,plan" and authoredon date ( see[how to search by reference](foo.md)and[how to search by token](#.md)and[how to search by date](#.md)).



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-medicationrequest",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-medicationrequest",
  "version" : "0.1.0",
  "name" : "USCoreMedicationRequestProfile",
  "title" : "US Core MedicationRequest Profile",
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
  "description" : "The US Core MedicationRequest Profile inherits from the FHIR [MedicationRequest](https://hl7.org/fhir/R4/medicationrequest.html) resource; refer to it for scope and usage definitions. This profile meets the requirements of the [U.S. Core Data for Interoperability (USCDI)](https://www.healthit.gov/isp/united-states-core-data-interoperability-uscdi)  *Medications* Data Class. This profile sets minimum expectations for the MedicationRequest resource to record, search, and fetch a patient's medication prescriptions or orders. It specifies which core elements, extensions, vocabularies, and value sets **SHALL** be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption.",
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
      "identity" : "script10.6",
      "uri" : "http://ncpdp.org/SCRIPT10_6",
      "name" : "Mapping to NCPDP SCRIPT 10.6"
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
  "type" : "MedicationRequest",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/MedicationRequest",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "MedicationRequest",
        "path" : "MedicationRequest",
        "constraint" : [
          {
            "key" : "us-core-21",
            "severity" : "error",
            "human" : "requester SHALL be present if intent is \"order\"",
            "expression" : "(intent='order' or intent='original-order' or intent='reflex-order'or intent='filler-order' or intent='instance-order') implies requester.exists()"
          }
        ],
        "mustSupport" : false,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "MedicationOrder"
          }
        ]
      },
      {
        "id" : "MedicationRequest.extension:medicationAdherence",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "MedicationRequest.extension",
        "sliceName" : "medicationAdherence",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: US Core Medication Adherence Extension",
        "min" : 0,
        "max" : "*",
        "type" : [
          {
            "code" : "Extension",
            "profile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-medication-adherence"
            ]
          }
        ],
        "mustSupport" : false
      },
      {
        "id" : "MedicationRequest.status",
        "path" : "MedicationRequest.status",
        "mustSupport" : true,
        "binding" : {
          "strength" : "required",
          "description" : "A code specifying the state of the prescribing event. Describes the lifecycle of the prescription.",
          "valueSet" : "http://hl7.org/fhir/ValueSet/medicationrequest-status"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "MedicationOrder.status"
          }
        ]
      },
      {
        "id" : "MedicationRequest.intent",
        "path" : "MedicationRequest.intent",
        "condition" : ["us-core-21"],
        "mustSupport" : true,
        "binding" : {
          "strength" : "required",
          "description" : "The kind of medication order.",
          "valueSet" : "http://hl7.org/fhir/ValueSet/medicationrequest-intent"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "MedicationOrder.status"
          }
        ]
      },
      {
        "id" : "MedicationRequest.category",
        "path" : "MedicationRequest.category",
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
        "id" : "MedicationRequest.category:us-core",
        "path" : "MedicationRequest.category",
        "sliceName" : "us-core",
        "mustSupport" : true,
        "binding" : {
          "strength" : "required",
          "description" : "The type of medication order. Note that other codes are permitted, see [Required Bindings When Slicing by Value Sets](general-requirements.html#required-bindings-when-slicing-by-valuesets)",
          "valueSet" : "http://hl7.org/fhir/ValueSet/medicationrequest-category"
        }
      },
      {
        "id" : "MedicationRequest.reported[x]",
        "path" : "MedicationRequest.reported[x]",
        "type" : [
          {
            "extension" : [
              {
                "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                "valueBoolean" : true
              }
            ],
            "code" : "boolean"
          },
          {
            "extension" : [
              {
                "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                "valueBoolean" : true
              }
            ],
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitioner",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitionerrole",
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
              }
            ]
          }
        ],
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "MedicationOrder.status"
          }
        ]
      },
      {
        "id" : "MedicationRequest.medication[x]",
        "path" : "MedicationRequest.medication[x]",
        "type" : [
          {
            "code" : "CodeableConcept"
          },
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-medication"
            ]
          }
        ],
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.113762.1.4.1010.4"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "MedicationOrder.medication[x]"
          }
        ]
      },
      {
        "id" : "MedicationRequest.subject",
        "path" : "MedicationRequest.subject",
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
            "map" : "MedicationOrder.patient"
          }
        ]
      },
      {
        "id" : "MedicationRequest.encounter",
        "path" : "MedicationRequest.encounter",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-encounter"
            ]
          }
        ],
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "NA"
          }
        ]
      },
      {
        "id" : "MedicationRequest.authoredOn",
        "path" : "MedicationRequest.authoredOn",
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "MedicationOrder.dateWritten"
          }
        ]
      },
      {
        "id" : "MedicationRequest.requester",
        "path" : "MedicationRequest.requester",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitioner",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization",
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
        "condition" : ["us-core-21"],
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "MedicationOrder.prescriber"
          }
        ]
      },
      {
        "id" : "MedicationRequest.reasonCode",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "MedicationRequest.reasonCode",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: Reason or indication for ordering or not ordering the medication",
        "binding" : {
          "strength" : "extensible",
          "valueSet" : "http://hl7.org/fhir/us/core/ValueSet/us-core-condition-code"
        }
      },
      {
        "id" : "MedicationRequest.reasonReference",
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
            "valueBoolean" : true
          }
        ],
        "path" : "MedicationRequest.reasonReference",
        "short" : "𝗔𝗗𝗗𝗜𝗧𝗜𝗢𝗡𝗔𝗟 𝗨𝗦𝗖𝗗𝗜: US Core Condition or Observation that supports the prescription"
      },
      {
        "id" : "MedicationRequest.dosageInstruction",
        "path" : "MedicationRequest.dosageInstruction",
        "mustSupport" : true
      },
      {
        "id" : "MedicationRequest.dosageInstruction.text",
        "path" : "MedicationRequest.dosageInstruction.text",
        "mustSupport" : true
      },
      {
        "id" : "MedicationRequest.dosageInstruction.timing",
        "path" : "MedicationRequest.dosageInstruction.timing",
        "mustSupport" : true
      },
      {
        "id" : "MedicationRequest.dosageInstruction.route",
        "path" : "MedicationRequest.dosageInstruction.route",
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "description" : "SNOMED CT and NCI Thesaurus SPL route of administration codes",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.113762.1.4.1267.22"
        }
      },
      {
        "id" : "MedicationRequest.dosageInstruction.doseAndRate",
        "path" : "MedicationRequest.dosageInstruction.doseAndRate",
        "mustSupport" : true
      },
      {
        "id" : "MedicationRequest.dosageInstruction.doseAndRate.dose[x]",
        "path" : "MedicationRequest.dosageInstruction.doseAndRate.dose[x]",
        "short" : "Amount of medication per dose",
        "type" : [
          {
            "extension" : [
              {
                "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                "valueBoolean" : true
              }
            ],
            "code" : "Quantity",
            "profile" : ["http://hl7.org/fhir/StructureDefinition/SimpleQuantity"]
          },
          {
            "code" : "Range"
          }
        ],
        "mustSupport" : true,
        "binding" : {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-maxValueSet",
              "valueCanonical" : "http://hl7.org/fhir/ValueSet/ucum-units"
            }
          ],
          "strength" : "preferred",
          "valueSet" : "http://hl7.org/fhir/ValueSet/ucum-common"
        }
      },
      {
        "id" : "MedicationRequest.dispenseRequest",
        "path" : "MedicationRequest.dispenseRequest",
        "mustSupport" : true
      },
      {
        "id" : "MedicationRequest.dispenseRequest.numberOfRepeatsAllowed",
        "path" : "MedicationRequest.dispenseRequest.numberOfRepeatsAllowed",
        "mustSupport" : true
      },
      {
        "id" : "MedicationRequest.dispenseRequest.quantity",
        "path" : "MedicationRequest.dispenseRequest.quantity",
        "mustSupport" : true
      }
    ]
  }
}

```
