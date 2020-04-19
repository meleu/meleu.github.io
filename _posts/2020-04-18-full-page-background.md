---
layout: post
title: Imagem de fundo perfeitamente ajustada
date: 2020-04-18
author: meleu
tags:
- frontend
---

Truque aprendido em [https://css-tricks.com/perfect-full-page-background-image/](https://css-tricks.com/perfect-full-page-background-image/)

O objetivo é usar uma imagem com plano de fundo de uma página web, cobrindo toda a janela.

Premissas:
- preencher toda a página com a imagem, sem espaços em branco;
- redimensionar a imagem se necessário;
- manter a proporção da imagem (_aspect ratio_);
- imagem centralizada na página;
- imagem não provoca o aparecimento de barras de rolagem;
- funciona ~~em qualquer~~ na esmagadora maioria dos navegadores.

Eis o código CSS:
```css
html {
  background: url("background.jpg") no-repeat center center fixed;
  background-size: cover;
}
```

As simple as that!

<!--stackedit_data:
eyJoaXN0b3J5IjpbMjgwOTAxMDE4XX0=
-->