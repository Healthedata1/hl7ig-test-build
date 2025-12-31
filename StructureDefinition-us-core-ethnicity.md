# US Core Ethnicity Extension - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Ethnicity Extension**

## Extension: US Core Ethnicity Extension 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/StructureDefinition/us-core-ethnicity | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreEthnicityExtension |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

Concepts classifying the person into a named category of humans sharing common history, traits, geographical origin or nationality. The ethnicity codes used to represent these concepts are based upon the [Race & Ethnicity - CDC (CDCREC)](https://phinvads.cdc.gov/vads/ViewCodeSystem.action?id=2.16.840.1.113883.6.238) code system. Detailed ethnicity concepts are grouped by and pre-mapped to the 2 OMB ethnicity categories:

* Hispanic or Latino
* Not Hispanic or Latino.

Complies with 2015 Edition Common Clinical Data Set for patient race.

**Context of Use**

**Usage info**

**Usages:**

* Use this Extension: [US Core Patient Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-patient.html)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/hl7.fhir.us.healthedata1-sandbox|current/StructureDefinition/us-core-ethnicity)

### Formal Views of Extension Content

 [Description of Profiles, Differentials, Snapshots, and how the XML and JSON presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-us-core-ethnicity.csv), [Excel](StructureDefinition-us-core-ethnicity.xlsx), [Schematron](StructureDefinition-us-core-ethnicity.sch) 

#### Terminology Bindings

#### Constraints



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "us-core-ethnicity",
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
  "url" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-ethnicity",
  "version" : "0.1.0",
  "name" : "USCoreEthnicityExtension",
  "title" : "US Core Ethnicity Extension",
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
  "description" : "Concepts classifying the person into a named category of humans sharing common history, traits, geographical origin or nationality.  The ethnicity codes used to represent these concepts are based upon the [Race & Ethnicity - CDC (CDCREC)](https://phinvads.cdc.gov/vads/ViewCodeSystem.action?id=2.16.840.1.113883.6.238) code system. Detailed ethnicity concepts are grouped by and pre-mapped to the 2 OMB ethnicity categories:\n\n   - Hispanic or Latino\n   - Not Hispanic or Latino.",
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
  "purpose" : "Complies with 2015 Edition Common Clinical Data Set for patient race.",
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
        "short" : "US Core ethnicity Extension",
        "definition" : "Concepts classifying the person into a named category of humans sharing common history, traits, geographical origin or nationality.  The ethnicity codes used to represent these concepts are based upon the [Race & Ethnicity - CDC (CDCREC)](https://phinvads.cdc.gov/vads/ViewCodeSystem.action?id=2.16.840.1.113883.6.238) code system. Detailed ethnicity concepts are grouped by and pre-mapped to the 2 OMB ethnicity categories:\n\n   - Hispanic or Latino\n   - Not Hispanic or Latino.",
        "min" : 0,
        "max" : "1"
      },
      {
        "id" : "Extension.extension",
        "path" : "Extension.extension",
        "slicing" : {
          "discriminator" : [
            {
              "type" : "value",
              "path" : "url"
            }
          ],
          "rules" : "open"
        },
        "min" : 1
      },
      {
        "id" : "Extension.extension:ombCategory",
        "path" : "Extension.extension",
        "sliceName" : "ombCategory",
        "short" : "Hispanic or Latino|Not Hispanic or Latino",
        "definition" : "The 2 ethnicity category codes according to the [OMB Standards for Maintaining, Collecting, and Presenting Federal Data on Race and Ethnicity, Statistical Policy Directive No. 15, as revised, October 30, 1997](https://www.govinfo.gov/content/pkg/FR-1997-10-30/pdf/97-28653.pdf).",
        "min" : 0,
        "max" : "1",
        "type" : [
          {
            "code" : "Extension"
          }
        ],
        "mustSupport" : true,
        "mapping" : [
          {
            "identity" : "iso11179",
            "map" : "/ClinicalDocument/recordTarget/patientRole/patient/ethnicGroupCode"
          }
        ]
      },
      {
        "id" : "Extension.extension:ombCategory.url",
        "path" : "Extension.extension.url",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "uri"
          }
        ],
        "fixedUri" : "ombCategory"
      },
      {
        "id" : "Extension.extension:ombCategory.value[x]",
        "path" : "Extension.extension.value[x]",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "Coding"
          }
        ],
        "binding" : {
          "strength" : "required",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.113883.4.642.40.2.48.3"
        }
      },
      {
        "id" : "Extension.extension:detailed",
        "path" : "Extension.extension",
        "sliceName" : "detailed",
        "short" : "Extended ethnicity codes",
        "definition" : "The 41 CDC ethnicity codes that are grouped under one of the 2 OMB ethnicity category codes.",
        "min" : 0,
        "max" : "*",
        "type" : [
          {
            "code" : "Extension"
          }
        ],
        "mapping" : [
          {
            "identity" : "iso11179",
            "map" : "/ClinicalDocument/recordTarget/patientRole/patient/sdtc:ethnicGroupCode"
          }
        ]
      },
      {
        "id" : "Extension.extension:detailed.url",
        "path" : "Extension.extension.url",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "uri"
          }
        ],
        "fixedUri" : "detailed"
      },
      {
        "id" : "Extension.extension:detailed.value[x]",
        "path" : "Extension.extension.value[x]",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "Coding"
          }
        ],
        "binding" : {
          "strength" : "required",
          "valueSet" : "http://cts.nlm.nih.gov/fhir/ValueSet/2.16.840.1.113883.4.642.40.2.48.1"
        }
      },
      {
        "id" : "Extension.extension:text",
        "path" : "Extension.extension",
        "sliceName" : "text",
        "short" : "ethnicity Text",
        "definition" : "Plain text representation of the ethnicity concept(s).",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "Extension"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "Extension.extension:text.url",
        "path" : "Extension.extension.url",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "uri"
          }
        ],
        "fixedUri" : "text"
      },
      {
        "id" : "Extension.extension:text.value[x]",
        "path" : "Extension.extension.value[x]",
        "min" : 1,
        "max" : "1",
        "type" : [
          {
            "code" : "string"
          }
        ]
      },
      {
        "id" : "Extension.url",
        "path" : "Extension.url",
        "min" : 1,
        "max" : "1",
        "fixedUri" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-ethnicity"
      },
      {
        "id" : "Extension.value[x]",
        "path" : "Extension.value[x]",
        "min" : 0,
        "max" : "0"
      }
    ]
  }
}

```
