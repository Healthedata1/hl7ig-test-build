# US Core Sex Extension - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Sex Extension**

## Extension: US Core Sex Extension 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-sex | *Version*:0.1.0 | |
| *Standards status:*[Deprecated](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 2 | *Computable Name*:USCoreSexExtension |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

The Sex Extension is used to reflect the documentation of a person's sex. Systems choosing to record sources of information should use the [Provenance resource](http://hl7.org/fhir/R4/element-level-provenance.html).

USCDI includes a data element for sex, intended to support the exchange of a sex value that is not characterized as sex assigned at birth or birth sex. This Sex extension supports USCDI. Sex assigned at birth or birth sex can be recorded using the more specific [US Core Birth Sex Extension](StructureDefinition-us-core-birthsex.md). Future versions of this extension may be informed by the content of the HL7 Cross Paradigm IG: Gender Harmony - Sex and Gender Representation, which may include additional guidance on its relationship to administrative gender ([Patient.gender](StructureDefinition-us-core-patient-definitions.md#Patient.gender)).

**Context of Use**

**Usage info**

**Usages:**

* This Extension is not used by any profiles in this Implementation Guide

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-sex)

### Formal Views of Extension Content

 [Description of Profiles, Differentials, Snapshots, and how the XML and JSON presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-sex.csv), [Excel](StructureDefinition-us-core-sex.xlsx), [Schematron](StructureDefinition-us-core-sex.sch) 

#### Terminology Bindings

#### Constraints



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-sex",
  "extension" : [
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
      "valueCode" : "deprecated",
      "_valueCode" : {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status-reason",
            "valueMarkdown" : "This extension is no longer a USCDI requirement and is deprecated. It **SHOULD NOT** be used for new or revised content. It is retained for historical/backward compatibility purposes. Implementers **SHOULD** use the [US Core Individual Sex Extension](StructureDefinition-us-core-individual-sex.html) instead"
          }
        ]
      }
    },
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
      "valueInteger" : 2
    }
  ],
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-sex",
  "version" : "0.1.0",
  "name" : "USCoreSexExtension",
  "title" : "US Core Sex Extension",
  "status" : "retired",
  "date" : "2023-05-15",
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
  "description" : "The Sex Extension is used to reflect the documentation of a person's sex. Systems choosing to record sources of information should use the [Provenance resource](element-level-provenance.html).\n \nUSCDI includes a data element for sex, intended to support the exchange of a sex value that is not characterized as sex assigned at birth or birth sex. This Sex extension supports USCDI. Sex assigned at birth or birth sex can be recorded using the more specific [US Core Birth Sex Extension](StructureDefinition-us-core-birthsex.html).\nFuture versions of this extension may be informed by the content of the HL7 Cross Paradigm IG: Gender Harmony - Sex and Gender Representation, which may include additional guidance on its relationship to administrative gender ([Patient.gender](StructureDefinition-us-core-patient-definitions.html#Patient.gender)).",
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
        "definition" : "The US Core Sex Extension is used to reflect the documentation of a person's sex. It aligns with the C-CDA Sex Observation (LOINC 46098-0).",
        "min" : 0,
        "max" : "1",
        "isModifier" : false
      },
      {
        "id" : "Extension.url",
        "path" : "Extension.url",
        "fixedUri" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-sex"
      },
      {
        "id" : "Extension.value[x]",
        "path" : "Extension.value[x]",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "code"
          }
        ],
        "binding" : {
          "strength" : "extensible",
          "description" : "Concepts used for general documentation of sex representation",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.113762.1.4.1240.3"
        }
      }
    ]
  }
}

```
