<!-- {% raw %} Use for sorted flat list  Extension allows for highlighting new stuff using include parameter
{% include ext-list-generator.md use="use parameter" %}
use parameter (required) = realm_only|ig_only|deprecated|profile see profiles and extensions page for their contenxt
 {% endraw %}-->
{% assign titles = "" %}
{%- for sd_hash in site.data.structuredefinitions -%}
  {%- assign sd = sd_hash[1] -%}
  {%- if sd.type == "Extension" -%}
     {%- assign profile_meta_row = site.data.profile_metadata | where:"title", sd.title | first -%}
     {%- if include.use != "profile" and profile_meta_row[include.use] -%}
        {% assign titles = titles | append: "," | append: sd.title -%}
     {%-  elsif include.use == "profile" %}
      {% unless profile_meta_row.ig_only or profile_meta_row.realm_only or profile_meta_row.deprecated -%}
        {% assign titles = titles | append: "," | append: sd.title -%}
      {% endunless -%}
     {%- endif -%}
  {%- endif -%}
{% endfor %}
{% assign titles = titles | split: "," | sort | uniq %}
<ul>
  {% for title in titles %}
    {%- for sd_hash in site.data.structuredefinitions -%}
      {%- assign sd = sd_hash[1] -%}
      {%- if sd.title == title %}
        {%- assign new = false -%}
        {%- assign profile_meta_row = site.data.profile_metadata | where:"title", title | first -%}
        {%- if profile_meta_row.is_new  == "TRUE" -%}
            {%- assign new = true -%}
        {%- endif -%}
        {%- if new -%}
          <li>
            <a href="{{sd.path}}">
              <span class="bg-success" markdown="1">{{ title }}</span><!-- new-content --></a>
          </li>
        {% else %}
          <li>
            <a href="{{sd.path}}">{{ title }}</a>
          </li>
        {% endif %}
      {% endif %}
    {% endfor %}
  {% endfor %}
</ul>