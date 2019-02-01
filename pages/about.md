---
layout: page
title: About
description: Ximing Li's Homepage 
keywords: Ximing Li 
comments: true
menu: 关于
permalink: /about/
subtitle:   <h3>Download My CV</h3>
            <a role="button" class="btn btn-primary hvr-grow-shadow" href="/assets/files/CV_en.pdf" target="_blanks">
                <span class="flag-icon flag-icon-gb"></span> English
            </a>
            <a role="button" class="btn btn-primary hvr-grow-shadow" href="/assets/files/CV_cn.pdf" target="_blanks">
                <span class="flag-icon flag-icon-cn"></span> 中文
            </a>
                            
---

## Contact 

{% for website in site.data.social %}
* {{ website.sitename }}：[@{{ website.name }}]({{ website.url }})
{% endfor %}

## Skill Keywords

{% for category in site.data.skills %}
### {{ category.name }}
<div class="btn-inline">
{% for keyword in category.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
