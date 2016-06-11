---
layout: default
title: home
---
# intro
Estou tentando fazer do github meu novo lar na web. Passei algum tempo no
blogspot, depois até tentei wordpress, mas quando vi o que dava para fazer
no github, resolvi tentar. Acho que é mais o meu estilo...

Mais um pouco sobre mim em [about](/about).

A seção de [textos](/txts/) possui alguns textos técnicos que escrevi.

E o [blog](/blog/) é onde vou colocando algumas nerdezas que
vou aprendendo por aí.

Postagens mais recentes do blog:
<ul class="posts">

    {% for post in site.posts limit:3 %}
    <li><span>{{ post.date | date_to_string }}</span>: <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></li>
    {% endfor %}
                                
</ul>

# projetos

No que eu estou me metendo ultimamente...

### meus projetos

[RetroPie-input-selection](https://github.com/meleu/RetroPie-input-selection) -
Um script (para usar no RetroPie) que permite ao usuário escolher qual
joystick será utilizado para controlar os players 1 ao 4 no RetroArch.

[.dotfiles](https://github.com/meleu/.dotfiles) - Isso não é um projeto
propriamente dito. É só uma cópia dos meus dotfiles do Linux para poder
replicar em todas as máquinas que eu uso.

[RetroArch-problematic-cheevos](https://github.com/meleu/RetroArch-problematic-cheevos) - Uma
coleção de savestates de jogos em pontos um pouco antes de realizar
um Achievement que é problemático no RetroArch e funciona normalmente nos
emuladores oficiais do RetroAchievements.

### projetos que acompanho
[RetroPie](http://retropie.org.uk/) - transforma seu Raspberry Pi numa
plataforma de videogames antigos.

[RetroArch](https://github.com/libretro/RetroArch) - Um frontend para vários
emuladores de games. Roda em inúmeras plataformas (as que eu uso são Android
e Linux). E possui suporte à [RetroAchievements](http://retroachievements.org).

[RetroAchievements](http://retroachievements.org) - Registre suas conquistas nos consoles clássicos:
NES/SNES/MegaDrive/GameBoy. (OK. Isso não é exatamente um "projeto", mas eu ando bastante interessado nisso ultimamente).

