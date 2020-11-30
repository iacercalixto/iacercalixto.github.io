---
layout: page
title:  Collaborators
---

## New York University, Center for Data Science

### Individual Project Supervision

{% assign sts = site.data.students | where: "selected", "y" | where: "institution", "NYU" %}
{% for st in sts %}
  {% if st.rel == "projai" %}
  * <a href="{{ st.link }}">{{ st.name }}</a> ({{ st.date }}). {{ st.about }}
  {% endif %}
{% endfor %}


## Master in Artificial Intelligence, University of Amsterdam

### Students' theses

{% assign sts = site.data.students | where: "selected", "y" | where: "institution", "UvA" %}
{% for st in sts %}
  {% if st.rel == "mscthesis" %}
  * <a href="{{ st.link }}">{{ st.name }}</a> ({{ st.date }}). {{ st.about }}
  {% endif %}
{% endfor %}

### Students' Individual Projects

{% for st in sts %}
  {% if st.rel == "projai" %}
  * <a href="{{ st.link }}">{{ st.name }}</a> ({{ st.date }}). {{ st.about }}
  {% endif %}
{% endfor %}

## Mentors

{% assign mentors = site.data.collaborators | where: "selected", "y" %}
{% for m in mentors %}
  {% include person.html person=m %}
{% endfor %}

