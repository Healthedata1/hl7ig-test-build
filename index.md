# Home - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* **Home**

## Home

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/healthedata1-sandbox/ImplementationGuide/hl7.fhir.us.healthedata1-sandbox | *Version*:0.1.0 | |
| *IG Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 2 | *Computable Name*:HealthEData_1Sandbox |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

### Health eData Sandbox

testbed for ideas….

#### FOO

using http:

[US Core](http://hl7.org/fhir/us/core/STU4/index.html)

[FHIR](http://hl7.org/fhir/)

using https:

[US Core](https://hl7.org/fhir/us/core/STU4/index.html)

[FHIR](https://hl7.org/fhir/)

using path variable

[FHIR](http://hl7.org/fhir/R4/)

#### in list…:

using http:

* [US Core](http://hl7.org/fhir/us/core/STU4/index.html)
* [FHIR](http://hl7.org/fhir/)

using https:

* [US Core](https://hl7.org/fhir/us/core/STU4/index.html)
* [FHIR](https://hl7.org/fhir/)

#### in table…:

using http:

| |
| :--- |
| [US Core](http://hl7.org/fhir/us/core/STU4/index.html) |
| [FHIR](http://hl7.org/fhir/) |

using https:

| |
| :--- |
| [US Core](https://hl7.org/fhir/us/core/STU4/index.html) |
| [FHIR](https://hl7.org/fhir/) |

### Cross Version Analysis

This is an R4 IG. None of the features it uses are changed in R4B, so it can be used as is with R4B systems. Packages for both [R4 (hl7.fhir.us.healthedata1-sandbox.r4)](package.r4.tgz) and [R4B (hl7.fhir.us.healthedata1-sandbox.r4b)](package.r4b.tgz) are available.

bar This is an R4 IG. None of the features it uses are changed in R4B, so it can be used as is with R4B systems. Packages for both [R4 (hl7.fhir.us.healthedata1-sandbox.r4)](package.r4.tgz) and [R4B (hl7.fhir.us.healthedata1-sandbox.r4b)](package.r4b.tgz) are available.  foo

### IG Dependencies

This IG Contains the following dependencies on other IGs.






### Global Profiles

*There are no Global profiles defined*

### Copyrights

```
This publication includes IP covered under the following statements.
<ul>
<li>This material contains content from <a href="http://loinc.org">LOINC</a>. LOINC is copyright &copy; 1995-2020, Regenstrief Institute, Inc. and the Logical Observation Identifiers Names and Codes (LOINC) Committee and is available at no cost under the <a href="http://loinc.org/license">license</a>. LOINC&reg; is a registered United States trademark of Regenstrief Institute, Inc.<div data-fhir="generated" id="ipp_1" onClick="if (document.getElementById('ipp2_1').innerHTML != '') {document.getElementById('ipp_1').innerHTML = document.getElementById('ipp2_1').innerHTML; document.getElementById('ipp2_1').innerHTML = ''}"> <span style="cursor: pointer; border: 1px grey solid; background-color: #fcdcb3; padding-left: 3px; padding-right: 3px; color: black">Show Usage</span></div><div id="ipp2_1" style="display: none">
<ul>
<li><a href="http://terminology.hl7.org/3.1.0/CodeSystem-v3-loinc.html">LOINC</a>: <a href="StructureDefinition-us-core-observation-lab.html">USCoreLaboratoryResultObservationProfile</a> and <a href="StructureDefinition-us-core-observation-adi-documentation.html">USCoreObservationADIDocumentationProfile</a></li>
</ul>
</div></li>
<li>This material contains content that is copyright of SNOMED International. Implementers of these specifications must have the appropriate SNOMED CT Affiliate license - for more information contact <a href="https://www.snomed.org/get-snomed">https://www.snomed.org/get-snomed</a> or <a href="mailto:info@snomed.org">info@snomed.org</a>.<div data-fhir="generated" id="ipp_2" onClick="if (document.getElementById('ipp2_2').innerHTML != '') {document.getElementById('ipp_2').innerHTML = document.getElementById('ipp2_2').innerHTML; document.getElementById('ipp2_2').innerHTML = ''}"> <span style="cursor: pointer; border: 1px grey solid; background-color: #fcdcb3; padding-left: 3px; padding-right: 3px; color: black">Show Usage</span></div><div id="ipp2_2" style="display: none">
<ul>
<li><a href="http://hl7.org/fhir/R4/codesystem-snomedct.html">SNOMED Clinical Terms&amp;reg; (SNOMED CT&amp;reg;)</a>: <a href="AllergyIntolerance-example.html">AllergyIntolerance/example</a> and <a href="StructureDefinition-us-core-observation-adi-documentation.html">USCoreObservationADIDocumentationProfile</a></li>
</ul>
</div></li>
<li>This material derives from the HL7 Terminology (THO). THO is copyright &copy;1989+ Health Level Seven International and is made available under the CC0 designation. For more licensing information see: <a href="https://terminology.hl7.org/license.html">https://terminology.hl7.org/license.html</a><div data-fhir="generated" id="ipp_3" onClick="if (document.getElementById('ipp2_3').innerHTML != '') {document.getElementById('ipp_3').innerHTML = document.getElementById('ipp2_3').innerHTML; document.getElementById('ipp2_3').innerHTML = ''}"> <span style="cursor: pointer; border: 1px grey solid; background-color: #fcdcb3; padding-left: 3px; padding-right: 3px; color: black">Show Usage</span></div><div id="ipp2_3" style="display: none">
<ul>
<li><a href="http://terminology.hl7.org/7.0.1/CodeSystem-allergyintolerance-clinical.html">AllergyIntolerance Clinical Status Codes</a>: <a href="AllergyIntolerance-example.html">AllergyIntolerance/example</a></li>
<li><a href="http://terminology.hl7.org/7.0.1/CodeSystem-allergyintolerance-verification.html">AllergyIntolerance Verification Status</a>: <a href="AllergyIntolerance-example.html">AllergyIntolerance/example</a></li>
<li><a href="http://terminology.hl7.org/7.0.1/CodeSystem-data-absent-reason.html">DataAbsentReason</a>: <a href="StructureDefinition-us-core-observation-adi-documentation.html">USCoreObservationADIDocumentationProfile</a></li>
<li><a href="http://terminology.hl7.org/7.0.1/CodeSystem-observation-category.html">Observation Category Codes</a>: <a href="StructureDefinition-us-core-observation-lab.html">USCoreLaboratoryResultObservationProfile</a>, <a href="StructureDefinition-us-core-observation-adi-documentation.html">USCoreObservationADIDocumentationProfile</a> and <a href="StructureDefinition-us-core-observation-clinical-result.html">USCoreObservationClinicalResultProfile</a></li>
<li><a href="http://terminology.hl7.org/7.0.1/CodeSystem-v3-ObservationInterpretation.html">ObservationInterpretation</a>: <a href="StructureDefinition-us-core-observation-lab.html">USCoreLaboratoryResultObservationProfile</a></li>
</ul>
</div></li>
<li>Used by permission of HL7 International, all rights reserved Creative Commons License<div data-fhir="generated" id="ipp_4" onClick="if (document.getElementById('ipp2_4').innerHTML != '') {document.getElementById('ipp_4').innerHTML = document.getElementById('ipp2_4').innerHTML; document.getElementById('ipp2_4').innerHTML = ''}"> <span style="cursor: pointer; border: 1px grey solid; background-color: #fcdcb3; padding-left: 3px; padding-right: 3px; color: black">Show Usage</span></div><div id="ipp2_4" style="display: none">
<ul>
<li><a href="http://tx.fhir.org/r4/ValueSet/us-core-category">US Core Category</a>: <a href="StructureDefinition-us-core-observation-adi-documentation.html">USCoreObservationADIDocumentationProfile</a></li>
</ul>
</div></li>
</ul>
<!--$$1$$-->

```

This publication includes IP covered under the following statements.

* This material contains content from [LOINC](http://loinc.org). LOINC is copyright © 1995-2020, Regenstrief Institute, Inc. and the Logical Observation Identifiers Names and Codes (LOINC) Committee and is available at no cost under the [license](http://loinc.org/license). LOINC® is a registered United States trademark of Regenstrief Institute, Inc.

* [LOINC](http://terminology.hl7.org/3.1.0/CodeSystem-v3-loinc.html): [USCoreLaboratoryResultObservationProfile](StructureDefinition-us-core-observation-lab.md) and [USCoreObservationADIDocumentationProfile](StructureDefinition-us-core-observation-adi-documentation.md)


* This material contains content that is copyright of SNOMED International. Implementers of these specifications must have the appropriate SNOMED CT Affiliate license - for more information contact [https://www.snomed.org/get-snomed](https://www.snomed.org/get-snomed) or [info@snomed.org](mailto:info@snomed.org).

* [SNOMED Clinical Terms&reg; (SNOMED CT&reg;)](http://hl7.org/fhir/R4/codesystem-snomedct.html): [AllergyIntolerance/example](AllergyIntolerance-example.md) and [USCoreObservationADIDocumentationProfile](StructureDefinition-us-core-observation-adi-documentation.md)


* This material derives from the HL7 Terminology (THO). THO is copyright ©1989+ Health Level Seven International and is made available under the CC0 designation. For more licensing information see: [https://terminology.hl7.org/license.html](https://terminology.hl7.org/license.html)

* [AllergyIntolerance Clinical Status Codes](http://terminology.hl7.org/7.0.1/CodeSystem-allergyintolerance-clinical.html): [AllergyIntolerance/example](AllergyIntolerance-example.md)
* [AllergyIntolerance Verification Status](http://terminology.hl7.org/7.0.1/CodeSystem-allergyintolerance-verification.html): [AllergyIntolerance/example](AllergyIntolerance-example.md)
* [DataAbsentReason](http://terminology.hl7.org/7.0.1/CodeSystem-data-absent-reason.html): [USCoreObservationADIDocumentationProfile](StructureDefinition-us-core-observation-adi-documentation.md)
* [Observation Category Codes](http://terminology.hl7.org/7.0.1/CodeSystem-observation-category.html): [USCoreLaboratoryResultObservationProfile](StructureDefinition-us-core-observation-lab.md), [USCoreObservationADIDocumentationProfile](StructureDefinition-us-core-observation-adi-documentation.md) and [USCoreObservationClinicalResultProfile](StructureDefinition-us-core-observation-clinical-result.md)
* [ObservationInterpretation](http://terminology.hl7.org/7.0.1/CodeSystem-v3-ObservationInterpretation.html): [USCoreLaboratoryResultObservationProfile](StructureDefinition-us-core-observation-lab.md)


* Used by permission of HL7 International, all rights reserved Creative Commons License

* [US Core Category](http://tx.fhir.org/r4/ValueSet/us-core-category): [USCoreObservationADIDocumentationProfile](StructureDefinition-us-core-observation-adi-documentation.md)


### using {{site.data.resources[resource_].description}}

by string

{{site.data.resources['ImplementationGuide/healthedata1-sandbox'].description | markdownify}}

with markdown filter

without markdown filter

0: John

1: Paul

2: George

3: Ringo



## Resource Content

```json
{
  "resourceType" : "ImplementationGuide",
  "id" : "hl7.fhir.us.healthedata1-sandbox",
  "extension" : [
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
      "valueCode" : "trial-use"
    },
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
      "valueInteger" : 2
    }
  ],
  "url" : "http://hl7.org/fhir/us/healthedata1-sandbox/ImplementationGuide/hl7.fhir.us.healthedata1-sandbox",
  "version" : "0.1.0",
  "name" : "HealthEData_1Sandbox",
  "title" : "Health eData 1 Sandbox",
  "status" : "active",
  "date" : "2025-12-29T21:47:57+00:00",
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
  "description" : "This is a **Healthedata1** sandbox for creation of resources and examples",
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
  "packageId" : "hl7.fhir.us.healthedata1-sandbox",
  "license" : "CC0-1.0",
  "fhirVersion" : ["4.0.1"],
  "dependsOn" : [
    {
      "id" : "hl7tx",
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/tools/StructureDefinition/implementationguide-dependency-comment",
          "valueMarkdown" : "Automatically added as a dependency - all IGs depend on HL7 Terminology"
        }
      ],
      "uri" : "http://terminology.hl7.org/ImplementationGuide/hl7.terminology",
      "packageId" : "hl7.terminology.r4",
      "version" : "7.0.1"
    },
    {
      "id" : "hl7ext",
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/tools/StructureDefinition/implementationguide-dependency-comment",
          "valueMarkdown" : "Automatically added as a dependency - all IGs depend on the HL7 Extension Pack"
        }
      ],
      "uri" : "http://hl7.org/fhir/extensions/ImplementationGuide/hl7.fhir.uv.extensions",
      "packageId" : "hl7.fhir.uv.extensions.r4",
      "version" : "5.2.0"
    },
    {
      "id" : "hl7_fhir_us_core",
      "uri" : "http://hl7.org/fhir/us/core/ImplementationGuide/hl7.fhir.us.core",
      "packageId" : "hl7.fhir.us.core",
      "version" : "5.0.1"
    },
    {
      "id" : "hl7_fhir_uv_sdc",
      "uri" : "http://hl7.org/fhir/uv/sdc/ImplementationGuide/hl7.fhir.uv.sdc",
      "packageId" : "hl7.fhir.uv.sdc",
      "version" : "3.0.0"
    },
    {
      "id" : "hl7_fhir_uv_bulkdata",
      "uri" : "http://hl7.org/fhir/uv/bulkdata/ImplementationGuide/hl7.fhir.uv.bulkdata",
      "packageId" : "hl7.fhir.uv.bulkdata",
      "version" : "2.0.0"
    },
    {
      "id" : "hl7_fhir_uv_smart_app_launch",
      "uri" : "http://hl7.org/fhir/smart-app-launch/ImplementationGuide/hl7.fhir.uv.smart-app-launch",
      "packageId" : "hl7.fhir.uv.smart-app-launch",
      "version" : "2.0.0"
    },
    {
      "id" : "vsac",
      "uri" : "http://fhir.org/packages/us.nlm.vsac/ImplementationGuide/us.nlm.vsac",
      "packageId" : "us.nlm.vsac",
      "version" : "0.3.0"
    },
    {
      "id" : "uscdcphinvads",
      "uri" : "http://fhir.org/packages/us.cdc.phinvads/ImplementationGuide/us.cdc.phinvads",
      "packageId" : "us.cdc.phinvads",
      "version" : "0.12.0"
    }
  ],
  "definition" : {
    "extension" : [
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "copyrightyear"
          },
          {
            "url" : "value",
            "valueString" : "2020+"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "releaselabel"
          },
          {
            "url" : "value",
            "valueString" : "CI Build"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "path-expansion-params"
          },
          {
            "url" : "value",
            "valueString" : "../../input/_resources/exp-params.json"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "show-inherited-invariants"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "usage-stats-opt-out"
          },
          {
            "url" : "value",
            "valueString" : "false"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "path-output"
          },
          {
            "url" : "value",
            "valueString" : "output"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "path-liquid"
          },
          {
            "url" : "value",
            "valueString" : "input/liquid"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "path-data"
          },
          {
            "url" : "value",
            "valueString" : "input/examples"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "excludexml"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "excludejson"
          },
          {
            "url" : "value",
            "valueString" : "false"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "excludettl"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "excludemap"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "propagate-status"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "path-history"
          },
          {
            "url" : "value",
            "valueString" : "http://hl7.org/fhir/us/healthedata1-sandbox/history.html"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "autoload-resources"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "path-liquid"
          },
          {
            "url" : "value",
            "valueString" : "template/liquid"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "path-qa"
          },
          {
            "url" : "value",
            "valueString" : "temp/qa"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "path-temp"
          },
          {
            "url" : "value",
            "valueString" : "temp/pages"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "path-suppressed-warnings"
          },
          {
            "url" : "value",
            "valueString" : "input/ignoreWarnings.txt"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "template-html"
          },
          {
            "url" : "value",
            "valueString" : "template-page.html"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "template-md"
          },
          {
            "url" : "value",
            "valueString" : "template-page-md.html"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "apply-contact"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "apply-context"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "apply-copyright"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "apply-jurisdiction"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "apply-license"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "apply-publisher"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "apply-version"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "apply-wg"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "active-tables"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "fmm-definition"
          },
          {
            "url" : "value",
            "valueString" : "http://hl7.org/fhir/versions.html#maturity"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "excludelogbinaryformat"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueString" : "tabbed-snapshots"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/expansion-parameters",
        "valueReference" : {
          "reference" : "Parameters/expansion-parameters"
        }
      },
      {
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-internal-dependency",
        "valueCode" : "hl7.fhir.uv.tools.r4#0.9.0"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "copyrightyear"
          },
          {
            "url" : "value",
            "valueString" : "2020+"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "releaselabel"
          },
          {
            "url" : "value",
            "valueString" : "CI Build"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "path-expansion-params"
          },
          {
            "url" : "value",
            "valueString" : "../../input/_resources/exp-params.json"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "show-inherited-invariants"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "usage-stats-opt-out"
          },
          {
            "url" : "value",
            "valueString" : "false"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "path-output"
          },
          {
            "url" : "value",
            "valueString" : "output"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "path-liquid"
          },
          {
            "url" : "value",
            "valueString" : "input/liquid"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "path-data"
          },
          {
            "url" : "value",
            "valueString" : "input/examples"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "excludexml"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "excludejson"
          },
          {
            "url" : "value",
            "valueString" : "false"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "excludettl"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "excludemap"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "propagate-status"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "path-history"
          },
          {
            "url" : "value",
            "valueString" : "http://hl7.org/fhir/us/healthedata1-sandbox/history.html"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "autoload-resources"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "path-liquid"
          },
          {
            "url" : "value",
            "valueString" : "template/liquid"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "path-qa"
          },
          {
            "url" : "value",
            "valueString" : "temp/qa"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "path-temp"
          },
          {
            "url" : "value",
            "valueString" : "temp/pages"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "path-suppressed-warnings"
          },
          {
            "url" : "value",
            "valueString" : "input/ignoreWarnings.txt"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "template-html"
          },
          {
            "url" : "value",
            "valueString" : "template-page.html"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "template-md"
          },
          {
            "url" : "value",
            "valueString" : "template-page-md.html"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "apply-contact"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "apply-context"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "apply-copyright"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "apply-jurisdiction"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "apply-license"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "apply-publisher"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "apply-version"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "apply-wg"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "active-tables"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "fmm-definition"
          },
          {
            "url" : "value",
            "valueString" : "http://hl7.org/fhir/versions.html#maturity"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "excludelogbinaryformat"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      },
      {
        "extension" : [
          {
            "url" : "code",
            "valueCode" : "tabbed-snapshots"
          },
          {
            "url" : "value",
            "valueString" : "true"
          }
        ],
        "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-parameter"
      }
    ],
    "grouping" : [
      {
        "id" : "TestExamples",
        "name" : "Test Examples",
        "description" : "Examples for Testing Stuff Out!!!"
      }
    ],
    "resource" : [
      {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
            "valueString" : "AllergyIntolerance"
          }
        ],
        "reference" : {
          "reference" : "AllergyIntolerance/example"
        },
        "name" : "AllergyIntolerance Example",
        "description" : "This is a allergyintolerance example for the *US Core AllergyIntolerance Profile*.",
        "exampleCanonical" : "http://hl7.org/fhir/us/core/StructureDefinition/us-core-allergyintolerance"
      },
      {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
            "valueString" : "CapabilityStatement"
          }
        ],
        "reference" : {
          "reference" : "CapabilityStatement/us-core-client-liquid"
        },
        "name" : "US Core Client CapabilityStatement Liquid Rendered",
        "description" : "This Section describes the expected capabilities of the US Core Client which is responsible for creating and initiating the queries for information about an individual patient. The complete list of FHIR profiles, RESTful operations, and search parameters supported by US Core Servers are defined in the [Conformance Requirements for Server](CapabilityStatement-us-core-server.html). US Core Clients have the option of choosing from this list to access necessary data based on their local use cases and other contextual requirements.",
        "exampleBoolean" : false
      },
      {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
            "valueString" : "StructureDefinition:resource"
          }
        ],
        "reference" : {
          "reference" : "StructureDefinition/us-core-observation-lab"
        },
        "name" : "US Core Laboratory Result Observation Profile",
        "description" : "The US Core Laboratory Result Observation Profile is based upon the US Core Observation Clinical Result Profile and, along with the US Core DiagnosticReport Profile for Laboratory Results Reporting, meets the U.S. Core Data for Interoperability (USCDI) Laboratory requirements. Laboratory results are grouped and summarized using the DiagnosticReport resource, which references Observation resources. Each Observation resource represents an individual laboratory test and result value, a “nested” panel (such as a microbial susceptibility panel) that references other observations, or rarely a laboratory test with component result values. The US Core Laboratory Result Observation Profile sets minimum expectations for the Observation resource to record, search, and fetch laboratory test results associated with a patient to promote interoperability and adoption through common implementation. It identifies which core elements, extensions, vocabularies, and value sets SHALL be present in the resource and constrains the way the elements are used when using this profile. It provides the floor for standards development for specific use cases.",
        "exampleBoolean" : false
      },
      {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
            "valueString" : "StructureDefinition:resource"
          }
        ],
        "reference" : {
          "reference" : "StructureDefinition/us-core-observation-adi-documentation"
        },
        "name" : "US Core Observation ADI Documentation Profile",
        "description" : "The US Core Observation Advance Directive Information (ADI) Documentation Profile inherits from the FHIR [Observation](https://hl7.org/fhir/R4/observation.html) resource; refer to it for scope and usage definitions. This profile and the [US Core Observation ADI DocumentationReference Profile](StructureDefinition-us-core-adi-documentreference.html) meet the [U.S. Core Data for Interoperability (USCDI)](https://www.healthit.gov/isp/united-states-core-data-interoperability-uscdi) *Advance Directive Observation* Data Element requirements. It is used to communicate whether a person has advance directive information (ADI) and, if one or more documents exist, their location. Examples of advance healthcare directive documents include physician order for life sustaining treatment (POLST), do not resuscitate order (DNR), and medical power of attorney. To communicate the type of advance directive document, the author, the verifier, and other properties, see the US Core ADI DocumentReference Profile. This profile sets minimum expectations for the Observation resource to record, search, and fetch findings about the presence of a patient's advance directives. It specifies which core elements, extensions,  vocabularies, and value sets **SHALL** be present in the resource and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption.",
        "exampleBoolean" : false
      },
      {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
            "valueString" : "StructureDefinition:resource"
          }
        ],
        "reference" : {
          "reference" : "StructureDefinition/us-core-observation-clinical-result"
        },
        "name" : "US Core Observation Clinical Result Profile",
        "description" : "The US Core Observation Clinical Result Profile is based upon the core FHIR Observation Resource and, along with the US Core DiagnosticReport Profile, meets the US Core Data for Interoperability (USCDI) requirements for *Diagnostic Imaging* and *Clinical Tests* Data Classes. This profile sets minimum expectations for the Observation resource to record and search non-laboratory clinical test results (e.g., radiology and other clinical observations generated from procedures). An example would be when a gastroenterologist reports the size of a polyp observed during a colonoscopy. This profile is the basis for the US Core Laboratory Result Observation Profile, which defines additional data elements to record and search laboratory test results.\n\nThe US Core Observation Clinical Result Profile sets minimum expectations to promote interoperability and adoption through common implementation. It identifies which core elements, extensions, vocabularies, and value sets **SHALL** be present in the resource and constrains the way the elements are used when using this profile. It provides the floor for standards development for specific use cases.",
        "exampleBoolean" : false
      },
      {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
            "valueString" : "StructureDefinition:resource"
          }
        ],
        "reference" : {
          "reference" : "StructureDefinition/us-core-patient"
        },
        "name" : "US Core Patient Profile",
        "description" : "The US Core Patient Profile inherits from the FHIR [Patient](https://hl7.org/fhir/R4/patient.html) resource; refer to it for scope and usage definitions. This profile meets the requirements of the [U.S. Core Data for Interoperability (USCDI)](https://www.healthit.gov/isp/united-states-core-data-interoperability-uscdi) *Patient Demographics/Information* Data Class. It sets minimum expectations for the Patient resource to record, search, and fetch basic demographics and other administrative information about an individual patient. It specifies which core elements, extensions, vocabularies, and value sets **SHALL** be present and constrains how the elements are used. Providing the floor for standards development for specific use cases promotes interoperability and adoption.",
        "exampleBoolean" : false
      },
      {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
            "valueString" : "CapabilityStatement"
          }
        ],
        "reference" : {
          "reference" : "CapabilityStatement/us-core-server-liquid"
        },
        "name" : "US Core Server CapabilityStatement Liquid Rendered",
        "description" : "This Section describes the expected capabilities of the US Core Server actor which is responsible for providing responses to the queries submitted by the US Core Requestors. The complete list of FHIR profiles, RESTful operations, and search parameters supported by US Core Servers are defined. Systems implementing this capability statement should meet the ASTP 2015 Common Clinical Data Set (CCDS) access requirement for Patient Selection 170.315(g)(7) and Application Access - Data Category Request 170.315(g)(8) and the ASTP [U.S. Core Data for Interoperability (USCDI) Version 6 July 2025](https://www.healthit.gov/isp/sites/isp/files/2025-07/USCDI-Version-6-July-2025.pdf).",
        "exampleBoolean" : false
      },
      {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
            "valueString" : "SearchParameter"
          }
        ],
        "reference" : {
          "reference" : "SearchParameter/us-core-observation-category"
        },
        "name" : "USCoreObservationCategory",
        "description" : "**The classification of the type of observation**  \nNOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the [Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation) to define additional expectations for the following SearchParameter elements:\n- `multipleAnd`\n- `multipleOr`\n- `comparator`\n- `modifier`\n- `chain`\n\nIt **SHALL NOT** be used as a search parameter for search. Servers and Clients **SHOULD** use the standard FHIR SearchParameter.",
        "exampleBoolean" : false
      },
      {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
            "valueString" : "SearchParameter"
          }
        ],
        "reference" : {
          "reference" : "SearchParameter/us-core-observation-code"
        },
        "name" : "USCoreObservationCode",
        "description" : "**The code of the observation type**  \nNOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the [Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation) to define additional expectations for the following SearchParameter elements:\n- `multipleAnd`\n- `multipleOr`\n- `comparator`\n- `modifier`\n- `chain`\n\nIt **SHALL NOT** be used as a search parameter for search. Servers and Clients **SHOULD** use the standard FHIR SearchParameter.",
        "exampleBoolean" : false
      },
      {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
            "valueString" : "SearchParameter"
          }
        ],
        "reference" : {
          "reference" : "SearchParameter/us-core-observation-date"
        },
        "name" : "USCoreObservationDate",
        "description" : "**Obtained date/time. If the obtained element is a period, a date that falls in the period**  \nNOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the [Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation) to define additional expectations for the following SearchParameter elements:\n- `multipleAnd`\n- `multipleOr`\n- `comparator`\n- `modifier`\n- `chain`\n\nIt **SHALL NOT** be used as a search parameter for search. Servers and Clients **SHOULD** use the standard FHIR SearchParameter.",
        "exampleBoolean" : false
      },
      {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
            "valueString" : "SearchParameter"
          }
        ],
        "reference" : {
          "reference" : "SearchParameter/us-core-observation-lastupdated"
        },
        "name" : "USCoreObservationLastUpdated",
        "description" : "**When the resource version last changed**  \nNOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the [Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation) to define additional expectations for the following SearchParameter elements:\n- `multipleAnd`\n- `multipleOr`\n- `comparator`\n- `modifier`\n- `chain`\n\nIt **SHALL NOT** be used as a search parameter for search. Servers and Clients **SHOULD** use the standard FHIR SearchParameter.",
        "exampleBoolean" : false
      },
      {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
            "valueString" : "SearchParameter"
          }
        ],
        "reference" : {
          "reference" : "SearchParameter/us-core-observation-patient"
        },
        "name" : "USCoreObservationPatient",
        "description" : "**The subject that the observation is about (if patient)**  \nNOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the [Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation) to define additional expectations for the following SearchParameter elements:\n- `multipleAnd`\n- `multipleOr`\n- `comparator`\n- `modifier`\n- `chain`\n\nIt **SHALL NOT** be used as a search parameter for search. Servers and Clients **SHOULD** use the standard FHIR SearchParameter.",
        "exampleBoolean" : false
      },
      {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/tools/StructureDefinition/resource-information",
            "valueString" : "SearchParameter"
          }
        ],
        "reference" : {
          "reference" : "SearchParameter/us-core-observation-status"
        },
        "name" : "USCoreObservationStatus",
        "description" : "**The status of the observation**  \nNOTE: This SearchParameter is defined only to document Server and Client expectations. Its definition is derived from the standard FHIR SearchParameter and it uses the [Conformance expectation extension](http://hl7.org/fhir/StructureDefinition/capabilitystatement-expectation) to define additional expectations for the following SearchParameter elements:\n- `multipleAnd`\n- `multipleOr`\n- `comparator`\n- `modifier`\n- `chain`\n\nIt **SHALL NOT** be used as a search parameter for search. Servers and Clients **SHOULD** use the standard FHIR SearchParameter.",
        "exampleBoolean" : false
      }
    ],
    "page" : {
      "extension" : [
        {
          "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
          "valueCode" : "informative"
        },
        {
          "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
          "valueUrl" : "toc.html"
        }
      ],
      "nameUrl" : "toc.html",
      "title" : "Table of Contents",
      "generation" : "html",
      "page" : [
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
              "valueCode" : "draft"
            },
            {
              "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
              "valueUrl" : "index.html"
            }
          ],
          "nameUrl" : "index.html",
          "title" : "Home",
          "generation" : "markdown"
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
              "valueCode" : "informative"
            },
            {
              "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
              "valueUrl" : "guidance.html"
            }
          ],
          "nameUrl" : "guidance.html",
          "title" : "Guidance",
          "generation" : "markdown"
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
              "valueCode" : "informative"
            },
            {
              "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
              "valueUrl" : "search-parameters.html"
            }
          ],
          "nameUrl" : "search-parameters.html",
          "title" : "Search Parameters",
          "generation" : "markdown"
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
              "valueCode" : "informative"
            },
            {
              "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
              "valueUrl" : "downloads.html"
            }
          ],
          "nameUrl" : "downloads.html",
          "title" : "Downloads",
          "generation" : "markdown"
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
              "valueCode" : "informative"
            },
            {
              "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
              "valueUrl" : "ImplementationGuide.html"
            }
          ],
          "nameUrl" : "ImplementationGuide.html",
          "title" : "ImplementationGuide Resource",
          "generation" : "markdown"
        },
        {
          "extension" : [
            {
              "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
              "valueCode" : "informative"
            },
            {
              "url" : "http://hl7.org/fhir/tools/StructureDefinition/ig-page-name",
              "valueUrl" : "changes.html"
            }
          ],
          "nameUrl" : "changes.html",
          "title" : "Change Log",
          "generation" : "markdown"
        }
      ]
    },
    "parameter" : [
      {
        "code" : "path-resource",
        "value" : "input/resources"
      },
      {
        "code" : "path-resource",
        "value" : "fsh-generated/resources"
      },
      {
        "code" : "path-resource",
        "value" : "input/intro-notes"
      },
      {
        "code" : "path-resource",
        "value" : "input/capabilities"
      },
      {
        "code" : "path-resource",
        "value" : "input/examples"
      },
      {
        "code" : "path-resource",
        "value" : "input/extensions"
      },
      {
        "code" : "path-resource",
        "value" : "input/models"
      },
      {
        "code" : "path-resource",
        "value" : "input/operations"
      },
      {
        "code" : "path-resource",
        "value" : "input/profiles"
      },
      {
        "code" : "path-resource",
        "value" : "input/vocabulary"
      },
      {
        "code" : "path-resource",
        "value" : "input/testing"
      },
      {
        "code" : "path-resource",
        "value" : "input/history"
      },
      {
        "code" : "path-pages",
        "value" : "template/config"
      },
      {
        "code" : "path-pages",
        "value" : "input/images"
      },
      {
        "code" : "path-tx-cache",
        "value" : "input-cache/txcache"
      }
    ]
  }
}

```
