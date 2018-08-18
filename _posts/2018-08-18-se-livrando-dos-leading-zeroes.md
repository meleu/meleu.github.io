---
layout: post
title: se livrando dos leading zeroes [bash]
date: 2018-08-18
tags:
- bash
---

**TL;DR**: aprendi [aqui](https://stackoverflow.com/a/11130324/6354514) uma maneira bacana
de fazer variáveis automaticamente descartarem os "leading zeroes" no bash:
```bash
var=000666
echo $(( 10#$var ))
# saída experada: 666
```

---

Num dos meus scripts eu precisava saber se a hora atual é menor que dezoito horas. Tipo isso:

```bash
hour=$(date +%H)
if [[ $hour -gt 18 ]]; then
    echo "do something..."
fi
```

Ao executar eu me deparei com o seguinte erro:

```
-bash: [[: 08: valor muito grande para esta base de numeração (token de erro é "08")
```

Dei umas googlada e achei a solução: `$(( ))`. Portanto meu (trecho de) código ficou assim:

```bash
hour=$(date +%H)
hour=$(( 10#$hour ))  # também poderia ser "$(( 10#$(date +%H) ))"
if [[ $hour -gt 18 ]]; then
    echo "do something..."
fi
```
