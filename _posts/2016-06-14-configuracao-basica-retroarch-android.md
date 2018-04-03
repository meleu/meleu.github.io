---
title: configuração básica do RetroArch no Android
date: 2016-06-14
tags:
- retroarch
- android
---

## Índice

- [Introdução](#intro)
- [Pré-requisitos](#pre-requisitos)
- [Instalação](#instalacao)
- [Interface com usuário](#interface-com-usuario)
- [Instalando os cores (emuladores)](#instalando-os-cores)
- [Configurando](#configurando)
  - [Desabilitar o joystick virtual](#desabilitar-o-joystick-virtual)
  - [Configuração dos botões](#configuracao-dos-botoes)
  - [Configuração dos hotkeys](#configuracao-dos-hotkeys)
- [Salvar configurações](#salvar-configuracoes)
- [Carregar um jogo](#carregar-um-jogo)
- [Quick Menu](#quick-menu)
- [Conclusão](#conclusao)

## intro

Esse texto tem como objetivo mostrar como instalar e configurar emuladores
de videogames antigos no Android (acredito que no iPhone o processo
de configuração é o mesmo).

Vamos usar o RetroArch, que é um software muito poderoso, cheio recursos,
totalmente livre e sem propaganda alguma(!). Ele age como se fosse uma
central de emuladores. Nele você terá em apenas um app os emuladores dos
clássicos Atari 2600, NES, Master System, Mega Drive, SNES e muitos outros
que estão disponíveis pra você escolher. Você não vai precisar
ficar procurando emuladores para cada videogame que você curte! Basta instalar
o RetroArch e a partir dele você terá disponível emuladores de diversos
sistemas.

Esse texto aborda o que considero o mínimo necessário para você jogar no
RetroArch. Mas o app é tão rico de recursos que o que vemos aqui é só a ponta do iceberg.
Dá pra fazer muito mais, e deixá-lo com visual bem bacana. Depois tentarei
escrever sobre outras configurações possíveis. Mas por enquanto vamos ficar
no básico do básico para você sair jogando.

Gostaria de deixar bem claro que os emuladores que eu utilizo vão no máximo
até SNES e MegaDrive. O RetroArch disponibiliza também emuladores de sistemas não
tão antigos, como de Dreamcast, Nintendo 64 e PlayStation 1, mas o desempenho
pode variar muito. Eu não testei nenhum destes.

Uma coisa que a princípio pode causar estranheza, é que a nota do RetroArch
no Google Play Store não é tão alta. Mas lendo os comentários nota-se
claramente que muita gente dá nota baixa por não saber fazer as configurações
iniciais antes de começar a jogar. Foi para tentar mudar este cenário que
escrevi este texto (eu mesmo sofri um pouco no começo).


## pre requisitos

Para tirar o máximo proveito do RetroArch no Android, são necessárias duas coisas:

- Joystick bluetooth
- ROMs dos jogos

Por padrão o RetroArch disponibiliza um joystick virtual, que fica na
tela e você comanda pelo touch screen. Mas eu não consigo ter prazer
algum jogando desta forma. Então nem vale a pena. Sem joystick eu nem jogo.

Existem inúmeros modelos de joysticks bluetooth no mercado. Eu não experimentei
vários, mas posso falar de dois modelos que uso e estou muito satisfeito:

- ípega GT-9023 ([aqui tem um vídeo review bacana](https://www.youtube.com/watch?v=QROvmQq-D-4))
- [8Bitdo ZERO](http://www.8bitdo.com/zero/) (um controlezinho minúsculo e discreto)

Não será abordado nesse texto como parear o joystick com o Android e nem
como obter as ROMs dos jogos. Então, supondo que você já tem um joystick
pareado com o seu Android e já tem ROMs no seu dispositivo, podemos começar.

Ah! É interessante que você habilite o recurso de rotação de tela automática no seu
Android.


## instalacao

Sem mistério: vai no Google Play Store e instala o
[RetroArch](https://play.google.com/store/apps/details?id=com.retroarch).

Atualmente (junho/2016) a versão disponível é a 1.3.4.


## interface com usuario

Isso é o que aparece quando você inicia o RetroArch pela primeira vez:

![alt text][mainmenu]

A primeira coisa a se estranhar no RetroArch é a sua interface com o usuário.
Atenção para duas grandes diferenças:

1. **No RetroArch você dá o primeiro toque numa opção para selecioná-la, e então
toca novamente para acionar a seleção.**
2. **O botão de voltar do Android não funciona no RetroArch!
Você tem que voltar por uma seta apontada para esquerda
que aparece no canto superior esquerdo**

Nos outros apps do Android, geralmente quando você toca em uma opção de um menu, você já está acionando
aquela opção. No RetroArch você dá o primeiro toque para selecionar, e então
toca novamente para acionar aquela seleção. Isso pode causar estranheza,
mas quando você configurar seu joystick direitinho, você vai acabar
controlando tudo pelo joystick. Inclusive o esquema de voltar/cancelar do Android.

**Observação**: Se você parear certinho seu joystick antes
de abrir o RetroArch, quando você abrí-lo é provável que ele já detecte
o seu joystick e aí você poderá navegar no menu através do direcional;
ativar/selecionar uma opção no botão equivalente ao A do SNES (ou bola
do PlayStation); voltar/cancelar no botão equivalente ao B do SNES (X no
PlayStation). Se estes botões não estiverem funcionando, calma que nós
já vamos configurá-los!

Não vou explicar aqui cada item dos menus do RetroArch. Por enquanto só
é importante que você observe que o ícone da casinha no canto inferior esquerdo
é o `Main Menu`; e o ícone da engrenagem no canto inferior direito acessa
o menu de configurações (`Settings tab`). O outro ícone que tem no meio nós
vamos ignorar.


## instalando os cores

Outra coisa a se acostumar ao usar o RetroArch é chamar os emuladores de
*cores*. Isso é outra coisa que confunde os não-iniciados.
Então acostume-se: Cada emulador é chamado de core dentro do RetroArch.

Para instalar um core nós vamos em `Online Updater`:

![alt text][onlineupdater]

 E em seguida vamos `Core Updater`:
 
![alt text][coreupdater]

Agora vem mais uma fonte de confusão: existem vários cores para um mesmo sistema e
você não sabe qual escolher! Só para SNES, existem 10 disponíveis!!

Bem, eu não sei as diferenças, vantagens/desvantagens de cada core.
Portanto vou apenas indicar os que eu percebo que são mais comuns
do pessoal instalar e que eu instalei e não tenho problema
algum.


Para **NES** (Nintendinho 8 bits) eu uso o FCEUmm:

![alt text][nescore]


Para **SNES** (Super Nintendo) eu uso o Snes9x Next (já usei o Snes9x e não tive problema
algum, mas depois li em algum lugar que o Next tem uma performance melhor):

![alt text][snescore]


Para **Mega Drive**, **Master System** e **Sega 32X**, usa-se o picodrive:

![alt text][megadrivecore]


Para os *true old gamers*, temos o Stella para emular o **Atari 2600**:

![alt text][ataricore]


## configurando

Você já tem o joystick, as ROMs e os cores (emuladores) e está seco para jogar!
Espere um pouquinho mais! Vamos só configurar os botões do joystick e mais
algumas coisinhas...

### Certifique-se de que o 'Save Configuration On Exit' está habilitado

Vá em `Settings` (ícone da engrenagem), e escolha `Configuration`.

![alt text][configuration]

Por padrão a opção
`Save Configuration On Exit` já está habilitada. Mas eu acho importante
mostrar o caminho até ela porque quando não está habilitada, as alterações
que você fizer não serão salvas.

![alt text][saveconfigonexit]


### Desabilitar o "joystick virtual"

Como vamos jogar com nosso joystick bluetooth, não precisamos daquele
joystick de mentirinha sendo exibido na tela do touch e atrapalhando
nossa visualização do game!

Em `Settings` (ícone da engrenagem), vá em `Onscreen Overlay`.

![alt text][onscreenoverlay]


Desabilite a opção `Display Overlay`

![alt text][displayoverlay]


### Configuracao dos botoes

No menu de configurações vá em `Input`:

![alt text][input]


Uma vez dentro do menu do `Input`, desça a lista que lá embaixo, quase no
final, vai ter a opção `Input User 1 Binds`.

![alt text][inputuser1binds]


Dentro deste menu, **nao altere as 3 primeiras opções**. Como o escopo
desse texto é só o basicão, ignore essas opções.

![alt text][inputuser1bindall]

A opção `User 1 Bind All`, percorre todos os botões pedindo para você atribuir
um botão equivalente do seu joystick. Mas para quem está usando o RetroArch pela
primeira vez, talvez seja mais interessante fazer esta
configuração individualmente, botão por botão.

A identificação dos botões no RetroArch é inspirada na nomeclatura do
SNES: Y, B, X, A, L e R. Mas também possui outros botões, como
L2, R2, L3 e R3. Eis um esquema que pode ajudar:

![alt text][retropad]

Esse RGUI ali no meio do controle você pode ignorar.

Ainda dentro do `Input User 1 Binds`, você vai observar que existem os botões L3 e R3:

![alt text][inputl3r3]

Estes botões são os direcionais analógicos pressionados. Ou seja L3 é o
analógico esquerdo pressionado, e o R3 é o analógico direito
pressionado. Se o seu joystick não possuir estes botões, simplesmente ignore
(o meu 8Bitdo Zero, por exemplo, não tem direcional analógico, nem L2 e R2).

**ATENÇÃO! Se você quer fazer uma configuração de botões diferente por conta
de um determinado jogo ou console, não faça essa configuração aqui no `Input`!
Utilize o `Quick Menu`, opção `Controls`, como veremos daqui a pouco.**

### configuracao dos hotkeys

As hotkeys são combinações de botões que você pode acionar no seu joystick
para controlar o RetroArch sem necessidade de outro
dispositivo de entrada (teclado, touch screen, etc).
Ou seja, pelo joystick você poderá fazer coisas como resetar o jogo,
tirar um screenshot, sair do RetroArch, salvar o 
estado do jogo, carregar um estado salvo do jogo, ir para o menu do
RetroArch, etc...

No menu de configurações vá em `Input`:

![alt text][input]


Vai abrir um menu com várias opções, desça a lista que lá embaixo, quase no
final, vai ter a opção `Input Hotkey Binds`.

![alt text][inputuser1binds]


Aparecerão várias opções, mas vou explicar aqui somente as configurações
mais básicas. Usarei o seguinte formato:

- `Função`: **botão**. Explicação da função.

Sendo que o **botão** você pode definir qualquer um que quiser, eu
estou mostrando aqui apenas uma sugestão de configuração que é 
mais consagrada entre os usuários do RetroArch.

**Lembre-se que a identificação dos botões segue o esquema da imagem abaixo**
e o seu controle físico, que você tem em mãos, pode ter uma identificação diferente
para os botões.

![alt text][retropad]

Vamos à explicação

- `Enable hotkeys`: **Select**. Esta opção é a mais importante, pois é o botão
que você tem que pressionar em combinação com algum outro para realizar 
determinada ação. Portanto, nas funções que explico abaixo, você tem que pressionar
**Select+[botão]**.

- `Menu toggle`: **X**. Dá uma pausa no jogo e vai para o Quick Menu
do RetroArch (falarei mais sobre esse Quick Menu daqui a pouco.)

- `Reset game`: **B**. Reinicia o jogo. Apesar de ser comum essa configuração
no botão B, eu acho ruim pois você pode apertar acidentalmente e reiniciar o
jogo. Se isso acontecer quando você estiver bem avançado no Battletoads (NES),
por exemplo,
te garanto que não será nada agradável! Portanto é melhor deixar o Reset
sem botão algum. E dá pra reiniciar pelo Quick Menu, como veremos daqui a pouco.
É mais seguro.

- `Quit RetroArch`: **Start**. Sai totalmente do RetroArch. Se você acha
que pode acionar Select+Start acidentalmente (ex.: 8Bitdo Zero), é melhor deixar essa opção
sem botão algum também.

- `Save state`: **R**. Salva o estado do jogo.

- `Load state`: **L**. Carrega o estado do jogo que foi salvo.


## salvar configuracoes

Agora vamos salvar todas estas configurações que fizemos. Vá em `Main Menu`
(ícone da casinha) e escolha `Save Current Config`:

![alt text][savecurrentconfig]


## carregar um jogo

Finalmente vamos jogar! Vá no `Main Menu` (ícone da casinha) e escolha
`Load Content`

![alt text][loadcontent]

Em seguida escolha `Select File And Detect Core`, vá navegando até
o diretório onde você salvou as ROMs e escolha algum jogo.
O RetroArch automaticamente vai detectar qual core utilizar para a ROM que você
escolher, se ele ficar na dúvida, irá te perguntar qual core você quer utilizar.

Uma forma mais rápida de carregar um jogo é indo no `Main Menu`, opção `Load Recent`.
Ali você verá os últimos games que você jogou.

Pronto! Você está no game! Mas espere um pouco antes de se entregar ao vício!
Vamos rapidinho dar uma olhada no `Quick Menu`.


## Quick Menu

Uma vez que você está no jogo, é possível retornar aos menus do RetroArch
usando a combinação de botões **Select+X** (considerando que você configurou
os hotkeys da maneira que eu sugeri).

![alt text][quickmenu]

Se você se deparar com essa tela escrito "Search:" aperte o **B** para tirar
esse Search da tela.

![alt text][quickmenu-search]

Agora vamos à uma explicação rápida das opções mais importantes do Quick Menu:

- **Resume**: volta para o jogo.
- **Restart**: reinicia o jogo.
- **Close**: fecha o jogo.
- **Save State**: salva o estado do jogo (que você pode fazer direto no
jogo com Select+R).
- **Load State**: carrega o estado que tiver salvo do jogo (você pode fazer
direto no jogo com Select+L).
- **Controls**: Muito útil para quando você quer uma configuração de botões
diferente para um jogo ou um core específico. Faça as configurações ao seu
gosto e depois vá em `Save Core Remap File` para salvar a configuração para
o core que está ativo, ou vá em `Save Game Remap File` para salvar a
configuração específica para o jogo que está ativo.

Lembre-se: para voltar para o jogo vá em **Resume**.

Se você apertar o B enquanto estiver no Quick Menu, você retornará para o 
`Main Menu`. Só que agora observe que a primeira opção do Main Menu é o `Quick Menu`:

![alt text][main-quickmenu]

Isso só acontece quando você tem algum core ativo (quando você está jogando
algum game).


## conclusao

Agora você já pode jogar os saudosos jogos antigos! Aproveite e dê a nota
máxima para o RetroArch lá no Google Play Store. Afinal de contas é um programa
poderoso, cheio de recursos, totalmente livre e sem aquelas propagandinhas chatas
que a gente costuma ver nos apps que se dizem Free.

Posteriormente pretendo falar sobre os
[RetroAchievements](http://retroachievements.org) e como habilitar esse recurso
no RetroArch. Você verá que a diversão com os jogos antigos será multiplicada.

Qualquer dúvida, coloca aí nos comentários que a gente tenta resolver.

{% assign imgra = "/images/retroarch/" %}

[retropad]:          {{ imgra }}Retropad_360pad.png "RetroPad"
[ataricore]:         {{ imgra }}ataricore.png
[configuration]:     {{ imgra }}configuration.png
[coreupdater]:       {{ imgra }}coreupdater.png
[displayoverlay]:    {{ imgra }}displayoverlay.png
[input]:             {{ imgra }}input.png
[inputuser1binds]:   {{ imgra }}inputuser1binds.png
[inputuser1bindall]: {{ imgra }}inputuser1bindall.png
[inputhotkeys]:      {{ imgra }}inputhotkeys.png
[inputl3r3]:         {{ imgra }}inputl3r3.png
[loadcontent]:       {{ imgra }}loadcontent.png
[loadrecent]:        {{ imgra }}loadrecent.png
[mainmenu]:          {{ imgra }}mainmenu.png
[main-quickmenu]:    {{ imgra }}main-quickmenu.png
[megadrivecore]:     {{ imgra }}megadrivecore.png
[nescore]:           {{ imgra }}nescore.png
[onlineupdater]:     {{ imgra }}onlineupdater.png
[onscreenoverlay]:   {{ imgra }}onscreenoverlay.png
[quickmenu]:         {{ imgra }}quickmenu.png
[quickmenu-search]:  {{ imgra }}quickmenu-search.png
[saveconfigonexit]:  {{ imgra }}saveconfigonexit.png
[savecurrentconfig]: {{ imgra }}savecurrentconfig.png
[selectfile]:        {{ imgra }}selectfile.png
[snescore]:          {{ imgra }}snescore.png
