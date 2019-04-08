---
layout: page
title:  Publications
---

{% assign hashes = site.data.publications %}
{% capture posts %}
  {% for hash in hashes %}
    |{{ hash.year }}###{{ hash.paper-type }}###{{ hash.doc-url }}###{{ hash.journal-url }}###{{ hash.title }}###{{ hash.booktitle }}###{{ hash.journal }}###{{ hash.authors }}###{{ hash.code }}###
  {% endfor %}
{% endcapture %}
{% assign sortedhashes = posts | split: '|' | sort | reverse %}
{% for hash in sortedhashes %}
  {% assign hashitems = hash | split: '###' %}
  [comment]: <> {{ hashitems[0] }}
  {% if hashitems[4] == "" or hashitems[4] == nil %}
    {% break %}
  {% endif %}

  {% if hashitems[1] == "inproceedings" and hashitems[2] != "" %}
  * <a href="{{ hashitems[2] }}">{{ hashitems[4] }}</a>
  {% elsif hashitems[1] == "article" and hashitems[3] != "" %}
  * <a href="{{ hashitems[3] }}">{{ hashitems[4] }}</a>
  {% else %}
  * <a href="{{ hashitems[8] }}">{{ hashitems[4] }}</a>
  {% endif %}<br/>
  {{ hashitems[7] }}.
  {% if hashitems[1] == "inproceedings" %}*In: {{ hashitems[5] }}*, {{ hashitems[0]}}.
  {% elsif hashitems[1] == "article" %}*{{ hashitems[6] }}*, {{ hashitems[0]}}.
  {% endif %}

{% endfor %}


