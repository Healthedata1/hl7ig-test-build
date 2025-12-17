# USCoreAllergyintolerancePatient - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **USCoreAllergyintolerancePatient**

## SearchParameter: USCoreAllergyintolerancePatient 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/SearchParameter/us-core-allergyintolerance-patient | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreAllergyintolerancePatient |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
**Who the sensitivity is for**
NOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the[Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation)to define additional expectations for the following SearchParameter elements: 
* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`
 
It**SHALL NOT**be used as a search parameter for search. Servers and Clients**SHOULD**use the standard FHIR SearchParameter. 

**id** us-core-allergyintolerance-patient

**url** : **http://hl7.org/fhir/us/core/SearchParameter/us-core-allergyintolerance-patient** 

**name** : USCoreAllergyintolerancePatient

**derivedFrom** : http://hl7.org/fhir/SearchParameter/clinical-patient

**status** : active

**date** : 11/17/2024

**publisher** : HL7 International - Cross-Group Projects

**contact** : http://www.hl7.org/Special/committees/cgp

**jurisdiction** : United States of America (the) (Details : {urn:iso:std:iso:3166 code 'US' = 'United States of America', given as 'United States of America (the)'}) 

**code** : `patient` 

**base** :AllergyIntolerance

**type** : reference

**expression** : `AllergyIntolerance.patient` 

**xpath** : `f:AllergyIntolerance/f:patient|f:CarePlan/f:subject|f:CareTeam/f:subject|f:ClinicalImpression/f:subject|f:Composition/f:subject|f:Condition/f:subject|f:Consent/f:patient|f:DetectedIssue/f:patient|f:DeviceRequest/f:subject|f:DeviceUseStatement/f:subject|f:DiagnosticReport/f:subject|f:DocumentManifest/f:subject|f:DocumentReference/f:subject|f:Encounter/f:subject|f:EpisodeOfCare/f:patient|f:FamilyMemberHistory/f:patient|f:Flag/f:subject|f:Goal/f:subject|f:ImagingStudy/f:subject|f:Immunization/f:patient|f:List/f:subject|f:MedicationAdministration/f:subject|f:MedicationDispense/f:subject|f:MedicationRequest/f:subject|f:MedicationStatement/f:subject|f:NutritionOrder/f:patient|f:Observation/f:subject|f:Procedure/f:subject|f:RiskAssessment/f:subject|f:ServiceRequest/f:subject|f:SupplyDelivery/f:patient|f:VisionPrescription/f:patient` 

**xpathUsage** : normal

**target** Patient

**multipleOr** : True (Conformance Expectation = MAY)

**multipleAnd** : True ( Conformance Expectation = MAY)



## Resource Content

```json
{
  "resourceType" : "SearchParameter",
  "id" : "us-core-allergyintolerance-patient",
  "extension" : [
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
      "valueInteger" : 5
    }
  ],
  "url" : "http://hl7.org/fhir/us/core/SearchParameter/us-core-allergyintolerance-patient",
  "version" : "0.1.0",
  "name" : "USCoreAllergyintolerancePatient",
  "derivedFrom" : "http://hl7.org/fhir/SearchParameter/clinical-patient",
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
  "description" : "**Who the sensitivity is for**  \nNOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the [Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation) to define additional expectations for the following SearchParameter elements:\n- `multipleAnd`\n- `multipleOr`\n- `comparator`\n- `modifier`\n- `chain`\n\nIt **SHALL NOT** be used as a search parameter for search. Servers and Clients **SHOULD** use the standard FHIR SearchParameter.\n",
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
  "code" : "patient",
  "base" : ["AllergyIntolerance"],
  "type" : "reference",
  "expression" : "AllergyIntolerance.patient",
  "xpathUsage" : "normal",
  "target" : ["Patient"],
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
