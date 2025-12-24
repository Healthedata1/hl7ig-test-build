<!-- {% raw %} This liquid script generates context specific search parameters for each  profiles base on the page context and type Do not edit directly{% endraw %} -->
---

**LIQUID SCRIPT**

establish the page context and get type

page.path = {{page.path}}

type = {{ include.type }}

then run through the csv file for all the data

{% assign type = include.type -%}
{% assign shall_searches = site.data.search_requirements | where: "base", type | where: "base_conf", "SHALL" -%}
{% if shall_searches.size > 0 %}
#### Mandatory Search Parameters:

The following search parameters and search parameter combinations **SHALL** be supported:

{% for search in shall_searches %}
{% assign search_codes = search.code | split: "," -%}
{% assign search_types = search.type | split: "," -%}
1. **SHALL** {% if search.description %}{{search.description}}{% else %}support searching using {% if search_codes.size > 1 %}the combination of `[{{ search_codes | join: ']` and `[' }}]` search parameters{% else %}`[{{ search_codes }}]`{% endif %}{% endif %}:

   {% for search_code in search_codes %}
     {%- assign search_code_row = site.data.search_requirements | where:"code", search_code |  where: "base", type | first -%}
      {% if search_code_row.multipleAnd_conf %}- **{{ search_code_row.multipleAnd_conf }}** support *AND* search on `{{search_code}}` (e.g.`{{search_code}}=[date]&{{search_code}}=[date]&...`){% endif %}
      {% if search_code_row.multipleOr_conf %}- **{{ search_code_row.multipleOr_conf }}** support *OR* search on `{{search_code}}` (e.g.`{{search_code}}={system|}[code],{system|}[code],...`){% endif %}
      {% if search_code_row.shall_comparator %}- **SHALL** support these `{{search_code}}` comparators: "{{ search_code_row.shall_comparator | split: "," | join: '", "' }}"{% endif %}
      {% if search_code_row.should_comparator %}- **SHOULD** support these `{{search_code}}` comparators: '{{ search_code_row.should_comparator | split: "," | join: '", "' }}"{% endif %}
      {% if search_code_row.shall_chain %}- **SHALL** support these chained  parameters: `{{ search_code_row.shall_chain | split: "," | join: '`, `' }}`{% endif %}
      {% if search_code_row.should_chain %}- **SHOULD** support these chained parameters:  `{{ search_code_row.should_chain | split: "," | join: '`, `' }}`{% endif %}
      {% if search_code_row.shall_include %}- **SHALL** support these `_include` parameters: `{{ search_code_row.shall_include | split: "," | join: '`, `' }}`{% endif %}
      {% if search_code_row.should_include %}- **SHOULD** support these `_include` parameters: `{{ search_code_row.should_include | split: "," | join: '`, `' }}`{% endif %}
   {%- endfor %}


   {% for search_code in search_codes %}
      {%- assign search_code_row = site.data.search_requirements | where:"code", search_code |  where: "base", type | first -%}
      {%- assign search_record = site.data.search_requirements | where:"code", search_code | where: "base", type | first -%}
      {%- assign search_type = search_record.type -%}
         {% if forloop.first %}`GET [base]/{{type}}?{% endif %}
      {{- search_code -}}
      {%- if search_code == '_id' %}=[id]
      {%- elsif search_code == '_lastUpdated' %}=[dateTime]
      {%- elsif search_code == '_tag' %}=[system]|[search_code]
      {%- elsif search_code == '_profile' %}=[type]
      {%- elsif search_code == '_security' %}=[system]|[search_code]
      {%- elsif search_code == '_text' %}=[string]
      {%- elsif search_code == '_content' %}=[string]
      {%- elsif search_code == '_list' %}=[id]
      {%- elsif search_code == '_has' %}=[string]
      {%- elsif search_code == '_type' %}=[uri]
      {%- elsif search_code == '_sort' %}=[string]
      {%- elsif search_code == '_count' %}=[number]
      {%- elsif search_code == '_include' %}=[string]
      {%- elsif search_code == '_revinclude' %}=[string]
      {%- elsif search_code == '_summary' %}=[search_code]
      {%- elsif search_code == '_total' %}=[search_code]
      {%- elsif search_code == '_elements' %}=[names]
      {%- elsif search_code == '_contained' %}=[search_code]
      {%- elsif search_code == '_containedType' %}=[search_code]
      {%- elsif search_code == '_filter' %}=[filter]
      {%- elsif search_code == '_query' %}=[name]&amp;[parameters]
      {%- elsif search_code == '_format' %}=[mime-type]
      {%- elsif search_code == '_pretty' %}=[true|false]
      {%- elsif search_type == 'reference' %}=[Type]/[id]
      {%- elsif search_type == 'status' %}=[status]
      {%- elsif search_type == 'composite' %}=[search_code]&amp;[value]
      {%- elsif search_type == 'uri' %}=[uri]
      {%- elsif search_type == 'string' %}=[{{search_code}}]
      {%- elsif search_type == 'date' %}={% if search_code_row.multipleAnd_conf and (search_code_row.shall_comparator or search_code_row.should_comparator) %}{gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}{% elsif search_code_row.multipleAnd_conf %}[dateTime]{&date=[dateTime]&...}{% elsif search_code_row.shall_comparator or search_code_row.should_comparator %}{gt|lt|ge|le}[dateTime]{% else %}[dateTime]{% endif %}
      {%- elsif search_type == 'token' %}={system}|[search_code]{% if search_code_row.multipleOr_conf %}{,{system|}[code],...}{% endif %}
      {%- else %}=[{{search_code}}]
      {%- endif -%}
      {%- unless forloop.last %}&{% else %}`{% endunless -%}
   {%- endfor %}

      Example:
      {%- assign examples = search.example | split: "~" -%}
      {% for ex in examples %}
      1. {{ ex }}
      {% endfor %}

      *Implementation Notes*: {{search.imp_note}} {% for search_type in search_types %}([how to search by {{search_type}}]{% unless forloop.last %} and {% endunless %}{% endfor %})

{% endfor -%}
{% endif %}


{% assign should_searches = site.data.search_requirements | where: "base", type | where: "base_conf", "SHOULD" -%}
{% if should_searches.size > 0 %}
#### Optional Search Parameters:

The following search parameters and search parameter combinations **SHOULD** be supported
{% for search in should_searches %}
{% assign search_codes = search.code | split: "," -%}
{% assign search_types = search.type | split: "," -%}
1. **SHOULD** {% if search.description %}{{search.description}}{% else %}support searching using {% if search_codes.size > 1 %}the combination of `[{{ search_codes | join: ']` and `[' }}]` search parameters{% else %}`[{{ search_codes }}]`{% endif %}{% endif %}:

   {% for search_code in search_codes %}
     {%- assign search_code_row = site.data.search_requirements | where:"code", search_code |  where: "base", type | first -%}
      {% if search_code_row.multipleAnd_conf %}- **{{ search_code_row.multipleAnd_conf }}** support *AND* search on `{{search_code}}` (e.g.`{{search_code}}=[date]&{{search_code}}=[date]&...`){% endif %}
      {% if search_code_row.multipleOr_conf %}- **{{ search_code_row.multipleOr_conf }}** support *OR* search on `{{search_code}}` (e.g.`{{search_code}}={system|}[code],{system|}[code],...`){% endif %}
      {% if search_code_row.shall_comparator %}- **SHALL** support these `{{search_code}}` comparators: "{{ search_code_row.shall_comparator | split: "," | join: '", "' }}"{% endif %}
      {% if search_code_row.should_comparator %}- **SHOULD** support these `{{search_code}}` comparators: '{{ search_code_row.should_comparator | split: "," | join: '", "' }}"{% endif %}
      {% if search_code_row.shall_chain %}- **SHALL** support these chained  parameters: `{{ search_code_row.shall_chain | split: "," | join: '`, `' }}`{% endif %}
      {% if search_code_row.should_chain %}- **SHOULD** support these chained parameters:  `{{ search_code_row.should_chain | split: "," | join: '`, `' }}`{% endif %}
      {% if search_code_row.shall_include %}- **SHALL** support these `_include` parameters: `{{ search_code_row.shall_include | split: "," | join: '`, `' }}`{% endif %}
      {% if search_code_row.should_include %}- **SHOULD** support these `_include` parameters: `{{ search_code_row.should_include | split: "," | join: '`, `' }}`{% endif %}
   {%- endfor %}


   {% for search_code in search_codes %}
      {%- assign search_code_row = site.data.search_requirements | where:"code", search_code |  where: "base", type | first -%}
      {%- assign search_record = site.data.search_requirements | where:"code", search_code | where: "base", type | first -%}
      {%- assign search_type = search_record.type -%}
         {% if forloop.first %}`GET [base]/{{type}}?{% endif %}
      {{- search_code -}}
      {%- if search_code == '_id' %}=[id]
      {%- elsif search_code == '_lastUpdated' %}=[dateTime]
      {%- elsif search_code == '_tag' %}=[system]|[search_code]
      {%- elsif search_code == '_profile' %}=[type]
      {%- elsif search_code == '_security' %}=[system]|[search_code]
      {%- elsif search_code == '_text' %}=[string]
      {%- elsif search_code == '_content' %}=[string]
      {%- elsif search_code == '_list' %}=[id]
      {%- elsif search_code == '_has' %}=[string]
      {%- elsif search_code == '_type' %}=[uri]
      {%- elsif search_code == '_sort' %}=[string]
      {%- elsif search_code == '_count' %}=[number]
      {%- elsif search_code == '_include' %}=[string]
      {%- elsif search_code == '_revinclude' %}=[string]
      {%- elsif search_code == '_summary' %}=[search_code]
      {%- elsif search_code == '_total' %}=[search_code]
      {%- elsif search_code == '_elements' %}=[names]
      {%- elsif search_code == '_contained' %}=[search_code]
      {%- elsif search_code == '_containedType' %}=[search_code]
      {%- elsif search_code == '_filter' %}=[filter]
      {%- elsif search_code == '_query' %}=[name]&amp;[parameters]
      {%- elsif search_code == '_format' %}=[mime-type]
      {%- elsif search_code == '_pretty' %}=[true|false]
      {%- elsif search_type == 'reference' %}=[Type]/[id]
      {%- elsif search_type == 'status' %}=[status]
      {%- elsif search_type == 'composite' %}=[search_code]&amp;[value]
      {%- elsif search_type == 'uri' %}=[uri]
      {%- elsif search_type == 'string' %}=[{{search_code}}]
      {%- elsif search_type == 'date' %}={% if search_code_row.multipleAnd_conf and (search_code_row.shall_comparator or search_code_row.should_comparator) %}{gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}{% elsif search_code_row.multipleAnd_conf %}[dateTime]{&date=[dateTime]&...}{% elsif search_code_row.shall_comparator or search_code_row.should_comparator %}{gt|lt|ge|le}[dateTime]{% else %}[dateTime]{% endif %}
      {%- elsif search_type == 'token' %}={system}|[search_code]{% if search_code_row.multipleOr_conf %}{,{system|}[code],...}{% endif %}
      {%- else %}=[{{search_code}}]
      {%- endif -%}
      {%- unless forloop.last %}&{% else %}`{% endunless -%}
   {%- endfor %}

      Example:
      {%- assign examples = search.example | split: "~" -%}
      {% for ex in examples %}
      1. {{ ex }}
      {% endfor %}

      *Implementation Notes*: {{search.imp_note}} {% for search_type in search_types %}([how to search by {{search_type}}]{% unless forloop.last %} and {% endunless %}{% endfor %})

{% endfor -%}
{% endif %}
