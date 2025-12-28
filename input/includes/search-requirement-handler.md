{%- comment %} invoke with {% include search-requirement-handler.md conf_verb="SHOULD|SHALL" search=search %}  note that the parent variables are inherited  e.g resource_type, encounter_codes, and code_codes {% endcomment -%}

{% assign conf_verb = include.conf_verb -%}
{% assign search_row = include.search -%}
{% assign search_codes = search_row.code | split: "," -%}
{% assign search_types = search_row.type | split: "," -%}
{%- comment %} search requirement details {% endcomment -%}
1. **{{conf_verb}}** {% if search_row.description %}{{search_row.description}} using {% else %}support searching using {% endif %}{% if search_codes.size > 1 %}the combination of [{{ search_codes | join: '] and [' }}] search parameters{% else %} the [{{ search_codes[0] }}] search parameter{% endif %}:

   {% for search_code in search_codes %}
     {%- assign search_code_row = site.data.search_requirements | where:"code", search_code |  where: "base", resource_type | first -%}
      {% if search_code_row.multipleAnd_conf %}- Including {% if search_code_row.multipleAnd_conf == "SHOULD" %} optional {% endif %} support for *AND* search on `{{search_code}}` (e.g.`{{search_code}}=[date]&{{search_code}}=[date]&...`){% endif %}
      {% if search_code_row.multipleOr_conf %}- Including {% if search_code_row.multipleOr_conf == "SHOULD" %} optional {% endif %} support *OR* search on `{{search_code}}` (e.g.`{{search_code}}={system|}[code],{system|}[code],...`){% endif %}
      {% if search_code_row.shall_comparator %}- Including support for these `{{search_code}}` comparators: "{{ search_code_row.shall_comparator | split: "," | join: '", "' }}"{% endif %}
      {% if search_code_row.should_comparator %}- Including optional support for these `{{search_code}}` comparators: '{{ search_code_row.should_comparator | split: "," | join: '", "' }}"{% endif %}
      {% if search_code_row.shall_chain %}- Including support for these chained  parameters: `{{ search_code_row.shall_chain | split: "," | join: '`, `' }}`{% endif %}
      {% if search_code_row.should_chain %}- Including optional support for these chained parameters:  `{{ search_code_row.should_chain | split: "," | join: '`, `' }}`{% endif %}
      {% if search_code_row.shall_include %}- Including support for these `_include` parameters: `{{ search_code_row.shall_include | split: "," | join: '`, `' }}`{% endif %}
      {% if search_code_row.should_include %}- Including optional support for these `_include` parameters: `{{ search_code_row.should_include | split: "," | join: '`, `' }}`{% endif %}
   {%- endfor %}

{% comment %} Search syntax {% endcomment %}
   {% for search_code in search_codes %}
      {%- assign search_code_row = site.data.search_requirements | where:"code", search_code |  where: "base", resource_type | first -%}
      {%- assign search_record = site.data.search_requirements | where:"code", search_code | where: "base", resource_type | first -%}
      {%- assign search_type = search_record.type -%}
         {% if forloop.first %}`GET [base]/{{type}}?{% endif %}
      {{- search_code -}}
      {%- if search_code == '_id' %}=[id]' or 'GET [base]/{{type}}/[id]
      {%- elsif search_code == '_lastUpdated' %}=[dateTime]
      {%- comment -%} {%- elsif search_code == '_tag' %}=[system]|[search_code]
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
      {%- elsif search_code == '_pretty' %}=[true|false] {%- endcomment -%}
      {%- elsif search_type == 'reference' %}={% if search_code == 'patient' %}{Patient/}[id]{% else %}{Type/}[id]{% endif %}
      {%- elsif search_type == 'status' %}=[status]
      {%- elsif search_type == 'composite' %}=[search_code]&amp;[value]
      {%- elsif search_type == 'uri' %}=[uri]
      {%- elsif search_type == 'string' %}=[{{search_code}}]
      {%- elsif search_type == 'date' %}={% if search_code_row.multipleAnd_conf and (search_code_row.shall_comparator or search_code_row.should_comparator) %}{gt|lt|ge|le}[dateTime]{&date={gt|lt|ge|le}[dateTime]&...}{% elsif search_code_row.multipleAnd_conf %}[dateTime]{&date=[dateTime]&...}{% elsif search_code_row.shall_comparator or search_code_row.should_comparator %}{gt|lt|ge|le}[dateTime]{% else %}[dateTime]{% endif %}
      {%- elsif search_type == 'token' %}={system|}[search_code]{% if search_code_row.multipleOr_conf %}{,{system|}[code],...}{% endif %}
      {%- else %}=[{{search_code}}]
      {%- endif -%}
      {%- unless forloop.last %}&{% else %}`{% endunless -%}
   {%- endfor %}
{% comment %} Search examples from the csv file replace '!CATEGORYNNN' and '!CODENNN' where NNN is 1, 2, 3 etc when code variables are needed{% endcomment %}
      Example:
      {%- assign examples = search_row.example | split: "~" -%}
      {% for ex in examples %}
      1.  {% assign display_example = ex -%}
          {% if fixed_categories -%}
          {% for code in fixed_categories -%}
          {%- assign category_placeholder = '!CATEGORY' | append: forloop.index -%}
          {% assign display_example = ex | replace: category_placeholder, code -%}
          {% endfor -%}
          {% endif -%}
          {% if code_codes -%}
          {% for code in code_codes -%}
          {%- assign code_placeholder = '!CODE' | append: forloop.index -%}
          {% assign display_example = display_example | replace: code_placeholder, code -%}
          {% endfor -%}
          {% endif -%}
        {{ display_example }}
      {% endfor %}
{% comment %} add in implementation notes from the csv file, replace '!CATEGORYNNN' and '!CODENNN' where NNN is 1, 2, 3 etc when code variables are needed - for easier reading, just the code - no system  {% endcomment %}
      *Implementation Notes*: {% assign imp_notes = search_row.imp_note -%}
          {% if fixed_categories -%}
          {% for code in fixed_categories -%}
          {%- assign replacement_code = code | split: '|' | last -%}
          {%- assign category_placeholder = '!CATEGORY' | append: forloop.index -%}
          {% assign imp_notes = search_row.imp_note | replace: category_placeholder, replacement_code -%}
          {% endfor -%}
          {% endif -%}
          {% if code_codes -%}
          {% for code in code_codes -%}
          {%- assign replacement_code = code | split: '|' | last -%}
          {%- assign code_placeholder = '!CODE' | append: forloop.index -%}
          {% assign imp_notes = imp_notes | replace: code_placeholder, replacement_code -%}
          {% endfor -%}
          {% endif %}
        {{ imp_notes | replace: resource_type, profile_name }}{%- if search_codes[0] == '_id' %} (see [Parameters for all resources]{% endif %}{% for search_type in search_types %} ([how to search by {{search_type}}]{% unless forloop.last %} and {% endunless %}{% endfor %}).
{% comment %} create a reference links list of relative url for search parameters {% endcomment %}
{% for search_code in search_codes %}
[{{search_code}}]: {% assign search_code_row = site.data.search_requirements | where:"code", search_code |  where: "base", resource_type | first %}{{search_code_row.rel_url}}
{% endfor %}