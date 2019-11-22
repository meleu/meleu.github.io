---
layout: post
title: clonando um sistema com rsync
date: 2019-11-22
tags:
- linux
---

Tava precisando migrar um sistema da Amazon para a Digital Ocean, e para clonar o sistema todo, usei `rsync`.

Conectei na máquina a ser migrada/clonada e mandei o seguinte comando:

```sh
sudo rsync --numeric-ids -aHAXSve ssh \
    --exclude={"/dev/*","/proc/*","/sys/*","/tmp/*","/run/*","/mnt/*","/media/*","/lost+found"} \
    / root@NewServer:/destination/directory
```

*Atenção*: lembrar de ajustar `@NewServer:/destination/directory` para os valores adequados.

É fundamental utilizar a opção `--numeric-ids` e `-A`, caso contrário todos os arquivos copiados terão suas permissões alteradas para que sejam de propriedade do usuário que está recebendo esses arquivos no host "NewServer".

A man page do `rsync` explica a função de cada uma das opções que utilizamos aqui, vou colocar aqui o trecho com um resumo:

```
     --numeric-ids           don't map uid/gid values by user/group name
 -a, --archive               archive mode; equals -rlptgoD (no -H,-A,-X)
 -H, --hard-links            preserve hard links
 -A, --acls                  preserve ACLs (implies -p)
 -X, --xattrs                preserve extended attributes
 -S, --sparse                handle sparse files efficiently
 -v, --verbose               increase verbosity
 -e, --rsh=COMMAND           specify the remote shell to use
     --exclude=PATTERN       exclude files matching PATTERN
```

**Observação**: é de suma importância que o acesso ao host que vai receber os arquivos seja `root` pois queremos manter as permissões e as informações de proprietário e grupo dos arquivos. E se usarmos um usuário regular para receber os arquivos, ele não terá permissão de alterar as permissões e consequentemente todos os arquivos pertencerão a ele (o que inviabiliza o que estamos querendo fazer aqui).

A execução deste comando vai demorar muitos minutos. Recomenda-se um bom café...
