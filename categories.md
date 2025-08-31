---
title: Categories
note: This is a list of all the categories of cards. To see a list of individual cards, 
  go to the [Cards page](/cards.html).
---
## Visual Diagram
This is a visual diagram of all the categories

<a href="/assets/images/categories/diagram/current.png" target="_blank">
<img src="/assets/images/categories/diagram/current.png" alt="Category Diagram">
</a>

## Chronological List
{% assign categories = site.categories | sort: "number" %}
{% for category in categories -%}
1. [{{category.title}}]({{category.url}})
{% endfor %}

## Alphabetical List
{% assign categories = site.categories | sort: "title" %}
{% assign current_letter = "" %}
{% for category in categories %}
{% assign first_char = category.title | slice: 0, 1 | upcase %}
{% if first_char != current_letter %}
{% unless forloop.first %}</ul>{% endunless %}
### {{first_char}}
<ul>
{% assign current_letter = first_char %}
{% endif %}
<li><a href="{{category.url}}">{{category.title}}</a></li>
{% if forloop.last %}</ul>{% endif %}
{% endfor %}
