+++
draft = true
+++

## Teaching

Here is a list of courses that I TA'ed.

{% for course in site.data.teaching %}
- {{ course.id }} {{ course.title }} \| {{ course.term }}, {{ course.institute }}
	- Instructor: {{ course.instructor }}
{%- if course.role %}
	- Role: {{ course.role }}
{%- endif %}
{% endfor %}
