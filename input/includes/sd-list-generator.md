{%- for sd_hash in site.data.structuredefinitions -%}
  {%- assign sd1= sd_hash[1] -%}
  {%- unless sd1.type == "Extension" -%}
    {% assign types =  types | append: "," | append: sd1.type %}
  {%- endunless -%}
{% endfor %}
{% assign my_types = types | split: "," %}
{% assign my_types = my_types | sort | uniq %}
{% for i in my_types offset:1 %}
  <h4>{{ i }}</h4>
  <ul>
    {%- for sd_hash in site.data.structuredefinitions -%}
      {%- assign sd1 = sd_hash[1] -%}
      {%- if sd1.type == i %}
        {%- assign new = false -%}
        {%- assign parent = false -%}
        {%- assign child = false -%}
        {%- for sd_hash2 in site.data.structuredefinitions -%}
          {%- assign sd2 = sd_hash2[1] -%}
          {% if sd1.basename == sd2.name %}
            {%- assign child = true -%}
            {% break %}
          {% elsif sd1.name == sd2.basename%}
             {%- assign parent = true -%}
             {% break %}
          {% endif %}
        {% endfor %}

        {%- assign profile_meta_row = site.data.profile_metadata | where:"title", sd1.title | first -%}
          {%- if profile_meta_row.is_new  == "TRUE" -%}
                {%- assign new = true -%}
          {%- endif -%}

          {%- unless parent or child -%}
            {%- if new -%}
              <li><a href="{{sd1.path}}"><span class="bg-success" markdown="1">{{sd1.title}}</span><!-- new-content --></a></li>
            {% else %}
              <li><a href="{{sd1.path}}">{{sd1.title}}</a></li>
            {% endif %}
          {%- endunless -%}

          {%- if parent -%}
            {%- if new -%}
              <li><a href="{{sd1.path}}"><span class="bg-success" markdown="1">{{sd1.title}}</span><!-- new-content --></a>
            {% else %}
              <li><a href="{{sd1.path}}">{{sd1.title}}</a>
            {% endif %}
                <ul>
                {%- for sd_hash3 in site.data.structuredefinitions -%}
                  {%- assign sd3 = sd_hash3[1] -%}
                  {% if sd1.name == sd3.basename %}
                    {%- assign new = false -%}
                    {%- assign profile_meta_row = site.data.profile_metadata | where:"title", sd3.title | first -%}
                     {%- if profile_meta_row.is_new  == "TRUE" -%}
                           {%- assign new = true -%}
                      {%- endif -%}
                      {%- if new -%}
                        <li><a href="{{sd3.path}}"><span class="bg-success" markdown="1">{{sd3.title}}</span><!-- new-content --></a></li>
                      {% else %}
                        <li><a href="{{sd3.path}}">{{sd3.title}}</a></li>
                      {% endif %}

                  {% endif %}
                {% endfor %}
                </ul>
            </li>
          {%- endif -%}
      {%- endif -%}
    {%- endfor -%}
  </ul>
{% endfor %}
