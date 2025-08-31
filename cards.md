---
title: Cards
note: This is the alphabetical listing of all cards. To find cards by set, see the
  [Sets page](/sets.html).
---
{%- assign cards = site.cards | sort_natural: "title" -%}
{%- assign current_letter = "" -%}
{%- for card in cards %}
{%- assign first_char = card.title | slice: 0, 1 | upcase -%}
{%- if first_char != current_letter -%}
{% unless forloop.first %}</ul>{% endunless %}
<h2 id="{{first_char}}">{{first_char}}</h2>
<ul>
{%- assign current_letter = first_char -%}
{% endif %}
<li><a href="{{card.url}}">{{card.title}}</a>{% if card.alternates %} - x{{card.alternates|size|plus:1}}{% endif %}</li>
{% if forloop.last %}</ul>{% endif %}
{% endfor %}
