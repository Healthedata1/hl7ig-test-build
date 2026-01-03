# US Core Fetch DocumentReference - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **US Core Fetch DocumentReference**

## OperationDefinition: US Core Fetch DocumentReference 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://hl7.org/fhir/us/core/OperationDefinition/docref | *Version*:0.1.0 | |
| *Standards status:*[Trial-use](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 5 | *Computable Name*:USCoreFetchDocumentReference |
| **Copyright/Legal**: Used by permission of HL7 International, all rights reserved Creative Commons License | | |

 
This operation is used to return all the references to documents related to a patient. It is invoked on a FHIR Server's DocumentReference endpoint (e.g.,`[base]/DocumentReference/$docref`) and operates across all DocumentReference instances. 
The operation requires a patient id and takes the optional input parameters: 
* start context date
* end context date
* document type
* on-demand
* profile
 
and returns a**searchset**[Bundle](http://hl7.org/fhir/bundle.html)containing[DocumentReference](http://hl7.org/fhir/documentreference.html)resources for the patient. If the server has stored documents or can create documents for the patient and those documents are available for the user, the server returns the DocumentReference resources associated with documents. This operation's intended use is to provide a way for providers or patients to access their available documents. The document itself can be subsequently retrieved using the link provided in the`DocumentReference.content.attachment.url element`. The link could be a FHIR endpoint to a[Binary](http://hl7.org/fhir/R4/binary.html)Resource or some other document repository. 
This operation is**different**from a FHIR RESTful query on DocumentReference by patient and type and period range because: 
1. It is used to request a server to**generate**a document based on the specified parameters.
1. If no parameters are specified, the server SHALL return a DocumentReference to the patient's current C-CDA CCD.
1. If the server cannot**generate**a document based on the specified parameters, the operation will return an empty search bundle.
 
Unless the client indicates they are only interested in 'on-demand' documents using the**on-demand**parameter, the server SHOULD return DocumentReference instances for**existing**documents that meet the request parameters In this regard, this operation is**similar**to a FHIR RESTful query. 



## Resource Content

```json
{
  "resourceType" : "OperationDefinition",
  "id" : "docref",
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
  "url" : "http://hl7.org/fhir/us/core/OperationDefinition/docref",
  "version" : "0.1.0",
  "name" : "USCoreFetchDocumentReference",
  "title" : "US Core Fetch DocumentReference",
  "status" : "active",
  "kind" : "operation",
  "date" : "2022-11-18",
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
  "description" : "This operation is used to return all the references to documents related to a\npatient. It is invoked on a FHIR Server's DocumentReference endpoint (e.g., `[base]/DocumentReference/$docref`) and operates across all DocumentReference instances.\n\nThe operation requires a patient id and takes the optional input parameters:\n- start context date\n- end context date\n- document type\n- on-demand\n- profile\n\nand returns a *searchset* [Bundle](http://hl7.org/fhir/bundle.html) containing [DocumentReference](http://hl7.org/fhir/documentreference.html) resources for the patient. If the server has stored documents or can create documents for the patient and those documents are available for the user, the server returns the DocumentReference resources associated with documents. This operation's intended use is to provide a way for providers or patients to access their available documents. The document itself can be subsequently retrieved using the link provided  in the `DocumentReference.content.attachment.url element`. The link could be a FHIR endpoint to a [Binary](http://hl7.org/fhir/R4/binary.html) Resource or some other document repository.\n\nThis operation is *different* from a FHIR RESTful query on DocumentReference by patient and type and period range because:\n\n1. It is used to request a server to *generate* a document based on the specified parameters.\n\n1. If no parameters are specified, the server SHALL return a DocumentReference to the patient's current C-CDA CCD.\n\n1. If the server cannot *generate* a document based on the specified parameters, the operation will return an empty search bundle.\n\nUnless the client indicates they are only interested in 'on-demand' documents using the *on-demand* parameter, the server SHOULD return DocumentReference instances for *existing* documents that meet the request parameters  In this regard, this operation is *similar* to a FHIR RESTful query.",
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
  "code" : "docref",
  "comment" : " - It is assumed that the server has identified and secured the context appropriately and can either associate the authorization context with a single patient or determine whether the context has the rights to the nominated patient if there is one. If there is no nominated patient (e.g., the operation is invoked at the system level) and the context is not associated with a single patient record, then the server should return an error. Specifying the relationship between the context, a user, and patient records is outside the scope of this specification.\n\n - A server may generate an on-demand document upon returning its DocumentReference during the $docref response or once the client accesses it. This specification places no requirements upon when a server generates an on-demand document and encourages server developers to balance the performance cost of creating unread documents against the response time to retrieve new documents.\n\n - See the US Core DocumentReference Profile [Quick Start Section](StructureDefinition-us-core-documentreference.html#quick-start) for example interactions",
  "resource" : ["DocumentReference"],
  "system" : false,
  "type" : true,
  "instance" : false,
  "parameter" : [
    {
      "name" : "patient",
      "use" : "in",
      "min" : 1,
      "max" : "1",
      "documentation" : "The id of the patient resource. If there is no match, an empty Bundle is returned.",
      "type" : "id"
    },
    {
      "name" : "start",
      "use" : "in",
      "min" : 0,
      "max" : "1",
      "documentation" : "The context date range relates to care service dates, not document reference creation dates - e.g., all records relating to care provided in a specific date range. If no start context date is provided, all documents before the end context date are in scope. The most recent or current document is in scope if neither a start date nor an end context date is provided. The client **SHOULD** provide values precise to the second + time offset.",
      "type" : "dateTime"
    },
    {
      "name" : "end",
      "use" : "in",
      "min" : 0,
      "max" : "1",
      "documentation" : "The context date range relates to care dates, not document reference creation dates - e.g., all records relating to care provided in a specific date range. If no end context date is provided, all documents after the start context date are in scope. The most recent or current document is in scope if neither a start date nor an end context date is provided. The client **SHOULD** provide values precise to the second + time offset.",
      "type" : "dateTime"
    },
    {
      "name" : "type",
      "use" : "in",
      "min" : 0,
      "max" : "*",
      "documentation" : "The type relates to document type e.g., for the LOINC code for a C-CDA Clinical Summary of Care (CCD) is 34133-9 (Summary of episode note). If no type is provided, the CCD document, if available, SHALL be in scope, and all other document types MAY be in scope. It is at the server's discretion how to respond if multiple types are provided. The server MAY return documents to any of the specified types. The server's CapabilityStatement should document its behavior and what types it supports.",
      "type" : "Coding",
      "binding" : {
        "strength" : "required",
        "valueSet" : "http://hl7.org/fhir/ValueSet/c80-doc-typecodes"
      }
    },
    {
      "name" : "on-demand",
      "use" : "in",
      "min" : 0,
      "max" : "1",
      "documentation" : "This on-demand parameter allows the client to dictate whether they are requesting only 'on-demand' or both 'on-demand' and 'stable' documents (or delayed/deferred assembly) that meet the query parameters",
      "type" : "boolean"
    },
    {
      "name" : "profile",
      "use" : "in",
      "min" : 0,
      "max" : "*",
      "documentation" : "This parameter allows the client to request documents according to a specific profile using the profile's canonical reference. It is at the server's discretion how to respond if multiple profiles are provided. The server MAY return documents to any of the specified profiles. The server's CapabilityStatement should document its behavior and what profiles it supports.",
      "type" : "canonical"
    },
    {
      "name" : "return",
      "use" : "out",
      "min" : 1,
      "max" : "1",
      "documentation" : "The bundle type is 'searchset' containing [DocumentReference](http://hl7.org/fhir/documentreference.html) resources which **SHOULD** conform to the [US Core DocumentReference Profiles](StructureDefinition-us-core-documentreference.html)",
      "type" : "Bundle"
    }
  ]
}

```
