Skip to content This repository Explore Gist Blog Help XiaoJu Zhang
juvion 7 Watch Star 35 Fork 12davidensinger/davidensinger.github.io
branch: source davidensinger.github.io/app/\_layouts/post.html David
Ensingerdavidensinger on Nov 11, 2014 Add previous, next JS navigation
to site. 1 contributor 59 lines (58 sloc) 3.104 kb RawBlameHistory ---
page-class: page-post --- {% include header.html %}

{{ page.title }} {.entry-title}
================

<div class="entry-meta entry-meta--header">

<span class="entry-meta--icon"> {% include icons/icon-clock.svg %}
</span> {{ page.date | date: "%B %d, %Y" }}

</div>

<div class="entry-content">

{{ content }}

</div>

<div class="entry-meta--footer__top entry-meta--suggested__tweet">

### Spread the Word {.suggested-tweet--title}

{% capture suggested\_tweet %}https://twitter.com/intent/tweet?text={%
if page.suggested\_tweet.text %}{{ page.suggested\_tweet.text |
cgi\_escape }}{% else %}{{ page.title | cgi\_escape }}{% endif %}&url={{
site.url }}{{ page.url }}&via={{ site.twitter }}{% if
page.suggested\_tweet.related %}&related={{
page.suggested\_tweet.related | join: ',' | cgi\_escape }}{% else
%}&related={{ site.twitter }}{% endif %}{% if
page.suggested\_tweet.hashtags %}&hashtags={{
page.suggested\_tweet.hashtags | join: ',' | cgi\_escape }}{% endif %}{%
if page.suggested\_tweet.in\_reply\_to %}&in\_reply\_to={{
page.suggested\_tweet.in\_reply\_to }}{% endif %}{% endcapture %} [<span
class="suggested-tweet--bubble__text">{% if page.suggested\_tweet.text
%}{{ page.suggested\_tweet.text }}{% else %}{{ page.title }}{% endif
%}</span> {% if page.suggested\_tweet.hashtags %} {% for hashtag in
page.suggested\_tweet.hashtags %} <span
class="suggested-tweet--hashtag">\#{{ hashtag }}</span> {% endfor %} {%
endif %}]({{%20suggested_tweet%20}})
[<span class="suggested-tweet--icon">{% include icons/icon-twitter.svg
%}</span>Click to Tweet]({{%20suggested_tweet%20}}) (you may edit before
posting.)

</div>

{% if page.tags != empty %}

<div class="entry-meta--footer__bottom">

{% if page.tags != empty %} <span class="entry-meta--icon"> {% include
icons/icon-tag.svg %} </span> {% for tag in page.tags %} [{{ tag
}}](/tag/{{%20tag%20|%20slugify%20}}){% if forloop.last == false %}, {%
endif %} {% endfor %} {% endif %}

</div>

{% endif %}

{% if page.previous %}

<div class="nav-previous">

<span id="js-navigation--previous">[{{ page.previous.title
}}]({{%20site.url%20}}{{%20page.previous.url%20}})</span>

</div>

{% endif %} {% if page.next %}

<div class="nav-next">

<span id="js-navigation--next">[{{ page.next.title
}}]({{%20site.url%20}}{{%20page.next.url%20}})</span>

</div>

{% endif %} {% include footer.html %} Status API Training Shop Blog
About © 2015 GitHub, Inc. Terms Privacy Security Contact

