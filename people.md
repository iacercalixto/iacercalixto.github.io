{% assign curryear = 2022 | plus: 0 %}

I often collaborate with <a href="https://kik.amc.nl/home/aabuhanna/">Ameen Abu-Hanna</a>, <a href="https://www.amsterdamumc.org/en/research/researchers/joanna-e.-klopotowska.htm">Joanna Klopotowska</a>, and <a href="https://www.amsterdamumc.org/en/research/researchers/iacopo-vagliano.htm">Iacopo Vagliano</a> in the Amsterdam UMC/UvA, and with <a href="https://ssc.io">Sebastian Schelter</a> in the Informatics Institute/UvA.

### PhD students

{% assign sts = site.data.students | where: "selected", "y" %}
{% for st in sts %}
  {% if st.alumnus != True %}
    {% if st.rel == "phdthesis" %}
  * <a href="{{ st.link }}">{{ st.name }}</a> ({{ st.month }} {{ st.year }}--, {{ st.institution }}). {{ st.about }} {% if st.cosupervised %} (Co-supervised with {{ st.cosupervisor }}) {% endif %}
    {% endif %}
  {% endif %}
{% endfor %}

### MSc/BSc students

{% assign sts = site.data.students | where: "selected", "y" %}
{% for st in sts %}
  {% if st.year == curryear %}
    {% if st.rel == "mscthesis" and st.institution == "UvA" %}
  * <a href="{{ st.link }}">{{ st.name }}</a> ({{ st.year }}--, {{ st.relation }}, {{ st.institution }}). {{ st.about }} {% if st.cosupervised %} (Co-supervised with {{ st.cosupervisor }}) {% endif %}
    {% endif %}
    {% if st.rel == "srp" and st.institution == "Amsterdam UMC" %}
  * <a href="{{ st.link }}">{{ st.name }}</a> ({{ st.year }}--, {{ st.relation }}, {{ st.institution }}/UvA). {{ st.about }} {% if st.cosupervised %} (Co-supervised with {{ st.cosupervisor }}) {% endif %}
    {% endif %}
    {% if st.rel == "projai" and st.institution == "UvA" %}
  * <a href="{{ st.link }}">{{ st.name }}</a> ({{ st.year }}--, {{ st.relation }}, {{ st.institution }}). {{ st.about }} {% if st.cosupervised %} (Co-supervised with {{ st.cosupervisor }}) {% endif %}
    {% endif %}
    {% if st.rel == "projai" and st.institution == "Center for Data Science, NYU" %}
  * <a href="{{ st.link }}">{{ st.name }}</a> ({{ st.year }}--, {{ st.relation }}, {{ st.institution }}). {{ st.about }} {% if st.cosupervised %} (Co-supervised with {{ st.cosupervisor }}) {% endif %}
    {% endif %}
  {% endif %}
{% endfor %}

## Alumni

### MSc/BSc students

{% assign sts = site.data.students | where: "selected", "y" %}
{% for st in sts %}
  {% if st.year < curryear %}
    {% if st.rel == "mscthesis" and st.institution == "UvA" %}
  * <a href="{{ st.link }}">{{ st.name }}</a> ({{ st.month }} {{ st.year }}, {{ st.relation }}, {{ st.institution }}). {{ st.about }} {% if st.cosupervised %} (Co-supervised with {{ st.cosupervisor }}) {% endif %}
    {% endif %}
    {% if st.rel == "projai" and st.institution == "UvA" %}
  * <a href="{{ st.link }}">{{ st.name }}</a> ({{ st.month }} {{ st.year }}, {{ st.relation }}, {{ st.institution }}). {{ st.about }} {% if st.cosupervised %} (Co-supervised with {{ st.cosupervisor }}) {% endif %}
    {% endif %}
    {% if st.rel == "projai" and st.institution == "Center for Data Science, NYU" %}
  * <a href="{{ st.link }}">{{ st.name }}</a> ({{ st.year }}--, {{ st.relation }}, {{ st.institution }}). {{ st.about }} {% if st.cosupervised %} (Co-supervised with {{ st.cosupervisor }}) {% endif %}
    {% endif %}
  {% endif %}
{% endfor %}


