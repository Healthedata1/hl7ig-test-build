# USCoreCareteamStatus - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **USCoreCareteamStatus**

## SearchParameter: USCoreCareteamStatus 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/SearchParameter/us-core-careteam-status | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreCareteamStatus |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
**proposed | active | suspended | inactive | entered-in-error**
NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements: 
* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
 
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. 

**id** us-core-careteam-status

**url** : **http://hl7.org/fhir/us/core/SearchParameter/us-core-careteam-status** 

**name** : USCoreCareteamStatus

**derivedFrom** : http://hl7.org/fhir/SearchParameter/CareTeam-status

**status** : active

**date** : 11/17/2024

**publisher** : HL7 International - Cross-Group Projects

**contact** : http://www.hl7.org/Special/committees/cgp

**jurisdiction** : United States of America (the) (Details : {urn:iso:std:iso:3166 code 'US' = 'United States of America', given as 'United States of America (the)'}) 

**code** : `status` 

**base** :CareTeam

**type** : token

**expression** : `CareTeam.status` 

**xpath** : `f:CareTeam/f:status` 

**xpathUsage** : normal

**multipleOr** : True (Conformance Expectation = SHOULD)

**multipleAnd** : True ( Conformance Expectation = MAY)



## Resource Content

```json
{
  "resourceType" : "SearchParameter",
  "id" : "us-core-careteam-status",
  "extension" : [
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
      "valueInteger" : 5
    }
  ],
  "url" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-careteam-status",
  "version" : "0.1.0",
  "name" : "USCoreCareteamStatus",
  "derivedFrom" : "http://hl7.org/fhir/SearchParameter/CareTeam-status",
  "status" : "active",
  "experimental" : false,
  "date" : "2024-11-17",
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
  "description" : "**proposed | active | suspended | inactive | entered-in-error**  \nNOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the [Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation) to define additional expectations for the following SearchParameter elements:\n- `multipleAnd`\n- `multipleOr`\n- `comparator`\n- `modifier`\n- `chain`\n\nIt **SHALL NOT** be used as a search parameter for search. Servers and Clients **SHOULD** use the standard FHIR SearchParameter.\n",
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
  "code" : "status",
  "base" : ["CareTeam"],
  "type" : "token",
  "expression" : "CareTeam.status",
  "xpathUsage" : "normal",
  "multipleOr" : true,
  "_multipleOr" : {
    "extension" : [
      {
        "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
        "valueCode" : "SHOULD"
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
