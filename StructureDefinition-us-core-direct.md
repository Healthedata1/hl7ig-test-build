# US Core Direct email Extension - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Direct email Extension**

## Extension: US Core Direct email Extension 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-direct | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 3 | *Computable Name*:USCoreDirectEmailExtension |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

This email address is associated with a ["Direct Secure Messaging"](https://directtrust.org/what-we-do/direct-secure-messaging) service. This extension can only be used on contact points where the system = 'email'

**Context of Use**

**Usage info**

**Usages:**

* This Extension is not used by any profiles in this Implementation Guide

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-direct)

### Formal Views of Extension Content

 [Description of Profiles, Differentials, Snapshots, and how the XML and JSON presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-direct.csv), [Excel](StructureDefinition-us-core-direct.xlsx), [Schematron](StructureDefinition-us-core-direct.sch) 

#### Constraints



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-direct",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-direct",
  "version" : "0.1.0",
  "name" : "USCoreDirectEmailExtension",
  "title" : "US Core Direct email Extension",
  "status" : "active",
  "date" : "2022-11-16",
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
  "description" : "This email address is associated with a [\"Direct Secure Messaging\"](https://directtrust.org/what-we-do/direct-secure-messaging) service.  This extension can only be used on contact points where the system = 'email'",
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
    }
  ],
  "kind" : "complex-type",
  "abstract" : false,
  "context" : [
    {
      "type" : "element",
      "expression" : "ContactPoint"
    }
  ],
  "type" : "Extension",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/Extension",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "Extension",
        "path" : "Extension",
        "short" : "Email is a \"Direct\" email",
        "definition" : "This email address is associated with a \"Direct Secure Messaging\" service. This extension can only be used on contact points where the system = 'email'",
        "comment" : "This extension can only be used on contact points where the system = 'email'.",
        "min" : 0,
        "max" : "1",
        "isModifier" : false,
        "mapping" : [
          {
            "identity" : "v2",
            "map" : "No v2 equivalent"
          },
          {
            "identity" : "rim",
            "map" : "No RIM equivalent"
          }
        ]
      },
      {
        "id" : "Extension.url",
        "path" : "Extension.url",
        "fixedUri" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-direct"
      },
      {
        "id" : "Extension.value[x]",
        "path" : "Extension.value[x]",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "boolean"
          }
        ]
      }
    ]
  }
}

```
