---
layout: default
---
{%- include files.html -%}

<section class="intro{% if photo_path != '' %} row{% endif %}">
{%- if photo_path != "" %}
<img class="portrait" src="{{ photo_path | relative_url }}" alt="Portrait of Yann de Boisvilliers" width="400" height="500">
{%- endif %}
<div class="body">
<p class="lede">I study French continuous news channels, combining the sociology of journalism with the computational analysis of large broadcast corpora.</p>
<p>I am a master’s student in quantitative sociology and computational social science at Institut Polytechnique de Paris. Since March 2026, the <a href="{{ '/research/' | relative_url }}">Laudisi Observatory</a>, a pipeline I designed, has been recording and transcribing French news channels.</p>
</div>
</section>

<section aria-labelledby="news">
<h2 id="news">News</h2>
{% include timeline.html items=site.data.news %}
</section>
