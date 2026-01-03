# Discharge Summary Example - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Discharge Summary Example**

## Example DocumentReference: Discharge Summary Example

| |
| :--- |
| *Page standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) |

Profile: [US Core DocumentReference Profile](http://hl7.org/fhir/us/core/STU5.0.1/StructureDefinition-us-core-documentreference.html)

**status**: Current

**type**: Discharge Summary

**category**: Clinical No

**subject**: [Amy V. Baxter Female, DoB: 1987-02-20 ( Medical Record Number: 1032702 (use: usual, ))](http://hl7.org/fhir/us/core/STU5.0.1/Patient-example.html)

> **content**

### Attachments

| | | |
| :--- | :--- | :--- |
| - | **ContentType** | **Data** |
| * | text/plain | `Tm8gYWN0aXZpdHkgcmVzdHJpY3Rpb24sIHJlZ3VsYXIgZGlldCwgZm9sbG93IHVwIGluIHR3byB0byB0aHJlZSB3ZWVrcyB3aXRoIHByaW1hcnkgY2FyZSBwcm92aWRlci4=` |


### Contexts

| | |
| :--- | :--- |
| - | **Encounter** |
| * | [Encounter: status = completed; class = ambulatory; type = 99201](http://hl7.org/fhir/us/core/STU5.0.1/Encounter-example-1.html) |



## Resource Content

```json
{
  "resourceType" : "DocumentReference",
  "id" : "discharge-summary",
  "meta" : {
    "extension" : [
      {
        "url" : "http://hl7.org/fhir/StructureDefinition/instance-name",
        "valueString" : "Discharge Summary Example"
      },
      {
        "url" : "http://hl7.org/fhir/StructureDefinition/instance-description",
        "valueMarkdown" : "This is a discharge summary example for the *US Core DocumentReference*. It is used in the [Write Note Example](StructureDefinition-us-core-documentreference.html#mandatory-operation)."
      }
    ],
    "profile" : [
      "http://hl7.org/fhir/us/core/StructureDefinition/us-core-documentreference"
    ]
  },
  "status" : "current",
  "type" : {
    "coding" : [
      {
        "system" : "http://loinc.org",
        "code" : "18842-5",
        "display" : "Discharge Summary"
      }
    ],
    "text" : "Discharge Summary"
  },
  "category" : [
    {
      "coding" : [
        {
          "system" : "http://hl7.org/fhir/us/core/CodeSystem/us-core-documentreference-category",
          "code" : "clinical-note",
          "display" : "Clinical Note"
        }
      ],
      "text" : "Clinical No"
    }
  ],
  "subject" : {
    "reference" : "Patient/example"
  },
  "content" : [
    {
      "attachment" : {
        "contentType" : "text/plain",
        "data" : "Tm8gYWN0aXZpdHkgcmVzdHJpY3Rpb24sIHJlZ3VsYXIgZGlldCwgZm9sbG93IHVwIGluIHR3byB0byB0aHJlZSB3ZWVrcyB3aXRoIHByaW1hcnkgY2FyZSBwcm92aWRlci4="
      }
    }
  ],
  "context" : {
    "encounter" : [
      {
        "reference" : "Encounter/example-1"
      }
    ]
  }
}

```
