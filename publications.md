---
layout: page
title:  Selected Publications
---

{% assign hashes = site.data.publications %}
{% capture posts %}
  {% for hash in hashes %}
    |{{ hash.year }}###{{ hash.paper-type }}###{{ hash.doc-url }}###{{ hash.journal-url }}###{{ hash.title }}###{{ hash.booktitle }}###{{ hash.journal }}###{{ hash.authors }}###{{ hash.code }}###{{ hash.bibtex }}###{{ hash.venues }}###{{ hash.bibtex_file }}###{{ hash.selected }}###
  {% endfor %}
{% endcapture %}
{% assign sortedhashes = posts | split: '|' | sort | reverse %}
{% for hash in sortedhashes %}
  {% assign hashitems = hash | split: '###' %}
  {% assign venues = hashitems[10] | split: ',' %}
  [comment]: <> {{ hashitems[0] }}
  {% if hashitems[12] != 'y' %}
    {% continue %}
  {% endif %}
  {% if hashitems[4] == "" or hashitems[4] == nil %}
    {% break %}
  {% endif %}


  {% if hashitems[1] == "inproceedings" and hashitems[2] != "" -%}
  * <a href="{{ hashitems[2] }}">{{ hashitems[4] }}</a>
  {% elsif hashitems[1] == "article" and hashitems[3] != "" -%}
  * <a href="{{ hashitems[3] }}">{{ hashitems[4] }}</a>
  {% else -%}
  * <a href="{{ hashitems[8] }}">{{ hashitems[4] }}</a>
  {% endif %}<br/>
  {{ hashitems[7] }}.
  {% if hashitems[1] == "inproceedings" %}*In: {{ hashitems[5] }}*, {{ hashitems[0]}}.
  {% elsif hashitems[1] == "article" %}*{{ hashitems[6] }}*, {{ hashitems[0]}}.
  {% endif %}<br/>
  {%- unless venues contains "notpublic" -%}
  <a href="{{ hashitems[11] }}" >![bib](/assets/img/publication_icons/button_bib.png){:height="25px"}</a>&nbsp;
  {%- endunless -%}
  {%- for venue in venues -%}
    {%- if venue == "conference" -%}
  ![conference](/assets/img/publication_icons/button_conference.png){:height="25px"}&nbsp;
    {%- elsif venue == "journal" -%}
  ![journal](/assets/img/publication_icons/button_journal.png){:height="25px"}&nbsp;
    {%- elsif venue == "workshop" or hashitems[10] == "sharedtask" -%}
  ![workshop](/assets/img/publication_icons/button_workshop.png){:height="25px"}&nbsp;
    {%- elsif venue == "preprint" -%}
  ![preprint](/assets/img/publication_icons/button_preprint.png){:height="25px"}&nbsp;
    {%- elsif venue == "long" -%}
  ![long paper/article](/assets/img/publication_icons/button_long.png){:height="25px"}&nbsp;
    {%- elsif venue == "short" -%}
  ![short paper/article](/assets/img/publication_icons/button_short.png){:height="25px"}&nbsp;
    {%- elsif venue == "bestpaper" -%}
  ![nopublic](/assets/img/publication_icons/button_bestpaper.png){:height="25px"}&nbsp;
    {%- endif %}
  {%- endfor -%}
{% endfor %}

