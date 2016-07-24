---
layout: post
title: passando opcoes da linha de comando para o shell script
date: 2016-07-24
tags:
- shell
- linux
---

Esse post é só pra deixar um template do esquema que costumo usar para passar
parâmetros da linha de comando para um shell script. No final das contas achei
esse esquema mais intuitivo e versátil do que o `getopts`.

Aprendi esse método no [livro de Shell Script](http://novatec.com.br/livros/shellscript/) do [Aurélio](https://aurelio.net). Eu tenho o liro e recomendo fortemente.

Uma coisa bacana é que o capítulo de amostra disponibilizado pela editora é justamente o que trata do esquema mostrado aqui. Confira:
[https://novatec.com.br/livros/shellscript/capitulo9788575221525.pdf](https://novatec.com.br/livros/shellscript/capitulo9788575221525.pdf)


```sh
while [[ "$1" ]]; do
    case "$1" in

    -h|--help)
        echo "$help_message"
        exit 0
    ;;

    #--outras-opcoes|-o)
    #   outras opções entram aqui
    #;;

    *)  echo "*** opção inválida: \"$1\"" >&2
        exit 1
    ;;
    esac

    # indo para a próxima opção
    shift
done
```

