---
layout: post
title: macetinhos de sed
date: 2016-07-22
tags:
- shell
- linux
- sed
---

Na verdade esse post é apenas um lembrete para mim mesmo de alguns truquezinhos
de sed que serão muito úteis para as coisas que eu ando me metendo...

**sed imitando o grep**
```sed
# print only lines which match regular expression (emulates "grep")
sed -n '/regexp/p'           # method 1
sed '/regexp/!d'             # method 2
```

Gostei mais do método 2. Então vou usá-lo daqui pra frente.


**imprimir conteúdo de um arquivo da linha 1 até REGEXP**
```sed
sed '1,/regexp/!d'
```

**imprimir conteúdo de um arquivo de REGEXP1 até REGEXP2**
```sed
sed '/regexp1/,/regexp2/!d'
```


Fontes: http://sed.sourceforge.net/sed1line.txt e livro de Shell Script do meu guru [Aurelio](http://aurelio.net).
