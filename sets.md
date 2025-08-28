---
title: Sets
---
This is all the sets. To see a list of individual cards, go to the 
[Cards page](/cards.html).

## Chronological List
{% assign sets = site.sets | sort: "number" %}
{% for set in sets %}
* [{{set.title}}]({{set.url}})
{% endfor %}

## Alphabetical List
{% assign sets = site.sets | sort: "title" %}
{% assign current_letter = "" %}
{% for set in sets %}
{% assign first_char = set.title | slice: 0, 1 | upcase %}
{% if first_char != current_letter %}
{% unless forloop.first %}</ul>{% endunless %}
### {{first_char}}
<ul>
{% assign current_letter = first_char %}
{% endif %}
<li><a href="{{set.url}}">{{set.title}}</a></li>
{% if forloop.last %}</ul>{% endif %}
{% endfor %}
