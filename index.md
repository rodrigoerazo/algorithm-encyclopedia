# Kyopro Encyclopedia of Algorithms (β版)

<dl>
{% for entry in site.entries %}
    {% if entry.draft %}
        <dt>{{ entry.title }}{% for url in entry.draft_urls %} <a href="{{ url }}" class="link-external">{% octicon link-external height:16 %}</a>{% endfor %}</dt>
        <dd>{{ entry.description }}</dd>
    {% else %}
        <dt><a href="{{ site.baseurl }}{{ entry.url }}">{{ entry.title }}</a></dt>
        <dd>{{ entry.description }}</dd>
    {% endif %}
{% endfor %}
</dl>

<div class="github-links">
    <a href="{{ site.github.repository_url }}">GitHub repository</a>
</div>
