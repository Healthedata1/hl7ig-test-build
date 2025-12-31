# US Core Individual Sex Extension - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Individual Sex Extension**

## Extension: US Core Individual Sex Extension 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-individual-sex | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreIndividualSexExtension |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

USCDI includes a data element for Sex, intended to support the exchange of a recorded sex value. This extension aligns with the USCDI definition of Sex: "Documentation of a specific instance of sex." It enables systems to share the sex value as it was documented in a particular context. Systems choosing to record sources of information should use the [Provenance resource](http://hl7.org/fhir/R4/element-level-provenance.html).

**Context of Use**

**Usage info**

**Usages:**

* This Extension is not used by any profiles in this Implementation Guide

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-individual-sex)

### Formal Views of Extension Content

 [Description of Profiles, Differentials, Snapshots, and how the XML and JSON presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-individual-sex.csv), [Excel](StructureDefinition-us-core-individual-sex.xlsx), [Schematron](StructureDefinition-us-core-individual-sex.sch) 

#### Terminology Bindings

#### Constraints



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-individual-sex",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-individual-sex",
  "version" : "0.1.0",
  "name" : "USCoreIndividualSexExtension",
  "title" : "US Core Individual Sex Extension",
  "status" : "active",
  "date" : "2025-04-22",
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
  "description" : "USCDI includes a data element for Sex, intended to support the exchange of a recorded sex value. This extension aligns with the USCDI definition of Sex: \"Documentation of a specific instance of sex.\" It enables systems to share the sex value as it was documented in a particular context.  Systems choosing to record sources of information should use the [Provenance resource](element-level-provenance.html).",
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
      "expression" : "Patient"
    },
    {
      "type" : "element",
      "expression" : "RelatedPerson"
    },
    {
      "type" : "element",
      "expression" : "Person"
    },
    {
      "type" : "element",
      "expression" : "Practitioner"
    },
    {
      "type" : "element",
      "expression" : "FamilyMemberHistory"
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
        "definition" : "The US Core Individual Sex Extension is used to reflect the documentation of a person's sex. It aligns with the C-CDA Sex Observation (LOINC 46098-0).",
        "min" : 0,
        "max" : "1",
        "isModifier" : false
      },
      {
        "id" : "Extension.url",
        "path" : "Extension.url",
        "fixedUri" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-individual-sex"
      },
      {
        "id" : "Extension.value[x]",
        "path" : "Extension.value[x]",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "Coding"
          }
        ],
        "binding" : {
          "strength" : "extensible",
          "description" : "Federal Administrative Sex",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.113762.1.4.1021.121"
        }
      }
    ]
  }
}

```
