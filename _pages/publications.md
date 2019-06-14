---
title: "Publications by year"
permalink: /publications/
pubs:
  - key: ""
    author: "<b>Ximing Li</b>,"
    title: ""
    keywords: ""
    month: ""
    year: ""
    address: ""
    booktitle: ""
    url: 
    bibtex: 
    slides:
    hidden:
    type:
    school:
    journal:

---

<ul class="taxonomy__index">
  {% assign pubsInYear = page.pubs | group_by_exp: 'pub', 'pub.year | year: "%Y"' %}
  {% for year in pubsInYear %}
    <li>
      <a href="#{{ year.name }}">
        <strong>{{ year.name }}</strong> <span class="taxonomy__count">{{ year.items | size }}</span>
      </a>
    </li>
  {% endfor %}
</ul>

{% assign pubsByYear = page.pubs | group_by_exp: 'pub', 'pub.year | year: "%Y"' %}
{% for year in pubsByYear %}
  <section id="{{ year.name }}" class="taxonomy__section">
    <h2 class="archive__subtitle">{{ year.name }}</h2>
      {% for pub in year.items %}
        {% unless pub.hidden %}
           <li>
             {% if pub.url %} <a href="{{ pub.url }}">{{pub.title}}</a>.
             {% else %} {{pub.title}}.
             {% endif %}{% if pub.type %}({{pub.type}})
             {% endif %}
             {{pub.author}}.
             {% if pub.type == 'Technical Report' %}{{pub.number}}
             {% endif %}{{pub.booktitle}}{{pub.school}}{{pub.journal}}.
             {% if pub.address %}{{pub.address}}.
             {% endif %} {{pub.month}}, {{pub.year}}. {% if pub.slides %}<a href="{{ pub.slides }}">Slides</a>.
             {% endif %}{% if pub.key %} <a href="http://groups.csail.mit.edu/commit/bibtex.cgi?key={{pub.key}}">Bibtex</a>.
             {% endif %}{% if pub.bibtex %} <a href="{{ pub.bibtex }}">Bibtex</a>.
             {% endif %}
           </li>
        {% endunless %}
      {% endfor %}
    <a href="#page-title" class="back-to-top">{{ site.data.ui-text[site.locale].back_to_top | default: 'Back to Top' }} &uarr;</a>
  </section>
{% endfor %}
