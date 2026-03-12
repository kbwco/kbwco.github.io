---
title: Statistics
---
<div class="alt-infoboxes">
{%- assign cards = site.cards -%}
{%- assign num-unique-cards = cards | size -%}
{%- assign num-total-cards = num-unique-cards -%}
{%- for card in cards -%}
{%- if card.alternates -%}
{%- assign num-alternates = card.alternates | size -%}
{%- assign num-total-cards = num-total-cards | plus: num-alternates -%}
{%- endif -%}
{%- endfor %}
{%- assign num-players = site.players | size -%}
{%- assign avg-cards-per-player = num-total-cards | divided_by: num-players -%}
<div class="alt-infobox-stats">
    <div class="infobox-title">Cards</div>
    <table class="infobox-table">
        <tr>
            <th>Total Cards</th>
            <td>{{num-total-cards}}</td>
        </tr>
        <tr>
            <th>Total Unique Cards</th>
            <td>{{num-unique-cards}}</td>
        </tr>
    </table>
</div>

<div class="alt-infobox-stats">
    <div class="infobox-title">Sets</div>
    <table class="infobox-table">
        <tr>
            <th>Total Sets</th>
            <td>{{site.sets|size}}</td>
        </tr>
        <tr>
            <th>Average Cards per Set</th>
            <td>{% include average-cards-per-set.html sets=site.sets -%}</td>
        </tr>
        <tr>
            <th>Smallest Set(s)</th>
            <td>{% include smallest-set.html sets=site.sets author=true %}</td>
        </tr>
        <tr>
            <th>Largest Set(s)</th>
            <td>{% include largest-set.html sets=site.sets author=true %}</td>
        </tr>
    </table>
</div>

<div class="alt-infobox-stats">
    <div class="infobox-title">Games</div>
    <table class="infobox-table">
        <tr>
            <th>Total Games</th>
            <td>{{site.games|size}}</td>
        </tr>
        <tr>
            <th>Average Cards Made per Game</th>
            <td>{% include average-cards-per-game.html games=site.games %}</td>
        </tr>
        <tr>
            <th>Least Cards Made in a Game</th>
            <td>{% include smallest-cards-in-game.html games=site.games %}</td>
        </tr>
        <tr>
            <th>Most Cards Made in a Game</th>
            <td>{% include largest-cards-in-game.html games=site.games %}</td>
        </tr>
    </table>
</div>

<div class="alt-infobox-stats">
    <div class="infobox-title">Players</div>
    <table class="infobox-table">
        <tr>
            <th>Total Players</th>
            <td>{{num-players}}</td>
        </tr>
        <tr>
            <th>Average Cards Made per Player</th>
            <td>{{avg-cards-per-player}}</td>
        </tr>
        <tr>
            <th>Player(s) with the Least Created Cards</th>
            <td>{% include smallest-cards-by-player.html players=site.players %}</td>
        </tr>
        <tr>
            <th>Player(s) with the Most Created Cards</th>
            <td>{% include largest-cards-by-player.html players=site.players %}</td>
        </tr>
    </table>
</div>

<div class="alt-infobox-stats">
    <div class="infobox-title">Categories</div>
    <table class="infobox-table">
        <tr>
            <th>Total Categories</th>
            <td>{{site.categories|size}}</td>
        </tr>
    </table>
</div>
</div>
