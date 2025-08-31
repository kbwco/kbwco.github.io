---
title: Sitemap
blurb: This is a listing of all the pages on here.
---
[Home/About](/)

## Categories
Main page: [Categories](/categories.html)
{% for category in site.categories -%}
* [{{category.title}}]({{category.url}})
{% endfor %}

## Sets
Main page: [Sets](/sets.html)
{% for set in site.sets -%}
* [{{set.title}}]({{set.url}})
{% endfor %}

## Cards
Main page: [Cards](/cards.html)
{% for card in site.cards -%}
* [{{card.title}}]({{card.url}})
{% endfor %}
