Estava querendo uma forma de validar datas no meu shell script. Ou seja, verificar se o usu�rio entrou com uma data v�lida. De repente veio o *insight*: "Hey! O comando `date` pode fazer isso!".

Pois �! Nada de reinventar a roda. Vamos usar o que j� temos na m�o. Imaginemos que temos uma vari�vel `DATE` e queremos que ela receba uma data v�lida vinda do primeiro argumento da linha de comando, se a data n�o for v�lida, sai do programa. O formato que queremos para `DATE` � dd-mm-aaaa. Eis um scriptzinho de exemplo:

```bash
#!/bin/bash
# datavalida.sh
DATE=$(date -d "$1" +%d-%m-%Y 2>/dev/null) || {
    echo "*** Erro: \"$1\" � uma data inv�lida!"
    exit 1
}

echo "DATE = $DATE"
```

S� tem um contra-tempo: a data a ser passada como par�metro precisa estar no formato "americano". Ou seja, 01/03/2009 � tr�s de janeiro de 2009, e n�o primeiro de mar�o... Mas isso � mole de resolver usando uns `cut` aqui e acol�. Eu preferi deixar assim mesmo para poder usar algumas facilidades do `date`, como "yesterday" e "-4 days" por exemplo.

Agora vejamos alguns exemplos do uso do script acima:

```shell
[prompt]$ # se n�o passar par�metro algum, mostra a data de hoje
[prompt]$ ./datavalida.sh
DATE = 09-06-2016
[prompt]$ ./datavalida.sh 3/1/2007
DATE = 01-03-2007
[prompt]$ ./datavalida.sh 99-99-99
*** Erro: "99-99-99" � uma data inv�lida!
[prompt]$ ./datavalida.sh yesterday
DATE = 08-06-2016
[prompt]$ ./datavalida.sh '-5 days'
DATE = 04-06-2016
[prompt]$ ./datavalida.sh '+9 days'
DATE = 18-06-2016
[prompt]$ ./datavalida.sh tomorrow
DATE = 10-06-2016
[prompt]$ ./datavalida.sh 2011-09-11
DATE = 11-09-2011
```