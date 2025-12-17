# USCoreRace - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **USCoreRace**

## SearchParameter: USCoreRace 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/SearchParameter/us-core-race | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreRace |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
Returns patients with a race extension matching the specified code. 

**id** us-core-race

**url** : **http://hl7.org/fhir/us/core/SearchParameter/us-core-race** 

**version** : 4.1.0

**name** : USCoreRace

**status** : active

**date** : 04/14/2022

**publisher** : HL7 International - Cross-Group Projects

**contact** : http://www.hl7.org/Special/committees/cgp

**jurisdiction** : United States of America (the) (Details : {urn:iso:std:iso:3166 code 'US' = 'United States of America', given as 'United States of America (the)'}) 

**code** : `race` 

**base** :Patient

**type** : token

**expression** : `Patient.extension.where(url = 'http://hl7.org/fhir/us/core/StructureDefinition/us-core-race').extension.value.code` 

**xpath** : `f:Patient/f:extension[@url='http://hl7.org/fhir/us/core/StructureDefinition/us-core-race']/f:extension/f:valueCoding/f:code/@value` 

**xpathUsage** : normal

**multipleOr** : True (Conformance Expectation = MAY)

**multipleAnd** : True ( Conformance Expectation = MAY)



## Resource Content

```json
{
  "resourceType" : "SearchParameter",
  "id" : "us-core-race",
  "extension" : [
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
      "valueInteger" : 5
    }
  ],
  "url" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-race",
  "version" : "0.1.0",
  "name" : "USCoreRace",
  "status" : "active",
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
  "description" : "Returns patients with a race extension matching the specified code.",
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
  "code" : "race",
  "base" : ["Patient"],
  "type" : "token",
  "expression" : "Patient.extension.where(url = 'http://hl7.org/fhir/us/core/StructureDefinition/us-core-race').extension.value.code",
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
