---
layout: page
permalink: /about/index.html
title: About Me
tags: [genomics, bioinformatics]
imagefeature: kaichop.jpg
chart: true
---
<figure>
  <img src="{{ site.url }}/images/kaichop.jpg" alt="Kai Wang">
  <figcaption>Kai Wang</figcaption>
</figure>

{% assign total_words = 0 %}
{% assign total_readtime = 0 %}
{% assign featuredcount = 0 %}
{% assign statuscount = 0 %}

{% for post in site.posts %}
    {% assign post_words = post.content | strip_html | number_of_words %}
    {% assign readtime = post_words | append: '.0' | divided_by:200 %}
    {% assign total_words = total_words | plus: post_words %}
    {% assign total_readtime = total_readtime | plus: readtime %}
    {% if post.featured %}
    {% assign featuredcount = featuredcount | plus: 1 %}
    {% endif %}
{% endfor %}


My name is **Kai Wang**, and this is my personal blog. It currently has {{ site.posts | size }} posts in {{ site.categories | size }} categories which combinedly have {{ total_words }} words, which will take an average reader ({{ site.wpm }} WPM) approximately <span class="time">{{ total_readtime }}</span> minutes to read. {% if featuredcount != 0 %}There are <a href="{{ site.url }}/featured">{{ featuredcount }} featured posts</a>, you should definitely check those out.{% endif %} The most recent post is {% for post in site.posts limit:1 %}{% if post.description %}<a href="{{ site.url }}{{ post.url }}" title="{{ post.description }}">"{{ post.title }}"</a>{% else %}<a href="{{ site.url }}{{ post.url }}" title="{{ post.description }}" title="Read more about {{ post.title }}">"{{ post.title }}"</a>{% endif %}{% endfor %} which was published on {% for post in site.posts limit:1 %}{% assign modifiedtime = post.modified | date: "%Y%m%d" %}{% assign posttime = post.date | date: "%Y%m%d" %}<time datetime="{{ post.date | date_to_xmlschema }}" class="post-time">{{ post.date | date: "%d %b %Y" }}</time>{% if post.modified %}{% if modifiedtime != posttime %} and last modified on <time datetime="{{ post.modified | date: "%Y-%m-%d" }}" itemprop="dateModified">{{ post.modified | date: "%d %b %Y" }}</time>{% endif %}{% endif %}{% endfor %}. The last commit was on {{ site.time | date: "%A, %d %b %Y" }} at {{ site.time | date: "%I:%M %p" }} [UTC](http://en.wikipedia.org/wiki/Coordinated_Universal_Time "Temps Universel Coordonné").

I am an Assistant Professor at the [ZNI](http://www.keck.usc.edu/zni) at **USC**. I am the PI of a lab, doing research on human genetics and genomics. I got my PhD from **UW** and did my postdoc at [UPENN](http://www.upenn.edu) and [CHOP](http://www.chop.edu).

*[ZNI]: Zilkha Neurogenetic Institute
*[UW]: University of Washington
*[UPENN]: University of Pennsylvania
*[USC]: University of Southern California
*[CHOP]: Children's Hospital of Philadelphia

<figure>
	<img src="{{ site.url }}/images/zniparty.jpg" alt="ZNI costume contest 2015">
	<figcaption>Our lab at ZNI costume contest 2015</figcaption>
</figure>

I was born and brought up in Honghu, China. It is beautiful city.

<figure class="third">
	<a href="{{ site.url }}/images/about/honghu7.jpg"><img src="{{ site.url }}/images/about/honghu7.jpg"></a>
	<a href="{{ site.url }}/images/about/honghu8.jpg"><img src="{{ site.url }}/images/about/honghu8.jpg"></a>
	<a href="{{ site.url }}/images/about/honghu9.jpg"><img src="{{ site.url }}/images/about/honghu9.jpg"></a>
	<a href="{{ site.url }}/images/about/honghu10.jpg"><img src="{{ site.url }}/images/about/honghu10.jpg"></a>
	<a href="{{ site.url }}/images/about/honghu11.jpg"><img src="{{ site.url }}/images/about/honghu11.jpg"></a>
	<a href="{{ site.url }}/images/about/honghu12.jpg"><img src="{{ site.url }}/images/about/honghu12.jpg"></a>
</figure>
<figure class="half">
	<a href="{{ site.url }}/images/about/honghu2.jpg"><img src="{{ site.url }}/images/about/honghu2small.jpg"></a>
	<a href="{{ site.url }}/images/about/honghu4.jpg"><img src="{{ site.url }}/images/about/honghu4small.jpg"></a>
	<figcaption>Scene on Lotus Garden and Yellow River (photo taken by me in Honghu).</figcaption>
</figure>

If you are interested in genomics, I hope you will enjoy reading my blog.
