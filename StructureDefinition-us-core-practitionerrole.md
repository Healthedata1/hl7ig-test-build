# US Core PractitionerRole Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core PractitionerRole Profile**

## Resource Profile: US Core PractitionerRole Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitionerrole | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCorePractitionerRoleProfile |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core PractitionerRole Profile inherits from the FHIR[PractitionerRole](https://hl7.org/fhir/R4/practitionerrole.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the PractitionerRole Resource to record, search, and fetch the practitioner role information. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. The requirements for the US Core Practitioner were drawn from the[Argonaut Provider Directory](http://www.fhir.org/guides/argonaut/pd//release1/index.html),[IHE Healthcare Provider Directory](http://ihe.net/uploadedFiles/Documents/ITI/IHE_ITI_Suppl_HPD.pdf)and the[ONC Provider Directory Workshop](https://confluence.oncprojectracking.org/display/PDW/Workshop+Documents). 

**Usages:**

* Refer to this Profile: [US Core ADI DocumentReference Profile](StructureDefinition-us-core-adi-documentreference.md), [US Core DocumentReference Profile](StructureDefinition-us-core-documentreference.md), [US Core Encounter Profile](StructureDefinition-us-core-encounter.md), [US Core Immunization Profile](StructureDefinition-us-core-immunization.md)...Show 10 more,[US Core MedicationRequest Profile](StructureDefinition-us-core-medicationrequest.md),[US Core FamilyMemberHistory Recorder Extension](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-familymemberhistory-recorder.html),[US Core MedicationDispense Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-medicationdispense.html),[US Core CareTeam Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-careteam.html),[US Core DiagnosticReport Profile for Laboratory Results Reporting](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-diagnosticreport-lab.html),[US Core DiagnosticReport Profile for Report and Note Exchange](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-diagnosticreport-note.html),[US Core DocumentReference Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-documentreference.html),[US Core Encounter Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-encounter.html),[US Core MedicationRequest Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-medicationrequest.html)and[US Core Provenance Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-provenance.html)
* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md), [US Core Server CapabilityStatement](CapabilityStatement-us-core-server.md), [US Core Client CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-client.html) and [US Core Server CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-server.html)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-practitionerrole)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-practitionerrole.csv), [Excel](StructureDefinition-us-core-practitionerrole.xlsx), [Schematron](StructureDefinition-us-core-practitionerrole.sch) 

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

Servers providing access to practitioner role data **SHALL** support these [US Core SMART Scopes]:

* [resource level scopes]: `<patient|user|system>/PractitionerRole.rs`

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-practitionerrole.html

type = PractitionerRole

title = US Core PractitionerRole Profile

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support searching practitioner role by practitioner name and identifier using chained parameters using the[practitioner](SearchParameter-us-core-practitionerrole-practitioner.md)search parameter
* Including support for these chained parameters: `practitioner.identifier,name`
* Including optional support for these `_include` parameters: `PractitionerRole:endpoint`, `PractitionerRole:practitioner`
`GET [base]/PractitionerRole?practitioner={Type/}[id]`Examples:
> 
1. GET [base]/PractitionerRole?practitioner.identifier=http://hl7.org/fhir/sid/us-npi|97860456&_include=PractitionerRole:practitioner&_include=PractitionerRole:endpoint
1. GET [base]/PractitionerRole?practitioner.name=Henry&_include=PractitionerRole:practitioner&_include=PractitionerRole:endpoint

**Implementation Notes**: Fetches a bundle containing US Core PractitionerRole Profile resources matching the chained parameter practitioner.name or practitioner.identifier. SHOULD support the _include parameters ( see[how to search by reference](foo.md)).
1. **SHALL**support searching practitioner role by specialty using the[specialty](SearchParameter-us-core-practitionerrole-specialty.md)search parameter
* Including optional support for these `_include` parameters: `PractitionerRole:endpoint`, `PractitionerRole:practitioner`
`GET [base]/PractitionerRole?specialty={system|}[search_code]`Example:
> 
1. GET [base]/PractitionerRole?specialty=http://nucc.org/provider-taxonomy|208D0000X

**Implementation Notes**: Fetches a bundle containing US Core PractitionerRole Profile resources matching the specialty ( see[how to search by token](#.md)).



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-practitionerrole",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitionerrole",
  "version" : "0.1.0",
  "name" : "USCorePractitionerRoleProfile",
  "title" : "US Core PractitionerRole Profile",
  "status" : "active",
  "experimental" : false,
  "date" : "2022-04-20",
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
  "description" : "The US Core PractitionerRole Profile inherits from the FHIR [PractitionerRole](https://hl7.org/fhir/R4/practitionerrole.html) resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the PractitionerRole Resource to record, search, and fetch the practitioner role information. It specifies which core elements, extensions, vocabularies, and value sets **SHALL** be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. The requirements for the US Core Practitioner were drawn from the [Argonaut Provider Directory](http://www.fhir.org/guides/argonaut/pd//release1/index.html),  [IHE Healthcare Provider Directory](http://ihe.net/uploadedFiles/Documents/ITI/IHE_ITI_Suppl_HPD.pdf)  and the [ONC Provider Directory Workshop](https://confluence.oncprojectracking.org/display/PDW/Workshop+Documents).",
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
      "identity" : "servd",
      "uri" : "http://www.omg.org/spec/ServD/1.0/",
      "name" : "ServD"
    },
    {
      "identity" : "w5",
      "uri" : "http://hl7.org/fhir/fivews",
      "name" : "FiveWs Pattern Mapping"
    }
  ],
  "kind" : "resource",
  "abstract" : false,
  "type" : "PractitionerRole",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/PractitionerRole",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "PractitionerRole",
        "path" : "PractitionerRole",
        "constraint" : [
          {
            "key" : "pd-1",
            "severity" : "error",
            "human" : "SHALL have contact information or a reference to an Endpoint",
            "expression" : "telecom.exists() or endpoint.exists()",
            "xpath" : "exists(f:telecom) or exists(f:endpoint)"
          },
          {
            "key" : "us-core-13",
            "severity" : "error",
            "human" : "SHALL have a practitioner, an organization, a healthcare service, or a location.",
            "expression" : "practitioner.exists() or organization.exists() or healthcareService.exists() or location.exists()",
            "xpath" : "exists(f:practitioner) or exists(f:organization) or exists(f:healthcareService) or exists(f:location)"
          }
        ],
        "mustSupport" : false
      },
      {
        "id" : "PractitionerRole.practitioner",
        "path" : "PractitionerRole.practitioner",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-practitioner"
            ]
          }
        ],
        "condition" : ["us-core-13"],
        "mustSupport" : true
      },
      {
        "id" : "PractitionerRole.organization",
        "path" : "PractitionerRole.organization",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization"
            ]
          }
        ],
        "condition" : ["us-core-13"],
        "mustSupport" : true
      },
      {
        "id" : "PractitionerRole.code",
        "path" : "PractitionerRole.code",
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "description" : "Indicates specific responsibility of an individual within the care team, such as Primary physician, Team coordinator, Caregiver, etc.",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.113762.1.4.1099.30"
        }
      },
      {
        "id" : "PractitionerRole.specialty",
        "path" : "PractitionerRole.specialty",
        "mustSupport" : true,
        "binding" : {
          "extension" : [
            {
              "extension" : [
                {
                  "url" : "key",
                  "valueId" : "us-core-snomedct-specialty"
                },
                {
                  "url" : "purpose",
                  "valueCode" : "preferred"
                },
                {
                  "url" : "valueSet",
                  "valueCanonical" : "http://hl7.org/fhir/ValueSet/c80-practice-codes"
                },
                {
                  "url" : "documentation",
                  "valueMarkdown" : "Support exchanges that use SNOMED CT medical specialty codes, such Direct Secure Messaging"
                },
                {
                  "url" : "shortDoco",
                  "valueString" : "Support exchanges that use SNOMED CT medical specialty codes"
                }
              ],
              "url" : "http://hl7.org/fhir/tools/StructureDefinition/additional-binding"
            }
          ],
          "strength" : "extensible",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.114222.4.11.1066"
        }
      },
      {
        "id" : "PractitionerRole.location",
        "path" : "PractitionerRole.location",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "http://hl7.org/fhir/us/core/StructureDefinition/us-core-location"
            ]
          }
        ],
        "condition" : ["us-core-13"],
        "mustSupport" : true
      },
      {
        "id" : "PractitionerRole.healthcareService",
        "path" : "PractitionerRole.healthcareService",
        "condition" : ["us-core-13"]
      },
      {
        "id" : "PractitionerRole.telecom",
        "path" : "PractitionerRole.telecom",
        "condition" : ["pd-1"],
        "mustSupport" : true
      },
      {
        "id" : "PractitionerRole.telecom.system",
        "path" : "PractitionerRole.telecom.system",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "code"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "PractitionerRole.telecom.value",
        "path" : "PractitionerRole.telecom.value",
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
        "id" : "PractitionerRole.endpoint",
        "path" : "PractitionerRole.endpoint",
        "condition" : ["pd-1"],
        "mustSupport" : true
      }
    ]
  }
}

```
