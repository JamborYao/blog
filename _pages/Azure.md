---
layout: page
title: All Post
permalink: /archives/all/
order: 4
share: false
---

<div id="search-results">
    <hr id="first-hr" class="with-no-margin"/>

    {% for post in site.posts %}
    <div class="article-wrapper">
        <article>
            {% include article-header.html page=post link=true share=false eye_catch=false %}
        </article>
    </div>
    <hr class="with-no-margin"/>
    {% endfor %}
</div>