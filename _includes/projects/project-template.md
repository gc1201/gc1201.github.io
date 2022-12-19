# {{ page.name }}
<br>
#### Overview
{{ page.description }}

{% if page.impact %}
#### Impact
{{ page.impact }}
{% endif %}

<p>

{% if page.roles.size > 0 %}
    Role: {% for role in page.roles %}
    <span class="badge badge-pill text-primary border border-primary ml-1">{{ role }}</span>
    {% endfor %}
    <br>
{% endif %}

{% if page.tags.size > 0 %}
    Tag: {% for tag in page.tags %}
    <span class="badge badge-pill text-primary border border-primary ml-1">{{ tag }}</span>
    {% endfor %}
{% endif %}
</p>


{% if page.images.size > 0 %}
{% assign carousel_images = page.images %}
{% include elements/carousel.html %}
{% endif %}

{% if page.tableau %}
{{ page.tableau }}
{% endif %}

{% if page.project_url %}
<p class="text-center">
{% include elements/button.html link=page.project_url text="Visit Project Link" %}
</p>
{% endif %}

{% if page.project_doc %}
<p class="text-center">
{% assign project_doc_url = "/assets/files/" | append: page.project_doc %}
{% include elements/button.html link=project_doc_url text="Read Project Doc" %}
</p>
{% endif %}

{% if page.media_url %}
<p class="text-center">
{% include elements/button.html link=page.media_url text="Check Project Media" %}
</p>
{% endif %}

{% if page.embedded_video %}
{{ page.embedded_video }}
{% endif %}