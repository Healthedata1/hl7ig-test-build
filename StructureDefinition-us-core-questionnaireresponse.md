# US Core QuestionnaireResponse Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core QuestionnaireResponse Profile**

## Resource Profile: US Core QuestionnaireResponse Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-questionnaireresponse | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 3 | *Computable Name*:USCoreQuestionnaireResponseProfile |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core QuestionaireResponse Profile inherits from the[Structured Data Capture (SDC) Questionnaire Response Profile](http://hl7.org/fhir/uv/sdc/STU3/StructureDefinition-sdc-questionnaireresponse.html). This profile sets minimum expectations for the QuestionnaireResponse resource to record, search, and fetch retrieve captures the responses to form/survey and assessment tools such as the**Protocol for Responding to and Assessing Patients\u2019 Assets, Risks, and Experiences (PRAPARE) Survey**. It specifies which core**additional**elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Before reviewing this profile, implementers are encouraged to read the Screening and Assessments guidance page, which documents the process of recording responses and capturing assertions/determinations resulting from surveys and questionnaires. 

**Usages:**

* Refer to this Profile: [US Core Observation Screening Assessment Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-screening-assessment.html), [US Core Simple Observation Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-simple-observation.html) and [US Core Observation Survey Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-observation-survey.html)
* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md), [US Core Server CapabilityStatement](CapabilityStatement-us-core-server.md), [US Core Client CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-client.html) and [US Core Server CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-server.html)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-questionnaireresponse)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-questionnaireresponse.csv), [Excel](StructureDefinition-us-core-questionnaireresponse.xlsx), [Schematron](StructureDefinition-us-core-questionnaireresponse.sch) 

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

Servers providing access to completed questionnnaire, survey and assessement data **SHALL** support these [US Core SMART Scopes]:

* [resource level scopes]: `<patient|user|system>/QuestionnaireResponse.rs`

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-questionnaireresponse.html

type = QuestionnaireResponse

title = US Core QuestionnaireResponse Profile

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support both read QuestionnaireResponse by`id`**AND**QuestionnaireResponse search using the[_id](SearchParameter-us-core-questionnaireresponse-id.md)search parameter`GET [base]/QuestionnaireResponse?_id=[id]' or 'GET [base]/QuestionnaireResponse/[id]`Examples:
> 
1. GET [base]/!QuestionnaireResponse/AHC-HRSN-screening-example
1. GET [base]/!QuestionnaireResponse/?_id=AHC-HRSN-screening-example

**Implementation Notes**: Fetches a US Core QuestionnaireResponse Profile resource or a search Bundle containing a US Core QuestionnaireResponse Profile resource matching the id (see[Parameters for all resources](http://hl7.org/fhir/R4/search.html#all)).
1. **SHALL**support searching for all questionnaireresponses for a patient using the[patient](SearchParameter-us-core-questionnaireresponse-patient.md)search parameter`GET [base]/QuestionnaireResponse?patient={Patient/}[id]`Example:
> 
1. GET [base]/QuestionnaireResponse?patient=Patient/1137192&

**Implementation Notes**: Fetches a bundle of all US Core QuestionnaireResponse Profile resources for the specified patient ( see[how to search by reference](foo.md)).

#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported

1. **SHOULD**combo description field using the combination of the[patient](SearchParameter-us-core-questionnaireresponse-patient.md)and[status](SearchParameter-us-core-questionnaireresponse-status.md)search parameters
* Including support **OR** search on `status` (e.g.`status={system|}[code],{system|}[code],...`)
`GET [base]/QuestionnaireResponse?patient={Patient/}[id]&status={system|}[search_code]{,{system|}[code],...}`Example:
> 
1. GET [base]/QuestionnaireResponse?patient=Patient/1137192&status=completed

**Implementation Notes**: Fetches a bundle of all US Core QuestionnaireResponse Profile resources for the specified patient and status ( see[how to search by reference](foo.md)and[how to search by token](#.md)).
1. **SHOULD**combo description field using the combination of the[patient](SearchParameter-us-core-questionnaireresponse-patient.md)and[authored](SearchParameter-us-core-questionnaireresponse-authored.md)search parameters
* Including optional support for **AND** search on `authored` (e.g.`authored=[date]&authored=[date]&...`)
* Including support for these `authored` comparators: "gt", "lt", "ge", "le"
`GET [base]/QuestionnaireResponse?patient={Patient/}[id]&authored={gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}`Example:
> 
1. GET [base]/QuestionnaireResponse?patient=Patient/1137192&date=ge2021

**Implementation Notes**: Fetches a bundle of all US Core QuestionnaireResponse Profile resources for the specified patient and date ( see[how to search by reference](foo.md)).
1. **SHOULD**combo description field using the combination of the[patient](SearchParameter-us-core-questionnaireresponse-patient.md)and[questionnaire](SearchParameter-us-core-questionnaireresponse-questionnaire.md)search parameters`GET [base]/QuestionnaireResponse?patient={Patient/}[id]&questionnaire={Type/}[id]`Example:
> 
1. GET [base]/QuestionnaireResponse?patient=Patient/1137192&questionnaire=http://hl7.org/fhir/us/sdoh-clinicalcare/Questionnaire/SDOHCC-QuestionnaireHungerVitalSign

**Implementation Notes**: Fetches a bundle of all US Core QuestionnaireResponse Profile resources for the specified patient that have been completed against a specified form. ( see[how to search by reference](foo.md)).

#### Searching QuestionnaireResponse by Context

Searching a patient's QuestionnaireResponses by specific context such as those defined in [US Core Category] can be achieved by querying the metadata on the associated Questionnaire. Specifically, [`Questionnaire.useContext`] with a code="focus" and value of "sdoh"/"functionalStatus"/etc. could be accomplished using a chained search:

`GET [base]/QuestionnaireResponse?subject=Patient/123&questionnaire.context-type-value=focus$sdoh`



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-questionnaireresponse",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-questionnaireresponse",
  "version" : "0.1.0",
  "name" : "USCoreQuestionnaireResponseProfile",
  "title" : "US Core QuestionnaireResponse Profile",
  "status" : "active",
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
  "description" : "The US Core QuestionaireResponse Profile inherits from the [Structured  Data Capture (SDC) Questionnaire Response Profile](http://hl7.org/fhir/uv/sdc/STU3/StructureDefinition-sdc-questionnaireresponse.html).   This profile sets minimum expectations for the QuestionnaireResponse resource to record, search, and fetch retrieve captures the responses to form/survey and assessment tools such as the *Protocol for Responding to and Assessing Patients\\u2019 Assets, Risks, and Experiences (PRAPARE) Survey*.  It specifies which core *additional* elements, extensions, vocabularies, and value sets **SHALL** be present and constrains how the elements are used.  Before reviewing this profile, implementers are encouraged to read the Screening and Assessments guidance page, which documents the process of recording responses and capturing assertions/determinations resulting from surveys and questionnaires.",
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
    }
  ],
  "kind" : "resource",
  "abstract" : false,
  "type" : "QuestionnaireResponse",
  "baseDefinition" : "http://hl7.org/fhir/uv/sdc/StructureDefinition/sdc-questionnaireresponse",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "QuestionnaireResponse",
        "path" : "QuestionnaireResponse",
        "short" : "US Core Profile based on SDC QuestionnaireResponse"
      },
      {
        "id" : "QuestionnaireResponse.questionnaire",
        "path" : "QuestionnaireResponse.questionnaire",
        "mustSupport" : true
      },
      {
        "id" : "QuestionnaireResponse.questionnaire.extension:url",
        "path" : "QuestionnaireResponse.questionnaire.extension",
        "sliceName" : "url",
        "short" : "The location where a non-FHIR questionnaire/survey form can be found.",
        "min" : 0,
        "max" : "1",
        "type" : [
          {
            "code" : "Extension",
            "profile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-extension-questionnaire-uri"
            ]
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "QuestionnaireResponse.status",
        "path" : "QuestionnaireResponse.status",
        "mustSupport" : true
      },
      {
        "id" : "QuestionnaireResponse.subject",
        "path" : "QuestionnaireResponse.subject",
        "comment" : "-",
        "min" : 1,
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient",
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
        "id" : "QuestionnaireResponse.authored",
        "path" : "QuestionnaireResponse.authored",
        "mustSupport" : true
      },
      {
        "id" : "QuestionnaireResponse.author",
        "path" : "QuestionnaireResponse.author",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitioner",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient",
              "http://hl7.org/fhir/StructureDefinition/PractitionerRole",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-device",
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
        "id" : "QuestionnaireResponse.item",
        "path" : "QuestionnaireResponse.item",
        "mustSupport" : true
      },
      {
        "id" : "QuestionnaireResponse.item.linkId",
        "path" : "QuestionnaireResponse.item.linkId",
        "mustSupport" : true
      },
      {
        "id" : "QuestionnaireResponse.item.answer.value[x]",
        "path" : "QuestionnaireResponse.item.answer.value[x]",
        "min" : 0,
        "max" : "1",
        "type" : [
          {
            "code" : "boolean"
          },
          {
            "code" : "date"
          },
          {
            "code" : "dateTime"
          },
          {
            "code" : "time"
          },
          {
            "extension" : [
              {
                "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                "valueBoolean" : true
              }
            ],
            "code" : "decimal"
          },
          {
            "code" : "integer"
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
            "extension" : [
              {
                "url" : "http://hl7.org/fhir/StructureDefinition/elementdefinition-type-must-support",
                "valueBoolean" : true
              }
            ],
            "code" : "Coding"
          },
          {
            "code" : "uri"
          },
          {
            "code" : "Quantity"
          },
          {
            "code" : "Attachment"
          },
          {
            "code" : "Reference"
          }
        ],
        "mustSupport" : true
      }
    ]
  }
}

```
