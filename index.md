---
layout: default
title: home
---

# home

Este site é tipo minha casa na web. E assim como minha casa física, é um pouco bagunçado... :sweat_smile:

Em [my-notes](/my-notes/) eu vou deixando anotações sobre diversos assuntos que vou me interessando.
O público alvo destas anotações é **eu**, mas pode ser que alguém ache alguma coisa útil por lá... :shrug:

Em [artigos-traduzidos](/artigos-traduzidos/) eu publico alguns artigos relacionados à área de T.I. que vou traduzindo e que acredito que permanecerão relevantes por bastante tempo.

E o [blog](/blog/) é onde vou colocando algumas nerdezas que
vou aprendendo por aí. (Se você gosta de shell scripts e linha de comando,
também vale uma visita num blog que criei exclusivamente para esse tema:
[https://meleu.sh/](https://meleu.sh/))

Postagens mais recentes do blog:
<ul class="posts">

    {% for post in site.posts limit:5 %}
    <li><span>{{ post.date | date_to_string }}</span>: <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
