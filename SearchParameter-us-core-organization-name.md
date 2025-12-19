# USCoreOrganizationName - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **USCoreOrganizationName**

## SearchParameter: USCoreOrganizationName 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/SearchParameter/us-core-organization-name | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreOrganizationName |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
**A portion of the organization's name or alias**
**NOTE**: This US Core SearchParameter definition extends the usage context of the[Conformance expectation extension](http://hl7.org/fhir/R4/extension-capabilitystatement-expectation.html) 
* multipleAnd
* multipleOr
* comparator
* modifier
* chain
 



## Resource Content

```json
{
  "resourceType" : "SearchParameter",
  "id" : "us-core-organization-name",
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
  "url" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-organization-name",
  "version" : "0.1.0",
  "name" : "USCoreOrganizationName",
  "derivedFrom" : "http://hl7.org/fhir/SearchParameter/Organization-name",
  "status" : "active",
  "experimental" : false,
  "date" : "2022-04-14",
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
  "description" : "**A portion of the organization's name or alias**  \n**NOTE**: This US Core SearchParameter definition extends the usage context of the\n[Conformance expectation extension](http://hl7.org/fhir/R4/extension-capabilitystatement-expectation.html)\n - multipleAnd\n - multipleOr\n - comparator\n - modifier\n - chain",
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
  "code" : "name",
  "base" : ["Organization"],
  "type" : "string",
  "expression" : "Organization.name|Organization.alias",
  "xpathUsage" : "normal",
  "multipleOr" : true,
  "_multipleOr" : {
    "extension" : [
      {
        "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
        "valueCode" : "MAY"
      }
    ]
  },
  "multipleAnd" : true,
  "_multipleAnd" : {
    "extension" : [
      {
        "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
        "valueCode" : "MAY"
      }
    ]
  }
}

```
