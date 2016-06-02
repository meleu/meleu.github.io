---
layout: post
title: fazer o find parar depois do primeiro match
date: '2016-05-06T23:50:00.001-03:00'
author: Meleu Zord
tags:
- Linux
- bash
- shell
modified_time: '2016-05-06T23:50:14.834-03:00'
blogger_id: tag:blogger.com,1999:blog-1613465446497619833.post-2013905847124991129
blogger_orig_url: http://mdicas.blogspot.com/2016/05/fazer-o-find-parar-depois-do-primeiro.html
---
Estava fazendo um script para abrir um determinado arquivo baseado no que era encontrado através de um find. O problema é que as vezes o find encontrava mais de um arquivo que atendia o critério de busca, e eu gostaria de parar no primeiro arquivo encontrado. Uma rápida googlada e a solução apareceu...

Fazer o comando find parar após o primeiro arquivo encontrado:

```
find caminho/do/diretorio -name nome-do-arquivo -print -quit
```

Simples assim! 
