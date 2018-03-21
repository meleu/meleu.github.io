---
layout: post
title: git bisect: encontrando o commit malvado
date: 2018-03-21
tags:
- git
---

## 1. Clonar o repositório

Se usar `--depth` certifique-se de estar pegando um commit que vc tem certeza que está bom.

```
git clone --depth {X} https://github.com/blabla/bleble
```

## 2. `git bisect start`

## 3. `git bisect good {HashDeUmCommitBom}`

## 4. Testa a versão atual

Faça o teste da versão mais recente. Provavelmente ela estará bugada, do contrário você não estaria fazendo isso, né?

## 5. `git bisect good|bad`

## 6. repetir os passos 4 e 5 até chegar no commit bugado
