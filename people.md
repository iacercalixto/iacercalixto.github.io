---
layout: page
title:  Collaborators
---

## Students

### Master in Artificial Intelligence

{% assign sts = site.data.students | where: "selected", "y"  %}
{% for st in sts %}
  {% if st.rel == "mscthesis" %}
  * <a href="{{ st.link }}">{{ st.name }}</a>. {{ st.about }}
  {% endif %}
{% endfor %}

### Individual Projects in Artificial Intelligence

{% for st in sts %}
  {% if st.rel == "projai" %}
  * <a href="{{ st.link }}">{{ st.name }}</a>. {{ st.about }}
  {% endif %}
{% endfor %}

## Mentors

{% assign mentors = site.data.collaborators | where: "selected", "y" %}
{% for m in mentors %}
  {% include person.html person=m %}
{% endfor %}

