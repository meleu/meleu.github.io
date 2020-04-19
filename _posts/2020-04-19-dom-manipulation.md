---
layout: post
title: básico de DOM manipulation
date: 2020-04-19
author: meleu
tags:
- frontend
---

Apenas algumas anotações do que venho aprendendo. O mais básico do básico de DOM manipulation.

**TODO: colocar mais exemplos**

## Elementos

```js
// métodos de document

getElementsByTagName()
getElementsByClassName()
getElementById()

querySelector()
querySelectorAll()
```
**DICA**: É preferível usar `querySelector/querySelectorAll`, pois a sintaxe é similar aos seletores CSS.

### Exemplos:

```
document.getElementsByTagName('li');
// vai retornar um HTMLCollection com todos os elementos 'li' que existirem

document.getElementsByTagName('li')[0];
// acessando o primeiro elemento individualmente

document.getElementById('idName');
// retorna o elemento com o 'id="idName"'
// OBS.:  os ids são/deveriam ser únicos. Se houver duplicação
//        apenas a primeira ocorrência é retornada.

// ----------
// ATENÇÃO! o uso de querySelector/querySelectorAll é bem mais cômodo!
// Pois funciona como um seletor CSS
// ----------

document.querySelector('ul.customList > li');
// retorna a primeira ocorrência de 'li' presente
// no 'ul' cuja classe é 'customList'

document.querySelectorAll('ul > li');
// retorna um NodeList (similar a um Array) com
// todos os 'li's filhos de 'ul's

```

## Atributos

Uma vez que obtemos um elemento, podemos manipular seus atributos:

```js
// métodos de um element
getAttribute()
setAttribute()
```

Se podemos manipular os atributos de um elemento, então podemos alterar o atributo `class` e assim manipular a estilização do elemento. **No entanto**, para manipular a estilização é melhor usar as técnicas mostradas no próximo tópico.


## Estilização

Uma vez que temos um elemento já devidamente selecionado, podemos manipular sua estilização usando as seguintes propriedades:
```
// manipulando a propriedade CSS diretamente
style.{propertyName}  // propertyName é uma versão camelCase de uma propriedade CSS

// manipulando estilo através de classes é mais elegante...
className   // string com as classes separadas por espaço
classList   // "Array" onde cada item é uma classe
            // (na verdade classList é um DOMTokenList, e não um Array)

// manipular estilização através dos métodos de classList é bem mais cômodo
classList.add()
classList.remove()
classList.toggle()
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA5MzU5NTc3N119
-->