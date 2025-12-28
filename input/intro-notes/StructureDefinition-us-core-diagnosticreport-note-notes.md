<!--input/intro-notes/StructureDefinition-us-core-condition-encounter-diagnosis-notes.md -->
<!-- establish the page context and get type,title,optionally fixed-categories and code lists (remember to escape "|" with "\|" ) -->
{% assign id = include.id %}
{% assign sd = site.data.structuredefinitions[id] %}
{% assign type = sd.type %}
{% assign title = sd.title %}

<!-- {% raw %} {% include quickstart-intro.md %} {% endraw %} -->

{% include quickstart-search.md type=type title=title fixed_categories="http://loinc.org\|LP29708-2" code_codes="http://loinc.org\|45033-8" %}

{% include link-list.md %}