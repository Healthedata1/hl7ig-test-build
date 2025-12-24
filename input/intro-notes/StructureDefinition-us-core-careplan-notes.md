<!--input/intro-notes/StructureDefinition-us-core-allergyintolerance-notes.md -->
<!-- establish the page context and get type -->
{% assign id = include.id %}
{% assign sd = site.data.structuredefinitions[id] %}
{% assign type = sd.type %}
{% assign url = sd.url %}

<!-- {% raw %} {% include quickstart-intro.md %} {% endraw %} -->

{% include quickstart-search.md type=type id=id url=url %}

{% include link-list.md %}