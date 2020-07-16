---
layout: post
title: Apache Virtual Hosting
date: 2020-07-16
author: meleu
tags:
- servidor
---
**NOTA**: isso é mais uma nota pessoal do que um artigo. Apenas use se souber o que está fazendo.

Passos para abilitar um virtual host num servidor rodando apache:
```shell
sudo mkdir /var/www/your_domain
sudo chown $USER:$USER /var/www/your_domain
# criar /var/www/your_domain/index.html
```
Criar o arquivo `/etc/apach
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAxNDUwMDc5NF19
-->