<!-- Used to create a sorted list of US Core SearchParameters links displayed by title in markdown. It only list SearchParameters that are based on FHIR SearchParameters. It excludes US Core exclusively-defined SearchParameter.  It groups by type and sorts alphabetically and allows for highlighting new stuff using the new_stuff data file
-->

{% assign exclude_list = "us-core-condition-asserted-date,us-core-careteam-role,us-core-encounter-discharge-disposition,us-core-goal-description" %}
{% assign my_types = "" %}
{% for sd_hash in site.data.structuredefinitions %}
  {% assign my_types =  my_types | append: "," | append: sd_hash[1].type %}
{% endfor %}

{% assign my_array = my_types | split: "," %}
{% assign my_array = my_array | sort | uniq %}

{% for i in my_array offset:1 %}

#### {{i}}
    {%- assign sp_exist = false -%}
    {%- for resource_hash in site.data.resources -%}

      {%- assign resource_type = resource_hash[0] | split: '/' | first -%}
      {%- if resource_type == "SearchParameter" -%}
        {%- assign sp_id = resource_hash[0]  | split: '/' | last -%}
        {%- unless exclude_list contains sp_id -%}
            {%- assign words = sp_id | split: '-' -%}
            {%- assign sp_type = words[2] | strip -%}
            {%- assign i_lower = i | downcase | strip -%}
            {%- if sp_type == i_lower  %}
                {%- assign sp_exist = true -%}
                {%- assign new = false -%}
                {%- for new_stuff in site.data.new_stuff -%}
                    {%- if resource_hash[1].name == new_stuff -%}
                    {%- assign new = true -%}
                    {%- break -%}
                    {%- endif -%}
                {%- endfor -%}

                {%- capture titlecase -%}
                {% for word in words -%}
                {{ word | capitalize }}{% unless forloop.last %}-{% endunless %}
                {%- endfor %}
                {%- endcapture -%}
{% comment %} {{titlecase | inspect }} {% endcomment %}
- {% if new %}<span class="bg-success" markdown="1">{% endif %}[{{ titlecase | replace_first: 'Us', 'US' | replace: '-', ' '}}]({{resource_hash[1].path}}){% if new %}</span><!-- new-content -->{% endif %}
            {%- endif -%}
        {%- endunless -%}
    {%- endif -%}
   {%- endfor %}
{% unless sp_exist %} &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;⸺ {% endunless %}
{% endfor %}

