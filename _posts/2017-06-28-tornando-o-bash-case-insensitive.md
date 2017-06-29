---
layout: post
title: tornando o bash case insensitive
date: 2017-06-28
tags:
- shell
- linux
---


Eu estava precisando fazer um script checar o conteúdo de um arquivo e tomar certas ações se o conteúdo fosse `CD`. Para fazer o bash considerar `CD`, `Cd` e `cd` a mesma coisa, eu setei o `nocasematch`.

```sh
shopt -s nocasematch
```

Executando o comando abaixo podemos observar que funciona como esperado
```sh
[[ CD == cd ]] && echo OK
```

O problema é que alguns dos arquivos estava escrito `CD` e outros estava escrito `Compact Disc`. E então eu gostaria que o script considerasse `CD`, `cd`, `Compact Disc`, `Compact disc` e `compact disc` a mesma coisa. Nesse caso uma expressão regular seria mais útil, e para deixá-la case-insensitive eu setei o `nocaseglob`:

```sh
shopt -s nocaseglob
```

Testes para ver que funciona:
```sh
[[ CD =~ ^(cd|compact disc)$ ]] && echo OK

[[ "Compact Disc" =~ ^(cd|compact disc)$ ]] && echo OK

[[ "CoMpAcT dIsC" =~ ^(cd|compact disc)$ ]] && echo OK
```

Aprendi isso enquanto estive escrevendo este script: https://github.com/meleu/used2betxt/blob/master/Used2BeTXT.sh
