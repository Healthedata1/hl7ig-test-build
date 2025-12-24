# US Core CareTeam Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core CareTeam Profile**

## Resource Profile: US Core CareTeam Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-careteam | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreCareTeam |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core CareTeam Profile inherits from the FHIR[CareTeam](https://hl7.org/fhir/R4/careteam.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the CareTeam resource for identifying the Care Team members associated with a patient to promote interoperability and adoption through common implementation. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present in the resource and how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. 

**Usages:**

* Refer to this Profile: [US Core CarePlan Profile](StructureDefinition-us-core-careplan.md), [US Core CareTeam Profile](StructureDefinition-us-core-careteam.md), [US Core Average Blood Pressure Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-average-blood-pressure.html), [US Core Care Experience Preference Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-care-experience-preference.html)...Show 13 more,[US Core Observation ADI Documentation Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-adi-documentation.html),[US Core Observation Clinical Result Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-clinical-result.html),[US Core Observation Occupation Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-occupation.html),[US Core Observation Pregnancy Intent Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-pregnancyintent.html),[US Core Observation Pregnancy Status Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-pregnancystatus.html),[US Core Observation Screening Assessment Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-screening-assessment.html),[US Core Simple Observation Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-simple-observation.html),[US Core Treatment Intervention Preference Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-treatment-intervention-preference.html),[US Core CareTeam Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-careteam.html),[US Core DiagnosticReport Profile for Laboratory Results Reporting](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-diagnosticreport-lab.html),[US Core DiagnosticReport Profile for Report and Note Exchange](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-diagnosticreport-note.html),[US Core Observation Social History Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-observation-social-history.html)and[US Core Observation Survey Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-observation-survey.html)
* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md), [US Core Server CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-server-liquid.md), [US Core Client CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-client.html) and [US Core Server CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-server.html)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-careteam)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-careteam.csv), [Excel](StructureDefinition-us-core-careteam.xlsx), [Schematron](StructureDefinition-us-core-careteam.sch) 

### Notes:

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-careteam.html

type = CareTeam

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support searching using the combination of`[patient]`and`[status]`search parameters:
* **SHOULD** support these `_include` parameters: `CareTeam:participant:PractitionerRole`, `CareTeam:participant:Practitioner`, `CareTeam:participant:Patient`, `CareTeam:participant:RelatedPerson`
* **SHOULD** support **OR** search on `status` (e.g.`status={system|}[code],{system|}[code],...`)
`GET [base]/CareTeam?patient=[Type]/[id]&status={system}|[search_code]{,{system|}[code],...}`Example:
1. GET [base]/CareTeam?patient=1137192&status=active
1. GET [base]/CareTeam?patient=1137192&status=active&_include=CareTeam:participant:RelatedPerson&_include=CareTeam:participant:Patient&_include=CareTeam:participant:Practitioner&_include=CareTeam:participant:PractitionerRole
**Implementation Notes**: Fetches a bundle of all CareTeam resources for the specified patient and status =`active`and may include CareTeam Patient, RelatedPerson and Practitioner and PractitionerRole participants.
To get Practitioner name and identifier using PractitionerRole:
1) Search for the careteam PractitionerRole: GET [base]/CareTeam?patient=[id]&status=active&_include=CareTeam:participant:PractitionerRole
2) using the FHIR _id from the PractitionerRole.practitioner element resource, fetch the Practitioner resources using GET [base]/Practitioner?_id=[id] ([how to search by reference](foo.md)and ([how to search by token])

#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported

1. **SHOULD**support searching a careteam by participant role:
* **SHOULD** support **OR** search on `role` (e.g.`role={system|}[code],{system|}[code],...`)
`GET [base]/CareTeam?role={system}|[search_code]{,{system|}[code],...}`Example:
1. GET [base]/CareTeam?role=http://snomed.info/sct|17561000
**Implementation Notes**: ([how to search by token])
1. **SHOULD**support searching using the combination of`[patient]`and`[role]`search parameters:
* **SHOULD** support these `_include` parameters: `CareTeam:participant:PractitionerRole`, `CareTeam:participant:Practitioner`, `CareTeam:participant:Patient`, `CareTeam:participant:RelatedPerson`
* **SHOULD** support **OR** search on `role` (e.g.`role={system|}[code],{system|}[code],...`)
`GET [base]/CareTeam?patient=[Type]/[id]&role={system}|[search_code]{,{system|}[code],...}`Example:
1. GET [base]/CareTeam?patient=1137192&role=http://snomed.info/sct|17561000
**Implementation Notes**: Fetches a bundle of all CareTeam resources for the specified patient and participant role ([how to search by reference](foo.md)and ([how to search by token])



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-careteam",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-careteam",
  "version" : "0.1.0",
  "name" : "USCoreCareTeam",
  "title" : "US Core CareTeam Profile",
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
  "description" : "The US Core CareTeam Profile inherits from the FHIR [CareTeam](https://hl7.org/fhir/R4/careteam.html) resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the CareTeam resource for identifying the Care Team members associated with a patient to promote interoperability and adoption through common implementation. It specifies which core elements, extensions, vocabularies, and value sets **SHALL** be present in the resource and how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption.",
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
      "identity" : "rim",
      "uri" : "http://hl7.org/v3",
      "name" : "RIM Mapping"
    }
  ],
  "kind" : "resource",
  "abstract" : false,
  "type" : "CareTeam",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/CareTeam",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "CareTeam",
        "path" : "CareTeam",
        "mustSupport" : false,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "CareTeam"
          }
        ]
      },
      {
        "id" : "CareTeam.status",
        "path" : "CareTeam.status",
        "mustSupport" : true,
        "binding" : {
          "strength" : "required",
          "description" : "Indicates whether the team is current , represents future intentions or is now a historical record.",
          "valueSet" : "http://hl7.org/fhir/ValueSet/care-team-status"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "CarePlan.status"
          }
        ]
      },
      {
        "id" : "CareTeam.subject",
        "path" : "CareTeam.subject",
        "min" : 1,
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
        "id" : "CareTeam.participant",
        "path" : "CareTeam.participant",
        "min" : 1,
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "CarePlan.participant"
          }
        ]
      },
      {
        "id" : "CareTeam.participant.role",
        "path" : "CareTeam.participant.role",
        "min" : 1,
        "max" : "1",
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "description" : "Indicates specific responsibility of an individual within the care team, such as Primary physician, Team coordinator, Caregiver, etc.",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.113762.1.4.1099.30"
        },
        "mapping" : [
          {
            "identity" : "argonaut-dq-dstu2",
            "map" : "CarePlan.participant.role"
          }
        ]
      },
      {
        "id" : "CareTeam.participant.member",
        "path" : "CareTeam.participant.member",
        "min" : 1,
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitioner",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-patient",
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitionerrole",
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
                    "valueBoolean" : true
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
            "map" : "CarePlan.participant.member"
          }
        ]
      }
    ]
  }
}

```
