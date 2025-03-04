---
layout: page
title: Projects
order: 2
---

Here is a list of some selected projects I have completed. These projects touch on mobile robots, quadrotors, and computer vision, among other things.

For more information, visit my <a href="//github.com/{{ site.author.github }}" target="_blank"><b>Github page</b> <i class="fa fa-external-link"></i></a>.

<hr/>

<div>
{% assign sorted_projects = site.projects | sort:"order" %}

{% for project in sorted_projects %}

    <div>
    <br/>

    <h3>{{ project.title }}</h3><br/>

    {% if project.img %}
        <img class="right" style="width: 40%; padding-left: 1em" src="{{ project.img }}">
    {% endif %}

    {% assign sorted_pubs = project.publications | sort:"date" %}

    {% for publication in sorted_pubs reversed %}

        {% if publication.links.doi %}
            <a href="{{ publication.links.doi }}" target="_blank"><b>{{ publication.title }}</b></a>
        {% else %}
            <b>{{ publication.title }}</b>
        {% endif %}
        <br/>

        <i>{{ publication.authors }}</i>
        <br/>

        {{ publication.venue }}
        <br/>

        {% if publication.note %}
            <i>{{ publication.note }}</i><br/>
        {% endif %}

        {% if publication.award %}
            <b>{{ publication.award }}</b><br/>
        {% endif %}

        {% if publication.links.preprint %}
            <a href="{{ publication.links.preprint }}" target="_blank"><i class="far fa-file-alt"></i>&nbsp;Preprint</a>&nbsp;
        {% endif %}

        {% if publication.links.code %}
            <a href="{{ publication.links.code }}" target="_blank"><i class="fas fa-code-branch"></i>&nbsp;Code</a>&nbsp;
        {% endif %}

        {% if publication.links.slides %}
            <a href="{{ publication.links.slides }}" target="_blank"><i class="fas fa-desktop"></i>&nbsp;Slides</a>&nbsp;
        {% endif %}

        {% if publication.links.poster %}
            <a href="{{ publication.links.poster }}" target="_blank"><i class="far fa-image"></i>&nbsp;Poster</a>&nbsp;
        {% endif %}

        {% if publication.links.video %}
            <a href="{{ publication.links.video }}" target="_blank"><i class="fab fa-youtube"></i>&nbsp;Video</a>&nbsp;
        {% endif %}

        {% if publication.links %}
            <br/>
        {% endif %}

        <br/>
    {% endfor %}

    </div>
    <hr/>
{% endfor %}
</div>
