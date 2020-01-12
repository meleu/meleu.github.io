---
layout: post
title: equivalente JavaScript para o array_count_values() do PHP
date: 2019-12-12
tags:
- JavaScript
---

Uma função que eu achei útil no PHP é a `array_count_values()`. Ela conta quantas vezes um determinado valor se repete em
um array e retorna um array associativo (também conhecido como mapa, ou dicionário, dependendo da linguagem), onde a chave
é o elemento do array original, e o valor é quantas vezes o elemento se repete no array original.

Estava precisando desse recurso no JavaScript e observei que não existe uma função "de fábrica" com este mesmo recurso.

Eis como resolvi:

```js
function arrayCountValues(sourceArray) {
    const counter = {};
    let key;
    for (let i = 0; i < sourceArray.length; i++) {
        key = sourceArray[i];
        counter[key] = (counter[key] ? counter[key] + 1 : 1);
    }
    return counter;
}
```
