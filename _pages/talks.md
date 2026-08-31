---
layout: page
title: talks
permalink: /talks/
description: conference presentations
nav: true
nav_order: 3
---

<div class="publications">

    <!-- {% assign sorted_talks = site.talks | sort: "date" | reverse %} -->
    {% assign visible_talks = site.talks | where_exp: "talk", "talk.hidden != true" %}
    {% assign sorted_talks = visible_talks | sort: "date" | reverse %}
    {% assign current_year = "" %}

    {% for talk in sorted_talks %}

    <!-- add hidden flag -->
    {% unless talk.hidden %} 

    {% assign talk_year = talk.date | date: "%Y" %}

    {% if talk_year != current_year %}
    {% unless forloop.first %}
    </ol>
    {% endunless %}

    <h2 class="year">{{ talk_year }}</h2>
    <ol class="bibliography">

        {% assign current_year = talk_year %}
        {% endif %}

        <li>

            <div class="row">

                <!-- Talk type badge -->
                <div class="col col-sm-2 abbr">
                    {% if talk.type %}
                    <abbr class="badge rounded w-100">
                        {{ talk.type }}
                    </abbr>
                    {% endif %}
                </div>

                <!-- Main talk information -->
                <div class="col-sm-10">

                    <!-- Title -->
                    <div class="title">
                        {% assign talk_content = talk.content | strip %}

                        {% if talk_content != "" %}
                        <a href="{{ talk.url | relative_url }}">
                            {{ talk.title }}
                        </a>
                        {% else %}
                        {{ talk.title }}
                        {% endif %}
                    </div>

                    <!-- Speaker -->
                    {% if talk.speaker %}
                    <div class="author">
                        {{ talk.speaker }}
                    </div>
                    {% endif %}

                    <!-- Venue / event / date -->
                    <div class="periodical">
                        {% if talk.event %}
                        <em>{{ talk.event }}</em>
                        {% elsif talk.venue %}
                        <em>{{ talk.venue }}</em>
                        {% endif %}

                        {% if talk.location %}
                        · {{ talk.location }}
                        {% endif %}

                        {% if talk.date %}
                        · {{ talk.date | date: "%b %Y" }}
                        {% endif %}
                    </div>

                    <!-- Links / Buttons -->
                    {% if talk.slides or talk.publication or talk.website %}
                    <div class="links">

                        {% if talk.slides %}
                        {% if talk.slides contains '://' %}
                        <a href="{{ talk.slides }}" class="btn btn-sm z-depth-0" role="button">
                            Slides
                        </a>
                        {% else %}
                        <a href="{{ talk.slides | relative_url }}" class="btn btn-sm z-depth-0" role="button">
                            Slides
                        </a>
                        {% endif %}
                        {% endif %}

                        {% if talk.publication %}
                        {% if talk.publication contains '://' %}
                        <a href="{{ talk.publication }}" class="btn btn-sm z-depth-0" role="button">
                            Publication
                        </a>
                        {% else %}
                        <a href="{{ talk.publication | relative_url }}" class="btn btn-sm z-depth-0" role="button">
                            Publication
                        </a>
                        {% endif %}
                        {% endif %}

                        {% if talk.website %}
                        <a href="{{ talk.website }}" class="btn btn-sm z-depth-0" role="button">
                            Website
                        </a>
                        {% endif %}

                    </div>
                    {% endif %}

                    <!-- Research tags -->
                    {% if talk.research %}
                    <div class="research-tags links">
                    
                        {% for tag in talk.research %}
                        {% assign research_item = site.data.research[tag] %}
                    
                        {% if research_item %}
                        <a class="research-tag btn btn-sm z-depth-0" href="{{ research_item.url | relative_url }}" role="button">
                            {{ research_item.title }}
                        </a>
                        {% endif %}
                    
                        {% endfor %}
                    
                    </div>
                    {% endif %}

                </div>
            </div>

        </li>

        {% if forloop.last %}
    </ol>
    {% endif %}

    {% endunless %}

    {% endfor %}

</div>