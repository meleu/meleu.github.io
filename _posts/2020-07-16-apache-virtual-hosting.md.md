---
layout: post
title: Apache Virtual Hosting
date: 2020-07-16
author: meleu
tags:
- servidor
---
**NOTA**: isso é mais uma nota pessoal do que um artigo. Apenas use se souber o que está fazendo.

Usei isso num Ubuntu Server 18.04 com Apache 2.

Passos para abilitar um virtual host num servidor rodando apache:
```shell
sudo mkdir /var/www/your_domain
sudo chown $USER:$USER /var/www/your_domain
# criar /var/www/your_domain/index.html
```
Criar o arquivo `/etc/apache2/sites-available/your_domain.conf`:
```
<VirtualHost *:80>
  ServerAdmin webmaster@localhost
  ServerName your_domain
  ServerAlias www.your_domain
  DocumentRoot /var/www/your_domain
  ErrorLog ${APACHE_LOG_DIR}/error.log
  CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

De volta a linha de comando:
```shell
sudo a2ensite your_domain.c
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQwNzcxNTA1NF19
-->