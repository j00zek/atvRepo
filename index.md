---
title: E2KodiPlayer pliki
---

<style>
.footer {
  display: none;
}

.png-gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 1rem;
  list-style: none;
  padding: 0;
}

.png-gallery img {
  display: block;
  max-width: 100%;
  height: auto;
  margin-top: 0.5rem;
}
</style>

# E2KodiPlayer APKs

{% assign static_files = site.static_files | sort: "name" %}
{% for file in static_files %}
{% assign extension = file.extname | downcase %}
{% if extension == ".apk" %}
- [{{ file.name | escape }}]({{ file.path | relative_url }})
{% endif %}
{% endfor %}

# Podgląd plików PNG

<ul class="png-gallery">
{% for file in static_files %}
{% assign extension = file.extname | downcase %}
{% if extension == ".png" %}
  <li>
    <a href="{{ file.path | relative_url }}">{{ file.name | escape }}</a>
    <a href="{{ file.path | relative_url }}">
      <img src="{{ file.path | relative_url }}" alt="Podgląd {{ file.name | escape }}" loading="lazy">
    </a>
  </li>
{% endif %}
{% endfor %}
</ul>
