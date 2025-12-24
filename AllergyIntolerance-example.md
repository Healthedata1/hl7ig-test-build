# AllergyIntolerance Example - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **AllergyIntolerance Example**

## Example AllergyIntolerance: AllergyIntolerance Example

| |
| :--- |
| *Page standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) |

Profile: [US Core AllergyIntolerance Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-allergyintolerance.html)

**clinicalStatus**: Active

**verificationStatus**: Confirmed

**category**: Medication

**criticality**: High Risk

**code**: sulfonamide antibacterial

**patient**: [Amy V. Shaw](http://hl7.org/fhir/us/core/STU5.0.1/Patient-example.html)

**recorder**: [Dr Ronald Bone](http://hl7.org/fhir/us/core/STU5.0.1/Practitioner-practitioner-1.html)

### Reactions

| | | |
| :--- | :--- | :--- |
| - | **Manifestation** | **Severity** |
| * | skin rash | Mild |



## Resource Content

```json
{
  "resourceType" : "AllergyIntolerance",
  "id" : "example",
  "meta" : {
    "extension" : [
      {
        "url" : "http://hl7.org/fhir/StructureDefinition/instance-name",
        "valueString" : "AllergyIntolerance Example"
      },
      {
        "url" : "http://hl7.org/fhir/StructureDefinition/instance-description",
        "valueMarkdown" : "This is a allergyintolerance example for the *US Core AllergyIntolerance Profile*."
      }
    ],
    "profile" : [
      "http://hl7.org/fhir/us/core/StructureDefinition/us-core-allergyintolerance"
    ]
  },
  "clinicalStatus" : {
    "coding" : [
      {
        "system" : "http://terminology.hl7.org/CodeSystem/allergyintolerance-clinical",
        "code" : "active"
      }
    ]
  },
  "verificationStatus" : {
    "coding" : [
      {
        "system" : "http://terminology.hl7.org/CodeSystem/allergyintolerance-verification",
        "code" : "confirmed"
      }
    ]
  },
  "category" : ["medication"],
  "criticality" : "high",
  "code" : {
    "coding" : [
      {
        "system" : "http://snomed.info/sct",
        "version" : "http://snomed.info/sct/731000124108",
        "code" : "763875007",
        "display" : "Product containing sulfonamide (product)"
      }
    ],
    "text" : "sulfonamide antibacterial"
  },
  "patient" : {
    "reference" : "Patient/example",
    "display" : "Amy V. Shaw"
  },
  "recorder" : {
    "reference" : "Practitioner/practitioner-1",
    "display" : "Dr Ronald Bone"
  },
  "reaction" : [
    {
      "manifestation" : [
        {
          "coding" : [
            {
              "system" : "http://snomed.info/sct",
              "version" : "http://snomed.info/sct/731000124108",
              "code" : "271807003",
              "display" : "skin rash"
            }
          ],
          "text" : "skin rash"
        }
      ],
      "severity" : "mild"
    }
  ]
}

```
