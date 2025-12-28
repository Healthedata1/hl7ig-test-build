<!--input/intro-notes/StructureDefinition-us-core-patient-notes.md -->
<!-- establish the page context and get type,title,optionally fixed-categories and code lists (remember to escape "|" with "\|" ) -->
{% assign id = include.id %}
{% assign sd = site.data.structuredefinitions[id] %}
{% assign type = sd.type %}
{% assign title = sd.title %}

<!-- {% raw %} {% include quickstart-intro.md %} {% endraw %} -->

{% include quickstart-search.md type=type title=title %}

{% include link-list.md %}