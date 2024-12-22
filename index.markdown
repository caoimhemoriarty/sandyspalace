---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Home

---
<div>
  <p>
    Good day! You look reasonably sane!
  </p>
  <p>
    I'm Rosa and this is my gay little website.
  </p>
</div>

<div>
  <h1>
    Blog posts:
  </h1>
</div>

<div>
  {% for post in paginator.posts %}
  <article>
    <span href="{{ post.url | relative_url }}">
      <time datetime="{{ post.date | date_to_xmlschema }}" class="post-date" style="display: inline-block; margin-right: 5px;">{{ post.date | date_to_string }}</time>
      -
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </span>
  </article>
  {% endfor %}
</div>
