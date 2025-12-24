<!-- {% raw %} This liquid script generates context specific search parameters for each  profiles base on the page context and type Do not edit directly{% endraw %} -->
---

**LIQUID SCRIPT**

establish the page context and get type

page.path = {{page.path}}

type = {{ include.type }}

then run through the csv file for all the data

{% assign resource_type = include.type -%}
{% assign shall_searches = site.data.search_requirements | where: "base", resource_type | where: "base_conf", "SHALL" -%}
{% if shall_searches.size > 0 %}
#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

{% for search in shall_searches %}
{% include search-requirement-handler.md conf_verb ="SHALL" search=search %}


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
