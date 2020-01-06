---
layout: default
title: home
---
# home
Estou tentando fazer do github meu novo lar na web. Passei algum tempo no
blogspot, depois até tentei wordpress, mas quando vi o que dava para fazer
no github, resolvi tentar. Acho que é mais o meu estilo...

Mais um pouco sobre mim em [about](/about).

A seção de [textos](/txts/) possui alguns textos que escrevi.

Em [projetos](/projetos) pode-se ver no que eu ando me metendo ultimamente.

E o [blog](/blog/) é onde vou colocando algumas nerdezas que
vou aprendendo por aí. (Se você gosta de shell scripts e linha de comando,
também vale uma visita num blog que criei exclusivamente para esse tema:
[https://meleu.sh/](https://meleu.sh/))

Postagens mais recentes do blog:
<ul class="posts">

    {% for post in site.posts limit:3 %}
    <li><span>{{ post.date | date_to_string }}</span>: <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
