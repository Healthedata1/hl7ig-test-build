# US Core USCDI Requirement Extension - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core USCDI Requirement Extension**

## Extension: US Core USCDI Requirement Extension 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCDIRequirement |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

**This extension is only used in the US Core Implementation Guide''s Profile StructureDefinition elements.** It flags elements that are **Additional** USCDI Requirements for certified systems. In other words, elements that are not marked as Must Support but are required for ASTP Health IT certification testing. See the [Conformance page](general-requirements.md) for more information.

**Context of Use**

**Usage info**

**Usages:**

* Examples for this Extension: [USCoreAllergyIntolerance](StructureDefinition-us-core-allergyintolerance.md), [USCoreDocumentReferenceProfile](StructureDefinition-us-core-documentreference.md), [USCoreEncounterProfile](StructureDefinition-us-core-encounter.md), [USCoreMedicationRequestProfile](StructureDefinition-us-core-medicationrequest.md)...Show 2 more,[USCoreObservationPregnancyStatusProfile](StructureDefinition-us-core-observation-pregnancystatus.md)and[USCoreSpecimenProfile](StructureDefinition-us-core-specimen.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/uscdi-requirement)

### Formal Views of Extension Content

 [Description of Profiles, Differentials, Snapshots, and how the XML and JSON presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-uscdi-requirement.csv), [Excel](StructureDefinition-uscdi-requirement.xlsx), [Schematron](StructureDefinition-uscdi-requirement.sch) 

#### Constraints



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "uscdi-requirement",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement",
  "version" : "0.1.0",
  "name" : "USCDIRequirement",
  "title" : "US Core USCDI Requirement Extension",
  "status" : "active",
  "date" : "2023-04-03",
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
  "description" : "**This extension is only used in the US Core Implementation Guide''s Profile StructureDefinition elements.**  It flags elements that are *Additional* USCDI Requirements for certified systems. In other words, elements that are not marked as Must Support but are required for ASTP Health IT certification testing. See the [Conformance page](general-requirements.html) for more information.",
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
      "expression" : "ElementDefinition"
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
        "short" : "USCDI Requirement Flag: ONLY USED FOR US Core Profile StructureDefinitions",
        "definition" : "This extension flags elements that are *Additional* USCDI  Requirements for certified systems. In other words, elements that are not marked as Must Support but are required for for ASTP Health IT certification testing. See the [Conformance page](general-requirements.html) for more information.",
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
        "fixedUri" : "http://hl7.org/fhir/us/core/StructureDefinition/uscdi-requirement"
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
