---
title: Games
note: This is a list of all the games that were played with friends. For sets created, 
  go to the [Sets page](/sets.html)
---
## Chronological List
{% assign games = site.games | sort: "number" %}
{% for game in games -%}
1. [{{game.title}}]({{game.url}})
{% endfor %}
