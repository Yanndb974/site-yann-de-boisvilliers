---
ref: home
title: Yann de Boisvilliers
---
<section class="intro row">
<img class="portrait" src="{{ site.photo | relative_url }}" alt="Portrait of Yann de Boisvilliers" width="800" height="1000">
<div class="body">
<p class="lede">I study French continuous news channels, combining the sociology of journalism with the computational analysis of large broadcast corpora.</p>
<p>I am a master’s student in quantitative sociology and computational social science at Institut Polytechnique de Paris. Since March 2026, the <a href="{{ '/research/' | relative_url }}#laudisi">Laudisi Observatory</a>, a pipeline I designed, has been recording and transcribing French news channels.</p>
<p class="actions"><a href="{{ '/research/' | relative_url }}">Research</a> <a href="{{ '/cv/' | relative_url }}">CV</a> <a href="mailto:{{ site.email }}">Email</a></p>
</div>
</section>

<section aria-labelledby="news">
<h2 id="news">News</h2>
{% include timeline.html items=site.data.news %}
</section>
