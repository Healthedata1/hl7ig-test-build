# Search Parameters - Health eData 1 Sandbox v0.1.0

* [**Table of Contents**](toc.md)
* **Search Parameters**

## Search Parameters

| |
| :--- |
| *Page standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) |

### Search Parameters

The following search parameters have been defined for the US Core Implementation Guide. The FHIR specification provides more information on the [FHIR RESTful search API] and the standard [Search Parameter Registry].

**SEE IMPLEMENTER NOTES BELOW**

#### Optional Search Parameters

The following search parameters have been defined as optional search parameters for search. US Core does not define any Server or Client expectations for their use.

* [US Core Race](SearchParameter-us-core-race.md)
* [US Core Ethnicity](SearchParameter-us-core-ethnicity.md)

#### Search Parameters defined by this Implementation Guide

The following search parameters have been defined by US Core. They are defined to be used for search and to document Server and Client expectations. Unlike the search parameter in the next section, they are not derived from the standard FHIR SearchParameters.

##### CareTeam

* [US Core CareTeam Role](SearchParameter-us-core-careteam-role.md)

##### Condition

* [US Core Condition Asserted Date](SearchParameter-us-core-condition-asserted-date.md)

##### Encounter

* [US Core Encounter Discharge Disposition](SearchParameter-us-core-encounter-discharge-disposition.md)

##### Goal

* [US Core Goal Description](SearchParameter-us-core-goal-description.md)

##### Patient

#### Search Parameters derived from the Base FHIR Specification

These SearchParameter are used solely to document Server and Client expectations. Their definitions are derived from the standard FHIR SearchParameter and define additional expectations for the following SearchParameter elements:

* `multipleAnd`
* `multipleOr`
* `comparator`
* `modifier`
* `chain`

They **SHALL NOT** be interpreted as search parameters for search. Servers and Clients **SHOULD** use the standard FHIR SearchParameters.

#### AllergyIntolerance

      ⸺

#### DocumentReference

      ⸺

#### Extension

      ⸺

#### MedicationRequest

      ⸺

#### Observation

* [US Core Observation Category](SearchParameter-us-core-observation-category.md)
* [US Core Observation Code](SearchParameter-us-core-observation-code.md)
* [US Core Observation Date](SearchParameter-us-core-observation-date.md)
* [US Core Observation Lastupdated](SearchParameter-us-core-observation-lastupdated.md)
* [US Core Observation Patient](SearchParameter-us-core-observation-patient.md)
* [US Core Observation Status](SearchParameter-us-core-observation-status.md)

#### Organization

      ⸺

#### PractitionerRole

      ⸺

