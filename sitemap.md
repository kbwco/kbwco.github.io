---
title: Sitemap
note: This is a listing of all the pages on here.
---
[Home/About](/)

## Basics
{% for basic in site.basics -%}
* [{{basic.title}}]({{basic.url}})
{% endfor %}

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

## Games
Main page: [Games](/games.html)
{% for game in site.games -%}
* [{{game.title}}]({{game.url}})
{% endfor %}
