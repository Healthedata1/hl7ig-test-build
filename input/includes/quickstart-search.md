<!-- {% raw %} This liquid script generates context specific search parameters for each  profiles base on the page context and type Do not edit directly
invoke with:
{% include quickstart-search.md type=type fixed_categories='{system|}[code]' code_codes='{system|}[code]'
%} note that the parent include tags are not accessible and have to be included specifically
the include parameters:
 - type (required)  = profile resource type
 - title (required) = profile name
 - fixed_category (optional) = a fixed category code for supplied examples  and implementation notes - these are profile dependent for resources with multiple profiles like Condition or Observation.
 - code1, code2, code3 (optional) = codes for supplied examples - these are profile dependent for resources with multiple profiles like Condition or Observation.
- single_example(optional) = flag for using only a single example. default is false, used for resources with multiple profiles like Condition or Observation, where not all examples provided are appropriate.

  {% endraw %} -->

---

**LIQUID SCRIPT**

establish the page context and get type

page.path = {{page.path}}

type = {{ include.type }}

title = {{ include.title }}

then run through the csv file for all the data

{% assign resource_type = include.type -%}
{% assign profile_name = include.title -%}
{% assign fixed_category = include.category -%}
{% assign code1 = include.code1 -%}
{% assign code2 = include.code2 -%}
{% assign code3 = include.code3 -%}
{% assign single_example = include.single_example %}  {% comment %} defaults to false {% endcomment -%}
{% assign shall_searches = site.data.search_requirements | where: "base", resource_type | where: "base_conf", "SHALL" -%}
{% if shall_searches.size > 0 %}
#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

{% for search in shall_searches %}
{% include search-requirement-handler.md conf_verb="SHALL" search=search %}


{% endfor -%}
{% endif %}


{% assign should_searches = site.data.search_requirements | where: "base", resource_type | where: "base_conf", "SHOULD" -%}
{% if should_searches.size > 0 %}
#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported
{% for search in should_searches %}
{% include search-requirement-handler.md conf_verb="SHOULD" search=search %}


{% endfor -%}
{% endif %}
