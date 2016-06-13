---
layout: post
title: maneira Deitel de checar data
date: '2008-10-08T02:14:00.002-03:00'
author: meleu
tags:
- C
- java
- programacao
modified_time: '2008-10-28T15:52:06.969-02:00'
blogger_id: tag:blogger.com,1999:blog-1613465446497619833.post-4320618570628642281
blogger_orig_url: http://mdicas.blogspot.com/2008/10/maneira-deitel-de-checar-data.html
---

Essa é mais uma dica da série "como é que eu não tinha pensado nisso antes?".
Trata-se de uma maneira super-simples de checar a validade de uma data. Vi isso
no livro "Java: Como Programar", sexta edição,  do Deitel. Aí vai...

- ano: pode ser qualquer inteiro não negativo.
- mês: inteiro dentro do intervalo [1,12].
- dia: depende do mês, e se for fevereiro, depende de ser ano bissexto.

Aí vai o algoritmo em C **já levando em consideração que o mês e ano são válidos**.

```c
int checarDia(int dia, int mes, int ano) {
   /* aqui está a simplicidade do algoritmo:
   * cada elemento deste array é o maior dia do mês cujo número
   * é o índice do elemento, exceto o elemento 0
   */
   int diaPorMes[] = { 0, 31, 28, 31, 30, 31, 30
   31, 31, 30, 31, 30, 31, 30 };

   /* veja que coisa mágica! */
   if(dia > 0 && dia <= diaPorMes[mes])
     return dia;

   /* cuidando do danadinho do ano bissexto */
   if(mes == 2 && dia == 29 && (ano % 400 == 0 || (ano % 4 == 0 && ano % 100 != 0)))
     return dia;

   /* se não for uma data válida, retornamos o dia primeiro */
     return 1;
}
```

Me lembro de um dia fazer um exercício de programação que pedia para
validar se a data que o usuário entrou era válida, fiz o código usando
switch-case e alguns ifs...

Ver essa solução usando um simples array chega a dar raiva! Raiva por
não ter pensado nisso de primeira.
