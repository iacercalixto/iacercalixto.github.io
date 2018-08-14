---
layout: photolist
title: People
menu: yes
---

## My mentors

{% assign students = site.data.people.colleagues | where: "selected", "y" %}
{% for person in students %}
{% include person.html person=person %}
{% endfor %}


## My students

{% assign students = site.data.people.students | where: "selected", "y" %}
{% for person in students %}
{% include person.html person=person %}
{% endfor %}
