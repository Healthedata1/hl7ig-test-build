# USCoreCareplanDate - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **USCoreCareplanDate**

## SearchParameter: USCoreCareplanDate 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/SearchParameter/us-core-careplan-date | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreCareplanDate |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
**Time period plan covers**
NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements: 
* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
 
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. 

**id** us-core-careplan-date

**url** : **http://hl7.org/fhir/us/core/SearchParameter/us-core-careplan-date** 

**name** : USCoreCareplanDate

**derivedFrom** : http://hl7.org/fhir/SearchParameter/clinical-date

**status** : active

**date** : 11/17/2024

**publisher** : HL7 International - Cross-Group Projects

**contact** : http://www.hl7.org/Special/committees/cgp

**jurisdiction** : United States of America (the) (Details : {urn:iso:std:iso:3166 code 'US' = 'United States of America', given as 'United States of America (the)'}) 

**code** : `date` 

**base** :CarePlan

**type** : date

**expression** : `CarePlan.period` 

**xpath** : `f:AllergyIntolerance/f:recordedDate|f:CarePlan/f:period|f:CareTeam/f:period|f:ClinicalImpression/f:date|f:Composition/f:date|f:Consent/f:dateTime|f:DiagnosticReport/f:effectiveDateTime|f:DiagnosticReport/f:effectivePeriod|f:Encounter/f:period|f:EpisodeOfCare/f:period|f:FamilyMemberHistory/f:date|f:Flag/f:period|f:Immunization/f:occurrenceDateTime|f:Immunization/f:occurrenceString|f:List/f:date|f:Observation/f:effectiveDateTime|f:Observation/f:effectivePeriod|f:Observation/f:effectiveTiming|f:Observation/f:effectiveInstant|f:Procedure/f:performedDateTime|f:Procedure/f:performedPeriod|f:Procedure/f:performedString|f:Procedure/f:performedAge|f:Procedure/f:performedRange|f:RiskAssessment/f:occurrenceDateTime|f:SupplyRequest/f:authoredOn` 

**xpathUsage** : normal

**multipleOr** : True (Conformance Expectation = MAY)

**multipleAnd** : True ( Conformance Expectation = SHOULD)

**comparator** : `eq` ( Conformance Expectation = MAY)

**comparator** : `ne` ( Conformance Expectation = MAY)

**comparator** : `gt` ( Conformance Expectation = SHALL)

**comparator** : `ge` ( Conformance Expectation = SHALL)

**comparator** : `lt` ( Conformance Expectation = SHALL)

**comparator** : `le` ( Conformance Expectation = SHALL)

**comparator** : `sa` ( Conformance Expectation = MAY)

**comparator** : `eb` ( Conformance Expectation = MAY)

**comparator** : `ap` ( Conformance Expectation = MAY)



## Resource Content

```json
{
  "resourceType" : "SearchParameter",
  "id" : "us-core-careplan-date",
  "extension" : [
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
      "valueInteger" : 5
    }
  ],
  "url" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-careplan-date",
  "version" : "0.1.0",
  "name" : "USCoreCareplanDate",
  "derivedFrom" : "http://hl7.org/fhir/SearchParameter/clinical-date",
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
  "description" : "**Time period plan covers**  \nNOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the [Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation) to define additional expectations for the following SearchParameter elements:\n- `multipleAnd`\n- `multipleOr`\n- `comparator`\n- `modifier`\n- `chain`\n\nIt **SHALL NOT** be used as a search parameter for search. Servers and Clients **SHOULD** use the standard FHIR SearchParameter.\n",
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
  "code" : "date",
  "base" : ["CarePlan"],
  "type" : "date",
  "expression" : "CarePlan.period",
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
        "valueCode" : "SHOULD"
      }
    ]
  },
  "comparator" : [
    "eq",
    "ne",
    "gt",
    "ge",
    "lt",
    "le",
    "sa",
    "eb",
    "ap"
  ],
  "_comparator" : [
    {
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
          "valueCode" : "MAY"
        }
      ]
    },
    {
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
          "valueCode" : "MAY"
        }
      ]
    },
    {
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
          "valueCode" : "SHALL"
        }
      ]
    },
    {
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
          "valueCode" : "SHALL"
        }
      ]
    },
    {
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
          "valueCode" : "SHALL"
        }
      ]
    },
    {
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
          "valueCode" : "SHALL"
        }
      ]
    },
    {
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
          "valueCode" : "MAY"
        }
      ]
    },
    {
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
          "valueCode" : "MAY"
        }
      ]
    },
    {
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation",
          "valueCode" : "MAY"
        }
      ]
    }
  ]
}

```
