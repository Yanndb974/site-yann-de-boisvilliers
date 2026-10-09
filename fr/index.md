---
ref: home
title: Yann de Boisvilliers
permalink: /fr/
---
<section class="intro row">
<img class="portrait" src="{{ site.photo | relative_url }}" alt="Portrait de Yann de Boisvilliers" width="800" height="1000">
<div class="body">
<p class="lede">J’étudie les chaînes d’information en continu françaises, en associant la sociologie du journalisme à l’analyse computationnelle de grands corpus audiovisuels.</p>
<p>Je suis étudiant en master de sociologie quantitative et sciences sociales computationnelles à l’Institut Polytechnique de Paris. Depuis mars 2026, l’<a href="{{ '/fr/recherche/' | relative_url }}#laudisi">Observatoire Laudisi</a>, une chaîne de traitement que j’ai conçue, enregistre et transcrit les chaînes d’information françaises.</p>
<p class="actions"><a href="{{ '/fr/recherche/' | relative_url }}">Recherche</a> <a href="{{ '/fr/cv/' | relative_url }}">CV</a> <a href="mailto:{{ site.email }}">Courriel</a></p>
</div>
</section>

<section aria-labelledby="actualites">
<h2 id="actualites">Actualités</h2>
{% include timeline.html items=site.data.news %}
</section>
