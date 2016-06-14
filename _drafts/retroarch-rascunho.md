---
layout: post
title: configuração básica do RetroArch
date: 2016-06-13
tags:
- retroarch
- android
---

## intro

Esse texto tem como objetivo mostrar como instalar e configurar emuladores
de videogames antigos no Android (e acredito que no iPhone o processo é o mesmo).

Vamos usar o RetroArch, que é um software muito poderoso, cheio recursos,
totalmente livre e sem propaganda alguma(!). Ele age como se fosse uma
central de emuladores. Nele você terá em apenas um app os emuladores dos
clássicos Atari 2600, NES, Master System, Mega Drive, SNES e muitos outros
que estão disponíveis pra você escolher. Isso mesmo! Você não vai precisar
ficar caçando emuladores para cada videogame que você curte! Basta instalar
o RetroArch e a partir dele você terá disponível emuladores de diversos
sistemas.

Esse texto aborda o que considero o mínimo necessário para você jogar no
RetroArch. Mas ele é tão rico de recursos que isso aqui é só a ponta do iceberg.
Dá pra fazer muito mais, e deixá-lo com visual bem bacana. Depois tentarei
escrever sobre outras configurações possíveis.

Gostaria de deixar bem claro que os emuladores que eu utilizo vão no máximo
até SNES e MegaDrive. O RetroArch disponibiliza emuladores de sistemas não
tão antigos, como de Dreamcast, Nintendo 64 e PlayStation 1, mas o desempenho
pode variar muito. Eu não testei nenhum destes.

Uma coisa que a princípio pode causar estranheza, é que a nota do RetroArch
no Google Play Store não é tão alta. Mas lendo os comentários nota-se
claramente que muita gente dá nota baixa por não saber fazer as configurações
iniciais antes de começar a jogar. Foi para tentar mudar este cenário que
escrevi este texto (eu mesmo sofri um pouco até deixar o RetroArch do meu jeito).


## pré requisitos

Para tirar o máximo proveito do RetroArch no Android, são necessárias duas coisas:

- Joystick bluetooth
- ROMs dos jogos

Por padrão o RetroArch disponibiliza um joystick virtual, que fica na
tela e você comanda pelo touch screen. Mas eu não consigo ter prazer
algum jogando desta forma. Por isso acho que nem vale a pena jogar
os jogos dos videogames antigos pelo touch. Sem joystick, nem jogo.

Existem inúmeros modelos de joysticks bluetooth. Eu não experimentei vários, mas
posso falar de dois modelos que uso e estou muito satisfeito:

- ípega GT-9023 ([aqui tem um vídeo review bacana](https://www.youtube.com/watch?v=QROvmQq-D-4))
- [8Bitdo ZERO](http://www.8bitdo.com/zero/)

Não será abordado nesse texto como parear o joystick com o Android e nem
como obter as ROMs dos jogos. Então, supondo que você já tem um joystick
pareado com o seu Android e já tem ROMs no seu dispositivo, podemos começar.


## instalação

Sem mistério: vai no Google Play Store e instala o [RetroArch](https://play.google.com/store/apps/details?id=com.retroarch).

Atualmente (junho/2016) a versão disponível é a 1.3.4.


## interface com usuário

A primeira coisa a se estranhar no RetroArch é a sua interface com o usuário.
O comportamento do touch screen é um pouco diferente dos apps tradicionais.

Geralmente quando você toca em uma opção de um menu, você já está acionando
aquela opção. **No RetroArch você dá o primeiro toque para escolher, e então
toca novamente para acionar a opção escolhida**. Com o tempo você se acostuma.

**O tradicional botão de voltar do Android não funciona nessa interface
do RetroArch! Você tem que voltar por aquela setinha apontada para esquerda
que aparece lá no canto superior esquerdo** (quem usa iPhone já está
acostumado com esse comportamento).

**Observação**: Se você parear certinho seu joystick com o Android antes
de abrir o RetroArch, quando você abrí-lo é provável que ele já detecte
o seu joystick e aí você poderá navegar no menu através do direcional,
ativar/selecionar uma opção no botão equivalente ao A do SNES (ou bola
do PlayStation), voltar/cancelar no botão equivalente ao B do SNES (X no
PlayStation).

Não vou explicar aqui cada item dos menus do RetroArch. Você vai entendendo
sob demanda, a medida que formos avançando aqui no texto. Por enquanto só
importante que você observe que o ícone da casinha no canto inferior esquerdo
é o menu inicial; e o ícone da engrenagem no canto inferior direito acessa
o menu de configurações. Esse outro ícone aí no meio nós vamos ignorar.

images/retroarch/onlineupdater.png


## instalando os cores

Outra coisa a se acostumar ao usar o RetroArch é chamar os emuladores de
*cores*. Isso é outra coisa que já acaba confundindo os não-iniciados.
Então acostume-se: Cada emulador é chamado de core dentro do RetroArch.

Para instalar um core nós vamos fazer em `Online Updater` e em seguida
`Core Updater`, conforme as imagens abaixo:

images/retroarch/onlineupdater.png
images/retroarch/coreupdater.png

Agora vem mais uma fonte de confusão: existem vários cores para um mesmo sistema e
você não sabe qual escolher! Só para SNES, existem 10 disponíveis!!

Bem, até hoje eu não sei as diferenças, vantagens/desvantagens de cada core.
Portanto vou apenas indicar os que eu percebo que é mais comum
do pessoal instalar e que eu instalei e não tenho problema
algum.


Para NES (Nintendinho 8 bits) eu uso o FCEUmm:

images/retroarch/nescore.png


Para SNES (Super Nintendo) eu uso o Snes9x Next (já usei o Snes9x e não tive problema
algum, mas depois li em algum lugar que o Next tem uma performance melhor):

images/retroarch/snescore.png


Para Mega Drive, uso o picodrive:

images/retroarch/megadrivecore.png


Para quem curte Master System, o core é o Emux:

images/retroarch/mastersystemcore.png


Para os caras quem são *true old gamers*, tem o Stella para emular o Atari 2600:

images/retroarch/ataricore.png


## configurando

Você já tem o joystick, as ROMs e os cores (emuladores) e está seco para jogar!
Espere um pouquinho mais! Vamos só configurar os botões do joystick e mais
algumas coisinhas...

### Certifique-se de que o 'Save Configuration On Exit' está habilitado

Vá no ícone da engrenagem, e escolha `Configuration`.

images/retroarch/saveconfigonexit.png


Por padrão a opção
`Save Configuration On Exit` já está habilitada. Mas eu acho importante
mostrar o caminho até ela porque quando não está habilitada, as alterações
que você fizer não serão salvas.

images/retroarch/saveconfigonexit.png


### Desabilitar o "joystick virtual"

Como vamos jogar com nosso joystick bluetooth, não precisamos daquele
joystick de mentirinha sendo exibido na tela do touch e atrapalhando
nossa visualização do game!

No menu de configurações (ícone da engrenagem), vá em `Onscreen Overlay`.

images/retroarch/onscreenoverlay.png


Desabilite a opção `Display Overlay`

images/retroarch/displayoverlay.png


### Configuração dos botões

No menu de configurações vá em `Input`:

images/retroarch/input.png


Uma vez dentro do menu do `Input`, desça a lista que lá embaixo, quase no
final, vai ter a opção `Input User 1 Binds`.

images/retroarch/inputuser1binds.png


Dentro deste menu, **nao altere as 3 primeiras opções**. Como o escopo
desse texto é só o basicão, ignore essas opções.

A opção `User 1 Bind All`, percorre todos os botões pedindo para você atribuir
um botão equivalente do seu joystick. Mas para quem usando o RetroArch pela
primeira vez, talvez seja mais interessante fazer esta
configuração individualmente, botão por botão.

A identificação dos botões no RetroArch é inspirada na nomeclatura do
SNES: Y, B, X, A, L e R. Mas também possui outros botões, como
L2, R2, L3 e R3. Eis um esquema que pode ajudar:

![alt text][retropad]


### Configuração dos hotkeys

As hotkeys são combinações de botões que você pode acionar no seu joystick
para possibilitar que você controle o RetroArch sem necessidade de outro
dispositivo de entrada (teclado, touch screen, etc).
Ou seja, pelo joystick você poderá fazer coisas como resetar o jogo,
tirar um screenshot, sair do RetroArch, salvar o 
estado do jogo, carregar um estado salvo do jogo, ir para o menu do
RetroArch, etc...

No menu de configurações vá em `Input`:

images/retroarch/input.png


Uma vez dentro do menu do `Input`, desça a lista que lá embaixo, quase no
final, vai ter a opção `Input Hotkey Binds`.

images/retroarch/inputhotkeybinds.png


Aparecerão várias opções, mas vou explicar aqui somente as configurações
mais básicas.

Usarei o seguinte formato:

- `Função`: **botão**. Explicação da função.

Sendo que o **botão** você pode definir qualquer um que quiser, eu
apenas estou mostrando qual é a configuração mais consagrada entre
os usuários do RetroArch.

**Lembre-se que a identificação dos botões segue o esquema da imagem abaixo**
e o seu controle físico, que você tem em mãos, pode ter uma identificação diferente
para os botões.

![alt text][retropad]

Vamos à explicação 
- `Enable hotkeys`: **Select**. Esta opção é a mais importante, pois é o botão que você
tem que pressionar em combinação com algum outro para realizar determinada
ação.

<b>&larr;</b>

<b>&rarr;</b>

<b>&uarr;</b>

<b>&darr;</b>

- `Menu toggle`: **X**. Sai momentaneamente do jogo e volta para o Quickmenu do RetroArch
(falarei mais sobre esse QuickMenu daqui a pouco.)

- `Reset game`: **B**. Reinicia o jogo. Apesar de ser comum essa configuração
no botão B, eu acho ruim pois você pode apertar acidentalmente. Eu costumava
alterar isso para <b>&darr;</b> direcional para baixo.

Load state
Save state
Quit RetroArch
Savestate slot +
Savestate slot -
Reset game


images/retroarch/saveconfigonexit.png
images/retroarch/saveconfigonexit.png
images/retroarch/saveconfigonexit.png
images/retroarch/saveconfigonexit.png
images/retroarch/saveconfigonexit.png
images/retroarch/saveconfigonexit.png


input
input hotkeys
input bind

load content
quick menu
controls


retroachievements
habilitar display overlay
retroachievements account
desabilitar display overlay

{% assign imgra = "/images/retroarch/" %}

[retropad]:         {{ imgra }}Retropad_360pad.png "RetroPad"

[ataricore]:        {{ imgra }}ataricore.png

[coreupdater]:      {{ imgra }}coreupdater.png

[displayoverlay]:   {{ imgra }}displayoverlay.png

[inputhotkeys]:     {{ imgra }}inputhotkeys.png

[loadcontent]:      {{ imgra }}loadcontent.png

[loadrecent]:       {{ imgra }}loadrecent.png

[mastersystemcore]: {{ imgra }}mastersystemcore.png

[megadrive]:        {{ imgra }}megadrivecore.png

[nescore]:          {{ imgra }}nescore.png

[onlineupdater]:    {{ imgra }}onlineupdater.png

[quickmenu]:        {{ imgra }}quickmenu.png

[saveconfigonexit]: {{ imgra }}saveconfigonexit.png

[selectfile]:       {{ imgra }}selectfile.png

[snescore]:         {{ imgra }}snescore.png
