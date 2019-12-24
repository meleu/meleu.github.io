---
layout: post
title: checando se um elemento está presente em um array (bash)
date: 2019-12-23
tags:
- bash
---

Quando estamos trabalhando com arrays em shell scripts é comum ocorrer situações onde queremos saber se um determinado elemento está presente no array.

O bash não tem um recurso específico para isso, portanto temos que arrumar um outro jeito de conseguir esse resultado.

A maneira que logo vem a mente é percorrer todo o array através de um loop e checar se o elemento está presente lá. No código a seguir veremos a função `elementInArray1`:

```sh
#uso: elementInArray1 elemento arrayItem1 arrayItem2 arrayItemN
elementInArray1() {
    local element="$1"
    local array=("${@:2}")
    for temp in "${array[@]}"; do
        [[ "$temp" == "$element" ]] && return 0
    done
    return 1
}
```

Essa função considera que `$1` (o primeiro argumento) é o elemento que você quer checar se está no array, e que todos argumentos que vêm depois `${@:2}` (do segundo argumento em diante) são os elementos do array.

Através do loop `for` vamos testando os elementos um por um, comparando com o valor que queremos encontrar. Caso ele encontre, já vai retornar o sucesso (`return 0`) interrompendo a checagem.

Se chegar até o final do loop significa que não encontrou o valor que queremos, portanto retorna insucesso (`return 1`).

Vejamos essa função em ação:

```
$ cat elementInArray.sh 
elementInArray1() {
    local element="$1"
    local array=("${@:2}")
    for temp in "${array[@]}"; do
        [[ "$temp" == "$element" ]] && return 0
    done
    return 1
}

$ . elementInArray.sh 
$ procurar='melancia'
$ frutas=(pera uva maçã laranja kiwi)
$ elementInArray1 "$procurar" "${frutas[@]}" && echo 'sim :)' || echo 'não :('
não :(
$ procurar='uva'
$ elementInArray1 "$procurar" "${frutas[@]}" && echo 'sim :)' || echo 'não :('
sim :)
```

Legal, mas acho que conseguimos fazer um método um pouco mais eficiente. Onde podemos nos aproveitar do _globbing_ do bash e fazer essa checagem com apenas um teste.

Vamos começar a função `elementInArray2` assim:

```sh
# OBS: código incompleto
elementInArray2() {
    local element="$1"
    local array=("${@:2}")
    [[ "${array[@]}" == *"$element"* ]]
}
```

O teste que está ocorrendo ali, pega todos os elementos do array e o transforma em uma só string e compara com `$element` sendo que aqueles `*` asteriscos dizem que ele pode ter qualquer coisa antes e depois.

Vamos dar uma olhada se ele vai funcionar legal:

```
$ . elementInArray.sh 
$ procurar='melancia'
$ frutas=(pera uva maçã laranja kiwi)
$ elementInArray2 "$procurar" "${frutas[@]}" && echo 'sim :)' || echo 'não :('
não :(
$ procurar='uva'
$ elementInArray2 "$procurar" "${frutas[@]}" && echo 'sim :)' || echo 'não :('
sim :)
$ procurar='lar'
$ elementInArray2 "$procurar" "${frutas[@]}" && echo 'sim :)' || echo 'não :('
sim :)
$ # OPA! Ele encontrou 'lar' no array?!
```

A princípio a função funcionou de acordo com o esperado, no entanto no último exemplo gerou um falso positivo.

A função encontrou `lar` mesmo que o array não tenha elemento algum com este valor. Como você já deve ter percebido, isso ocorreu por conta do valor `laranja`.

Vejamos uma maneira de contornar isso:

```sh
elementInArray2() {
    local element="$1"
    local array=("${@:2}")
    [[ "${array[@]}" == *" $element "* ]]
}
```

A única diferença aqui é que o foi adicionado um espaço antes e depois de `$element`. Vamos aos testes:

```
$ . elementInArray.sh 
$ procurar='melancia'
$ frutas=(pera uva maçã laranja kiwi)
$ elementInArray2 "$procurar" "${frutas[@]}" && echo 'sim :)' || echo 'não :('
não :(
$ procurar='uva'
$ elementInArray2 "$procurar" "${frutas[@]}" && echo 'sim :)' || echo 'não :('
sim :)
$ procurar='lar'
$ elementInArray2 "$procurar" "${frutas[@]}" && echo 'sim :)' || echo 'não :('
não :(
$ frutas=(pera 'uva passa' maçã laranja kiwi)
$ # removi 'uva' substituindo por 'uva passa'
$ procurar='uva' # vamos ver se 'uva' ainda está no array
$ elementInArray2 "$procurar" "${frutas[@]}" && echo 'sim :)' || echo 'não :('
sim :)
$ # OPA! Isso não deveria ter ocorrido!
```

A função atendeu legal, porém mais uma vez gerando um falso positivo. Ela acusa que `uva` está presente no array mesmo quando não há elemento algum contendo **apenas** `uva`. Obviamente isso ocorreu devido ao elemento `uva passa`.

Poderíamos ir adicionando mais gambiarras para contornar este problema, mais sinceramente, eu não gosto muito de gambiarras. Principalmente se for tornar o código de difícil leitura.

Vou me dar por satisfeito com esta função assim mesmo e tomar o cuidado de usá-la somente com arrays cujos elementos não contenham espaços.

O máximo que eu faria é remover a atribuição das variáveis locais para deixar a função com apenas uma linha (prejudica um pouco a legibilidade, mas... pô! é só uma única linha!).

```sh
elementInArray2() {
    [[ "${@:2}" == *" $1 "* ]]
}
```

Vou terminar este post recomendando o seguinte:

1. Se quer um método infalível, use a versão com loop.
2. Se tem certeza que seu array não possui elementos contendo espaço, use a versão mais eficiente
3. A melhor recomendação: **use o que foi mostrado aqui como inspiração e crie sua própria solução!**


## Fontes

- [https://github.com/dylanaraps/pure-bash-bible](https://github.com/dylanaraps/pure-bash-bible)
- [https://mywiki.wooledge.org/glob](https://mywiki.wooledge.org/glob)
- [https://stackoverflow.com/a/15394738/6354514](https://stackoverflow.com/a/15394738/6354514)
