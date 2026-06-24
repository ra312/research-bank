---
layout: default
title: Research Ideas
---

# ML Research Ideas

A running log of hypotheses, validation plans, and results.

{% assign posts_by_status = site.posts | group_by: "status" %}
{% assign status_order = "exploring,draft,validated,archived" | split: "," %}

{% if site.posts.size > 0 %}
  {% for status in status_order %}
    {% assign group = posts_by_status | where: "name", status | first %}
    {% if group.items.size > 0 %}
<div class="ideas-section">
<h2>{{ status | capitalize }}</h2>
<div class="ideas-grid">
      {% for post in group.items %}
<a class="idea-card" href="{{ post.url | relative_url }}">
<div class="card-meta">
<span class="status-badge status-{{ post.status }}">{{ post.status }}</span>
<time>{{ post.date | date: "%b %-d, %Y" }}</time>
{% if post.tags %}<span class="tags">{% for tag in post.tags %}<span class="tag">{{ tag }}</span>{% endfor %}</span>{% endif %}
</div>
<h3>{{ post.title }}</h3>
{% if post.eval_plan %}<p class="card-eval">{{ post.eval_plan | truncate: 120 }}</p>{% endif %}
</a>
      {% endfor %}
</div>
</div>
    {% endif %}
  {% endfor %}
{% else %}
<p>No ideas yet — <a href="{{ site.baseurl }}/admin/">add one via the CMS</a> or push a <code>.tex</code> file to <code>_tex/</code>.</p>
{% endif %}

---

**Validation checkpoint:** Can you see this equation? $E = mc^2$ (inline) and

$$\mathcal{L}(\param) = -\E_{x \sim \data}\!\left[\log p_\param(x)\right]$$

If both render as math (not raw LaTeX), Phase 1 is working.
