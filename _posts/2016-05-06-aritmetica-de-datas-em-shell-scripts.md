---
layout: post
title: Aritmética de datas em shell scripts
date: '2016-05-06T01:29:00.002-03:00'
author: meleu
tags:
- bash
- shell
modified_time: '2016-05-06T01:30:38.902-03:00'
blogger_id: tag:blogger.com,1999:blog-1613465446497619833.post-7295886484911605626
blogger_orig_url: http://mdicas.blogspot.com/2016/05/aritmetica-de-datas-em-shell-scripts.html
---

Estava eu felizinho e tranquilo fazendo um scriptzinho aqui para me ajudar em algumas
coisas do trabalho, quando esbarrei no problema da aritmética de datas.

O caso é o seguinte: tenho um arquivo (planilha excel) onde todos os dias preencho várias
informações, e às 17h eu tenho que fechar este arquivo e abrir um novo que se encerrará às
17h do dia seguinte. O meu objetivo era fazer um script onde eu pudesse passar uma data na
linha de comando e ele já abrisse diretamente o arquivo referente a esta data. Útil para
consultar os arquivos de dias anteriores.

O problema que encontrei foi que o nome dos arquivos contem a data de fechamento daquele arquivo
e a data anterior, exemplo: "Dados 01-05-2016 a 02-05-2016.xls". Isso é um problema pois não é
uma matemática tão simples fazer o script saber qual é o dia anterior de uma determinada data.
Alguns meses tem 28, 29, 30 ou 31 dias...<br /><br />Numa rápida googlada achei uma solução
simples, bonita e elegante:

```bash
date -d "2016-05-01 - 1 day"
```

Para obter a data no formato desejado basta usar o caractere de formatação '%', de acordo com o
que é mostrado na manpage. No meu caso fica assim:

```bash
date -d "2016-05-01 - 1 day" +%d-%m-%Y
```

(OBS.: pelo que andei lendo esse recurso de aritmética de datas é uma feature do GNU date. Portanto
funcionará em qualquer distro Linux moderna, porém não funciona no date do BSD, que é o utilizado nos SOs da Apple.)
