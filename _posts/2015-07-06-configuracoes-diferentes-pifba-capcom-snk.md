---
layout: post
title: 'RetroPie: configuração de controles distintas para jogos de luta SNK e CAPCOM'
date: '2015-07-06T23:33:00.000-03:00'
author: meleu
tags:
- retropie
- games
- raspberry pi
modified_time: '2015-07-15T22:58:41.453-03:00'
blogger_id: tag:blogger.com,1999:blog-1613465446497619833.post-9004026733378655198
blogger_orig_url: http://mdicas.blogspot.com/2015/07/pra-quem-nao-sabe-o-que-e-retropie-e.html
---
[update em 11/06/2016: este "macete" só tem utilidade para o pifba. Quem usa o fba do libretro não precisa disso!]

Pra quem não sabe o que é RetroPie e nem Raspberry Pi, eu recomendo uma visita nos seguintes links:

- [https://retropie.org.uk/](https://retropie.org.uk/)
- [https://www.raspberrypi.org/](https://www.raspberrypi.org/)


**OBSERVAÇÃO:**
Como o RetroPie é um projeto relativamente novo, algumas coisas estão mudando assim que novas versões são lançadas,
como por exemplo arquivos de configuração e os seus respectivos diretórios. Então é bom frisar que o esquema explicado
aqui foi realizado no RetroPie 3.0 beta 4 (também testei no 2.6, mas alguns diretórios são diferentes).

### PROBLEMA

No RetroPie o emulador utilizado para a maioria dos jogos de luta de arcade é FinalBurn Alpha (ou fba, ou ainda pifba,
omo a versão para Raspberry Pi é chamada). Só que diferentemente do MAME, o FBA não tem como configurar os controles
individualmente por jogo. E aí que começa o meu problema. Pois eu costumo jogar num controle de PlayStation2, utilizando
o seguinte esquema:

- quadrado: soco fraco
- triângulo: soco forte
- xis: chute fraco
- bola: chute forte
- R1: soco médio [CAPCOM]
- R2: chute médio [CAPCOM]

O problema é que nos games CAPCOM temos o soco/chute médio, e nos games SNK não temos. Aí a configuração que eu
considero ideal para um já não fica legal no outro. Pois aqui vou descrever como contornar este problema.

### SOLUÇÃO

#### passo 1

- Colocar as roms dos jogos SNK no diretório `/home/pi/RetroPie/roms/neogeo`. No meu caso foram as várias edições de Art of Fighting, Samurai Shodown, Metal Slug, Fatal Fury e King of Fighters. O sistema vai continuar executando o pifba para jogar estas roms, mas fazendo desta forma o emulationstation vai ficar mais organizadinho.
- Colocar as roms CAPCOM no diretório `/home/pi/RetroPie/roms/fba`. No meu caso foram os Street Fighter da vida, Marvel vs Capcom, X-Men vs Street Fighter (infelizmente não rodou Street Fighter 3).

#### passo 2

Criar dois arquivos de configuração distintos para SNK e CAPCOM.

Um vai se chamar `/opt/retropie/configs/fba/fba2x.cfg-neogeo`:

```
### meleu: ARQUIVO DE CONFIGURACAO DOS BOTOES PARA JOGAR JOGOS DA SNK ###
#########################################################################
[Keyboard]
# Get codes from /usr/include/SDL/SDL_keysym.h
A_1=306
B_1=32
X_1=308
Y_1=304
L_1=122
R_1=120
START_1=13
SELECT_1=9
LEFT_1=276
RIGHT_1=275
UP_1=273
DOWN_1=274
QUIT=27
#player 2 keyboard controls, disabled by default
A_2=999
B_2=999
X_2=999
Y_2=999
L_2=999
R_2=999
START_2=999
SELECT_2=999
LEFT_2=999
RIGHT_2=999
UP_2=999
DOWN_2=999

[Joystick]
# Get codes from "jstest /dev/input/js0"
# from package "joystick"
# quadrado = soco fraco
A_1=3
# triangulo = soco forte
B_1=0
# xis = chute fraco
X_1=2
# bolinha = chute forte
Y_1=1
L_1=7
R_1=5
START_1=9
SELECT_1=8
#Joystick axis
JA_LR=0
JA_UD=1
#player 2 button configuration
A_2=3
B_2=0
X_2=2
Y_2=1
L_2=7
R_2=5
START_2=9
SELECT_2=8
#Joystick axis
JA_LR_2=0
JA_UD_2=1

[Graphics]
DisplaySmoothStretch=1
# Display Effect: 0 none, 1 scanlines
DisplayEffect=0
DisplayBorder=0
MaintainAspectRatio=1

[Sound]
### FINAL DO ARQUIVO ###
```

O outro arquivo vai se chamar `/opt/retropie/configs/fba/fba2x.cfg-capcom`:

```
### meleu: ARQUIVO DE CONFIGURACAO DOS BOTOES PARA JOGAR JOGOS DA CAPCOM ###
############################################################################
[Keyboard]
# Get codes from /usr/include/SDL/SDL_keysym.h
A_1=306
B_1=32
X_1=308
Y_1=304
L_1=122
R_1=120
START_1=13
SELECT_1=9
LEFT_1=276
RIGHT_1=275
UP_1=273
DOWN_1=274
QUIT=27
#player 2 keyboard controls, disabled by default
A_2=999
B_2=999
X_2=999
Y_2=999
L_2=999
R_2=999
START_2=999
SELECT_2=999
LEFT_2=999
RIGHT_2=999
UP_2=999
DOWN_2=999

[Joystick]
# Get codes from "jstest /dev/input/js0"
# from package "joystick"
### meleu: lembrando que eu costumo utilizar um controle de ps2
# A = soco fraco = quadrado
A_1=3
# B = soco forte = triangulo
B_1=0
# X = soco medio = R1
X_1=7

# Y = chute fraco = xis
Y_1=2
# L = chute médio = R2
L_1=5
# R = chute forte = bola
R_1=1

START_1=9
SELECT_1=8
#Joystick axis
JA_LR=0
JA_UD=1
#player 2 button configuration
A_2=3
B_2=0
X_2=7
Y_2=2
L_2=5
R_2=1
START_2=9
SELECT_2=8
#Joystick axis
JA_LR_2=0
JA_UD_2=1

[Graphics]
DisplaySmoothStretch=1
# Display Effect: 0 none, 1 scanlines
DisplayEffect=0
DisplayBorder=0
MaintainAspectRatio=1

[Sound]
### FINAL DO ARQUIVO ###
```

#### passo 3

Mudar o dono do arquivo `/opt/retropie/configs/fba/fba2x.cfg`, executando o seguinte comando:

```
chown pi.pi /opt/retropie/configs/fba/fba2x.cfg
```

Isso vai permitir que possamos alterar este arquivo no esquema a seguir.


#### passo 4

Copiar o arquivo `/etc/emulationstation/es_systems.cfg` para seu diretório pessoal, executando o seguinte comando:

```
cp /etc/emulationstation/es_systems.cfg ~/.emulationstation/es_systems.cfg
```

#### passo 5

O `es_systems.cfg` é um arquivo XML relativamente fácil de entender. Primeiro vamos procurar pela entrada referente ao neogeo. Estará algo assim:

```xml
...
  <system>
    <name>neogeo</name>
    <fullname>Neo Geo</fullname>
    <path>~/RetroPie/roms/neogeo</path>
    <extension>.zip .fba .ZIP .FBA</extension>
    <command>/opt/retropie/supplementary/runcommand/runcommand.sh 0 _SYS_ neogeo %ROM%</command>
    <platform>neogeo</platform>
    <theme>neogeo</theme>
  </system>
...
```

Na linha onde está o `<command>` nós vamos alterar para o seguinte:

```xml
<command>(cd /opt/retropie/configs/fba/ && cat fba2x.cfg-neogeo > fba2x.cfg) && /opt/retropie/supplementary/runcommand/runcommand.sh 0 _SYS_ neogeo %ROM%</command>
```

Em seguida vamos fazer a mesma coisa com a entrada referente ao fba. Ela estará assim:

```xml
...
  <system>
    <name>fba</name>
    <fullname>Final Burn Alpha</fullname>
    <path>~/RetroPie/roms/fba</path>
    <extension>.fba .zip .FBA .ZIP</extension>
    <command>/opt/retropie/supplementary/runcommand/runcommand.sh 0 _SYS_ fba %ROM%</command>
    <platform>arcade</platform>
    <theme>fba</theme>
  </system>
...
```

Alterar a linha do `<command>` para o seguinte:

```xml
<command>(cd /opt/retropie/configs/fba/ && cat fba2x.cfg-capcom > fba2x.cfg) && /opt/retropie/supplementary/runcommand/runcommand.sh 0 _SYS_ fba %ROM%</command>
```

### finalizando

Reiniciar o emulationstation e pronto!
