---
layout: post
title: validando datas em shell scripts
date: 2016-06-09
tags:
- shell
- linux
---
Estava querendo uma forma de validar datas no meu shell script. Ou seja, verificar se o usuário entrou com uma data válida. De repente veio o *insight*: "Hey! O comando `date` pode fazer isso!".

Pois é! Nada de reinventar a roda. Vamos usar o que já temos na mão. Imaginemos que temos uma variável `DATE` e queremos que ela receba uma data válida vinda do primeiro argumento da linha de comando, se a data não for válida, sai do programa. O formato que queremos para `DATE` é dd-mm-aaaa. Eis um scriptzinho de exemplo:

```bash
#!/bin/bash
# datavalida.sh
DATE=$(date -d "$1" +%d-%m-%Y 2>/dev/null) || {
    echo "*** Erro: \"$1\" é uma data inválida!"
    exit 1
}

echo "DATE = $DATE"
```

Só tem um contra-tempo: a data a ser passada como parâmetro precisa estar no formato "americano". Ou seja, 01/03/2009 é três de janeiro de 2009, e não primeiro de março... Mas isso é mole de resolver usando uns `cut` aqui e acolá. Eu preferi deixar assim mesmo para poder usar algumas facilidades do `date`, como "yesterday" e "-4 days" por exemplo.

Agora vejamos alguns exemplos do uso do script acima:

```
[prompt]$ # se não passar parâmetro algum, mostra a data de hoje
[prompt]$ ./datavalida.sh
DATE = 09-06-2016
[prompt]$ ./datavalida.sh 3/1/2007
DATE = 01-03-2007
[prompt]$ ./datavalida.sh 99-99-99
*** Erro: "99-99-99" é uma data inválida!
[prompt]$ ./datavalida.sh yesterday
DATE = 08-06-2016
[prompt]$ ./datavalida.sh '-5 days'
DATE = 04-06-2016
[prompt]$ ./datavalida.sh '+9 days'
DATE = 18-06-2016
[prompt]$ ./datavalida.sh tomorrow
DATE = 10-06-2016
[prompt]$ ./datavalida.sh 2011-09-11
DATE = 11-09-2011
```



![alt text][retropad]

{% assign imgra = {{ site.baseurl }} + "images/retroarch/" %}

[retropad]: {{ imgra }}Retropad_360pad.png "RetroPad"
