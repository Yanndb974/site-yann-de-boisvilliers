---
layout: default
---
{% include files.html %}

## About

{% if photo_path != "" %}<img class="profile-picture" src="{{ photo_path | relative_url }}" alt="Portrait of Yann de Boisvilliers" width="140" height="140">{% endif %}

I am a master's student in sociology and computational social science. I study French continuous news channels, combining sociology of journalism with the computational analysis of large broadcast corpora. I am interested in how professional routines, formats and competition between channels shape what becomes news, and in building the tools needed to observe this systematically.

In 2026–27 I am enrolled in the M2 in Quantitative Sociology and Computational Social Sciences at Institut Polytechnique de Paris, after a first master's year at Université Paris-Dauphine – PSL.

Research interests: sociology of media and journalism; computational social science.

## Research

**The Laudisi Observatory.** I designed and maintain a pipeline that records, transcribes and analyses the output of French continuous news channels: stream capture, automatic speech recognition, speaker diarisation and OCR of on-screen banners. The first complete corpus covers March 2026: about 2,230 hours of broadcast.

The project examines agenda and framing dynamics across channels: how far they converge in the topics they cover and the words they use, which channel takes up a topic first, and who gets to speak on air, including the gap between how often women are seen and how often they are heard.

Methods: topic segmentation and clustering; sentence embeddings.

{% comment %} Quand l'intégration Gallicagram sera publique, ajouter à la fin du premier paragraphe de cette rubrique :
     The transcripts are reused in Gallicagram. {% endcomment %}

## Talks

* *Montrées plus qu’entendues&nbsp;? Mesurer en continu l’écart entre présence à l’écran et accès à la parole des femmes sur les chaînes d’information françaises.*{:lang="fr"} Study day <span lang="fr">«&nbsp;Mesurer la diversité de genre dans les contenus médiatiques&nbsp;: l’apport des sciences sociales computationnelles&nbsp;»</span>, Grenoble, 30 November 2026 (forthcoming).
* *The Laudisi Observatory: A computational pipeline for framing and agenda dynamics in French continuous news.* [Computational Humanities Research Group Seminar Series](https://www.kcl.ac.uk/events/series/computational-humanities-research-group-seminar-series), King’s College London (online), 9 September 2026.

## Education

* Master's (M2), Quantitative Sociology and Computational Social Sciences, Institut Polytechnique de Paris, 2026–27. Thesis supervised by Marshall A. Taylor (ENSAE-CREST).
* Master's (M1), Économie et sociétés, Université Paris-Dauphine – PSL, Mines Paris – PSL and EHESS, 2025–26. Thesis: *L’Observatoire Laudisi&nbsp;: Sociologie computationnelle de l’information en continu française (mars 2026)*{:lang="fr"}, supervised by Samuel Bouron and Antoine Mazières.
* Licence (bachelor's), Sciences pour un monde durable, Université PSL, 2022–25. Major in economics and social sciences; minors in health and environment and in ecosystem management.

## Research experience

* Research intern, computational analysis of the media landscape. Institut des sciences sociales du politique (ENS Paris-Saclay), February–July 2026. Automated collection and quantitative analysis of broadcast data, supervised by Baptiste Coulmont (ENS Paris-Saclay) and Benoît de Courson (LSE).
* Research stay, London School of Economics, June 2026.
* Research assistant, agricultural mobilisations and digital reconfigurations. LISIS, Université Gustave Eiffel (Champs-sur-Marne), March–June 2025. Digital ethnography of agricultural YouTube channels and text analysis of about two million comments, supervised by Baptiste Kotras and Sylvain Brunier.
* Research assistant, due-diligence regulation. LEDa, Université Paris-Dauphine – PSL, 2024 (three months, one day a week). Contributed to a study of the effects of due-diligence rules (Dodd–Frank Act) on global supply chains, supervised by Ninon Moreau-Kastler.

## Awards and funding

* Prix de la Recherche IMPACT TANK × L’Ascenseur, April 2026, for my M1 thesis on the Laudisi Observatory.
* Mobility grant, Social Sciences Graduate Programme, Université Paris-Dauphine – PSL, 2026.

## Contact {#contact}

<ul>
  <li>Email: <a href="mailto:yann.deboisvilliers@psl.eu">yann.deboisvilliers@psl.eu</a></li>
  {% if cv_path != "" %}<li><a href="{{ cv_path | relative_url }}" target="_blank" rel="noopener">CV (PDF)</a></li>{% endif %}
  <li><a href="https://www.linkedin.com/in/yann-de-boisvilliers-875ab8275">LinkedIn</a></li>
</ul>

{% comment %} GitHub, quand le compte sera public : ajouter dans la liste ci-dessus
     <li><a href="https://github.com/IDENTIFIANT">GitHub</a></li> {% endcomment %}
