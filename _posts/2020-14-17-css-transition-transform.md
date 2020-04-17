---
layout: post
title: Estudando CSS transition e transform
date: 2020-04-17
tags:
- frontend
---

## Introdução

Isso é um resumo do que eu aprendi lendo esse artigo: [https://thoughtbot.com/blog/transitions-and-transforms#transition-timing-optional](https://thoughtbot.com/blog/transitions-and-transforms#transition-timing-optional)

- `transform`: move ou muda a aparência de um elemento.
- `transition`: faz o elemento mudar suave e gradualmente.

Estas duas propriedades são combinadas fazem com que o `transition` torne as mudanças causadas pelo transform ocorrerem de forma suave e agradável (caso contrário a mudança seria abrupta).

Aqui está um exemplo ridiculamente simples de HTML/CSS para ir brincando com as possibilidades:
```html
<!DOCTYPE html>
<html lang="en">

<head>
  <style>
    .container {
      display: flex;
      justify-content: center;
    }

    .box {
      width: 50px;
      height: 50px;
      background-color: red;
      transition: all 1s;
    }

    .box:hover {
      transform: scale(2);
    }
  </style>
  <title>Document</title>
</head>

<body>
  <h1>praticando transition e transform</h1>

  <div class="container">
    <div class="box"></div>
  </div>
</body>

</html>
```

## `transition`

Duas propriedades são necessárias para o `transition` fazer efeito:

1. `transition-property`
2. `transition-duration`

Existem outras, mas essas são obrigatórias. A propósito, o mais usual é usar a versão resumida de definir todas essas propriedades:

```
selector {
  transition: [property] [duration] [timing-function] [delay];
}
```

### `transition-property` (obrigatória)

Especifica em que propriedade CSS a `transition` será aplicada.

É comum usar simplesmente `all`, mas também pode ser específico (ex.: `background-color`).

Exemplo:
```
div {
  transition-property: background-color;
}
```

### `transition-duration` (obrigatória)

Especifica o intervalo de tempo da transição.

Pode ser em `s` (segundos) ou `ms` (milisegundos).

Exemplo:
```
div {
  transition-duration: 300ms;
}
```

No entanto o mais usual é usar simplesmente `transition` e declarar os valores de `-property` e `-duration` numa única linha:
```
div {
  transition: all 2s;
}
```

### `transition-timing-function` (opcional)

Permite que você defina o comportamento da velocidade da transição durante a sua duração.

O padrão é `ease`. O comportamento de cada um é descrito a seguir:

- `ease`: acelera rapidamente e vai desacelerando no final.
- `linear`: velocidade constante.
- `ease-in`: acelera progressivamente até parar abruptamene no fim.
- `ease-out`: começa de maneira abrupta e desacelera no fim.
- `ease-in-out`: começa acelerando e termina desacelerando (semelhante ao `ease`, porém a aceleração inicial é um pouco mais suave).
- `cubic-bezier()`: uma forma avançada de `-timing-function`. Documentada em detalhes [aqui](https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function).


TODO: continuar seguindo o "tutorial" aqui: https://thoughtbot.com/blog/transitions-and-transforms#transition-timing-optional


### `transition-delay` (opcional)



