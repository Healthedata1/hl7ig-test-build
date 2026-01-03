# US Core Organization Profile - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Organization Profile**

## Resource Profile: US Core Organization Profile 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreOrganizationProfile |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
The US Core Organization Profile inherits from the FHIR[Organization](https://hl7.org/fhir/R4/organization.html)resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the Organization resource to record, search, and fetch patient or provider organziation information. It specifies which core elements, extensions, vocabularies, and value sets**SHALL**be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption. 

**Usages:**

* Refer to this Profile: [US Core ADI DocumentReference Profile](StructureDefinition-us-core-adi-documentreference.md), [US Core DocumentReference Profile](StructureDefinition-us-core-documentreference.md), [US Core Encounter Profile](StructureDefinition-us-core-encounter.md), [US Core Immunization Profile](StructureDefinition-us-core-immunization.md)...Show 30 more,[US Core MedicationRequest Profile](StructureDefinition-us-core-medicationrequest.md),[US Core Observation Pregnancy Status Profile](StructureDefinition-us-core-observation-pregnancystatus.md),[US Core PractitionerRole Profile](StructureDefinition-us-core-practitionerrole.md),[US Core QuestionnaireResponse Profile](StructureDefinition-us-core-questionnaireresponse.md),[US Core Vital Signs Profile](StructureDefinition-us-core-vital-signs.md),[US Core Average Blood Pressure Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-average-blood-pressure.html),[US Core Care Experience Preference Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-care-experience-preference.html),[US Core Coverage Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-coverage.html),[US Core MedicationDispense Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-medicationdispense.html),[US Core Observation ADI Documentation Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-adi-documentation.html),[US Core Observation Clinical Result Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-clinical-result.html),[US Core Observation Occupation Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-occupation.html),[US Core Observation Pregnancy Intent Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-pregnancyintent.html),[US Core Observation Screening Assessment Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-observation-screening-assessment.html),[US Core PMO ServiceRequest Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-pmo-servicerequest.html),[US Core Simple Observation Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-simple-observation.html),[US Core Treatment Intervention Preference Profile](http://hl7.org/fhir/us/core/2026Jan/StructureDefinition-us-core-treatment-intervention-preference.html),[US Core CareTeam Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-careteam.html),[US Core DiagnosticReport Profile for Laboratory Results Reporting](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-diagnosticreport-lab.html),[US Core DiagnosticReport Profile for Report and Note Exchange](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-diagnosticreport-note.html),[US Core DocumentReference Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-documentreference.html),[US Core Encounter Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-encounter.html),[US Core Location Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-location.html),[US Core MedicationRequest Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-medicationrequest.html),[US Core Observation Social History Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-observation-social-history.html),[US Core Observation Survey Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-observation-survey.html),[US Core PractitionerRole Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-practitionerrole.html),[US Core Provenance Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-provenance.html),[US Core QuestionnaireResponse Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-questionnaireresponse.html)and[US Core ServiceRequest Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-servicerequest.html)
* CapabilityStatements using this Profile: [US Core Client CapabilityStatement Liquid Rendered](CapabilityStatement-us-core-client-liquid.md), [US Core Server CapabilityStatement](CapabilityStatement-us-core-server.md), [US Core Client CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-client.html) and [US Core Server CapabilityStatement](http://hl7.org/fhir/us/core/STU5.0.1/CapabilityStatement-us-core-server.html)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-organization)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-organization.csv), [Excel](StructureDefinition-us-core-organization.xlsx), [Schematron](StructureDefinition-us-core-organization.sch) 

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

Servers providing access to organization data **SHALL** support these [US Core SMART Scopes]:

* [resource level scopes]: `<patient|user|system>/Organization.rs`

-------

**LIQUID SCRIPT**

establish the page context and get type

page.path = StructureDefinition-us-core-organization.html

type = Organization

title = US Core Organization Profile

then run through the csv file for all the data

#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

1. **SHALL**support searching organization based on text address using the[address](SearchParameter-us-core-organization-address.md)search parameter`GET [base]/Organization?address=[address]`Example:
> 
1. GET [base]/Organization?address=Ann%20Arbor

**Implementation Notes**: Fetches a bundle of all US Core Organization Profile resources that match the address string ( see [how to search by string]).
1. **SHALL**support searching by organization name using the[name](SearchParameter-us-core-organization-name.md)search parameter`GET [base]/Organization?name=[name]`Example:
> 
1. GET [base]/Organization?name=ACME%20Labs

**Implementation Notes**: Fetches a bundle of all US Core Organization Profile resources that match the name ( see [how to search by string]).



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-organization",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-organization",
  "version" : "0.1.0",
  "name" : "USCoreOrganizationProfile",
  "title" : "US Core Organization Profile",
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
  "description" : "The US Core Organization Profile inherits from the FHIR [Organization](https://hl7.org/fhir/R4/organization.html) resource; refer to it for scope and usage definitions. This profile sets minimum expectations for the Organization resource to record, search, and fetch patient or provider organziation information. It specifies which core elements, extensions, vocabularies, and value sets **SHALL** be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption.",
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
  "type" : "Organization",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/Organization",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "Organization",
        "path" : "Organization",
        "mustSupport" : false
      },
      {
        "id" : "Organization.identifier",
        "path" : "Organization.identifier",
        "slicing" : {
          "discriminator" : [
            {
              "type" : "value",
              "path" : "$this"
            }
          ],
          "rules" : "open"
        },
        "comment" : "NPI preferred.",
        "mustSupport" : true
      },
      {
        "id" : "Organization.identifier.system",
        "path" : "Organization.identifier.system",
        "max" : "1",
        "type" : [
          {
            "code" : "uri"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Organization.identifier.value",
        "path" : "Organization.identifier.value",
        "max" : "1",
        "type" : [
          {
            "code" : "string"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Organization.identifier:NPI",
        "path" : "Organization.identifier",
        "sliceName" : "NPI",
        "short" : "National Provider Identifier (NPI)",
        "patternIdentifier" : {
          "system" : "http://hl7.org/fhir/sid/us-npi"
        },
        "condition" : ["us-core-16", "us-core-17"],
        "constraint" : [
          {
            "key" : "us-core-16",
            "severity" : "error",
            "human" : "NPI must be 10 digits",
            "expression" : "value.matches('^[0-9]{10}$')",
            "xpath" : "f:value/f:matches(value,/^[0-9]{10}$/)"
          },
          {
            "key" : "us-core-17",
            "severity" : "error",
            "human" : "NPI check digit must be valid (Luhn algorithm check)",
            "expression" : "(((select(value.substring(0,1).toInteger()).select(iif($this<5, $this*2, (($this*2)-9))))+(value.substring(1,1).toInteger())+(select(value.substring(2,1).toInteger()).select(iif($this<5, $this*2, (($this*2)-9))))+(value.substring(3,1).toInteger())+(select(value.substring(4,1).toInteger()).select(iif($this<5, $this*2, (($this*2)-9))))+(value.substring(5,1).toInteger())+(select(value.substring(6,1).toInteger()).select(iif($this<5, $this*2, (($this*2)-9))))+(value.substring(7,1).toInteger())+(select(value.substring(8,1).toInteger()).select(iif($this<5, $this*2, (($this*2)-9))))+(value.substring(9,1).toInteger()) + 24)mod 10=0)"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Organization.identifier:CLIA",
        "path" : "Organization.identifier",
        "sliceName" : "CLIA",
        "short" : "Clinical Laboratory Improvement Amendments (CLIA) Number for laboratories",
        "patternIdentifier" : {
          "system" : "urn:oid:2.16.840.1.113883.4.7"
        },
        "condition" : ["us-core-18"],
        "constraint" : [
          {
            "key" : "us-core-18",
            "severity" : "error",
            "human" : "CLIA number must be 10 digits with a letter \"D\" in third position",
            "expression" : "value.matches('^[0-9]{2}D[0-9]{7}$')",
            "xpath" : "f:value/f:matches(value,/^[0-9]{2}D[0-9]{7}$/)"
          }
        ],
        "mustSupport" : false
      },
      {
        "id" : "Organization.identifier:NAIC",
        "path" : "Organization.identifier",
        "sliceName" : "NAIC",
        "short" : "NAIC Code",
        "comment" : "NAIC Company code (sometimes called \"NAIC Number\" or \"cocode\") for payers.",
        "patternIdentifier" : {
          "system" : "urn:oid:2.16.840.1.113883.6.300"
        },
        "condition" : ["us-core-19"],
        "constraint" : [
          {
            "key" : "us-core-19",
            "severity" : "error",
            "human" : "NAIC must be 5 digits",
            "expression" : "value.matches('^[0-9]{5}$')",
            "xpath" : "f:value/f:matches(value,/^[0-9]{5}$/)"
          }
        ],
        "mustSupport" : false
      },
      {
        "id" : "Organization.active",
        "path" : "Organization.active",
        "min" : 1,
        "mustSupport" : true
      },
      {
        "id" : "Organization.name",
        "path" : "Organization.name",
        "min" : 1,
        "mustSupport" : true
      },
      {
        "id" : "Organization.telecom",
        "path" : "Organization.telecom",
        "mustSupport" : true
      },
      {
        "id" : "Organization.telecom.system",
        "path" : "Organization.telecom.system",
        "mustSupport" : true
      },
      {
        "id" : "Organization.telecom.value",
        "path" : "Organization.telecom.value",
        "mustSupport" : true
      },
      {
        "id" : "Organization.address",
        "path" : "Organization.address",
        "mustSupport" : true
      },
      {
        "id" : "Organization.address.line",
        "path" : "Organization.address.line",
        "max" : "4",
        "type" : [
          {
            "code" : "string"
          }
        ],
        "example" : [
          {
            "label" : "US Core",
            "valueString" : "49 MEADOW ST"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Organization.address.city",
        "path" : "Organization.address.city",
        "max" : "1",
        "type" : [
          {
            "code" : "string"
          }
        ],
        "example" : [
          {
            "label" : "US Core",
            "valueString" : "EVERYTOWN"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Organization.address.state",
        "path" : "Organization.address.state",
        "max" : "1",
        "type" : [
          {
            "code" : "string"
          }
        ],
        "example" : [
          {
            "label" : "US Core",
            "valueString" : "OK"
          }
        ],
        "mustSupport" : true,
        "binding" : {
          "strength" : "extensible",
          "description" : "Two letter USPS alphabetic codes.",
          "valueSet" : "http://terminology.hl7.org/ValueSet/USPS-State"
        }
      },
      {
        "id" : "Organization.address.postalCode",
        "path" : "Organization.address.postalCode",
        "short" : "US Zip Codes",
        "max" : "1",
        "type" : [
          {
            "code" : "string"
          }
        ],
        "example" : [
          {
            "label" : "US Core",
            "valueString" : "74047"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Organization.address.country",
        "path" : "Organization.address.country",
        "max" : "1",
        "type" : [
          {
            "code" : "string"
          }
        ],
        "mustSupport" : true
      }
    ]
  }
}

```
