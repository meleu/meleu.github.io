---
layout: post
title: comparando datas em shell scripts
date: 2016-08-05
tags:
- shell
- linux
---
Mas uma diquinha bacana para quem precisa manipular datas no shell script...

Primeiramente vamos lembrar do macetinho de validação de datas publicado em [outro post aqui no blog](http://meleu.github.io/blog/2016/06/09/validando-datas-em-shell-scripts).

Cosiderando que temos duas variáveis com datas já validadas `date1` e `date2`. Podemos usar o formato `+%s` do comando `date`, que ele nos retorna um número inteiro correspondente ao número de segundos passados desde primeiro de janeiro de 1970.

O trecho do script ficaria mais ou menos assim:

```sh
# considere que nesse ponto date1 e date2 já possuem datas validas
date1=$(date -d $date1 +%s)
date2=$(date -d $date2 +%s)
# agora date1 e date2 possuem o número de segundos passados desde 1 de janeiro de 1970

if [ $date1 -ge $date2 ]; then
    echo "date1 é mais recente que (ou igual) date2"
else
    echo "date2 é mais recente que date1"
fi  
```
