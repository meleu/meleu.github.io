---
layout: post
title: resumo de fevereiro/2020
date: 2020-03-13
tags:
- pessoal
---

Tentando manter um log dos aprendizados desse ano...

No mês de Fevereiro comecei a fazer o GoStack bootcamp, e o volume de informação despejado no meu cérebro está sendo insano!

Se eu não anotar o que venho aprendendo, para futuras consultas, eu vou ficar perdidinho e esse tempo pode acabar sendo desperdiçado!

## Conceitos

- arquitetura MVC
    - Model:
        - uma representação em mais alto nível do que está no DB.
        - usado para manipular o DB.
        - **OBS.**: regras de negócio **não** ficam no Model.
    - View:
        - como os dados são fornecidos ao cliente.
        - pode ser tanto HTML como simplesmente dados no formato JSON.
    - Controller:
        - ponto de entrada das requisições na aplicação.
        - geralmente cada rota está associada a um método controlador.
        - é onde boa parte das regras de negócio são codificadas.
        - todo modelo tem um controlador, mas também existem controladores para entidades que não são modelos.
        - apenas 5 métodos: `index()`, `show()`, `store()`, `update()` e `delete()`.
        - sempre retorna JSON
        - um controlador não chama outro método controlador.

## JavaScript/Node

- continuo me aperfeiçoando no telegraf para criar bots para telegram

- aprendi a usar Express.js 

- finalmente entendi o conceito de middlewares e como utilizá-lo de inteligentemente.

- aprendi o que é um ORM (Object-Relational Mapping) e estou usando Sequelize.

- usando sequelize-cli para migrations (criação/alteração/remoção de tabelas e campos em DBs) e seeds (maneira de popular tabelas em DBs).

- usar JSON Web Token (jwt) para criar um fluxo de autenticação.

- usar bcrypt para encriptar senhas

- usar Yup para validar dados.

- usar multer para lidar com "Multipart Form" (pra ser sincero não compreendi isso muito bem, apenas segui a receitinha).

- validação/formatação de datas e horários usando date-fns. Também dá pra usar _locales_ para exibir data-hora de acordo com a preferência do usuário (date-fns/locale/pt).

- básico de utilização do mongoose para interagir com o MongoDB.

- usar nodemailer para enviar emails.
    - usar templates de email com express-handlebars e nodemailer-express-handlebars

- filas de email usando Redis e bee-queue

- embelezar mensagens de erro com Youch (e enviar para o Sentry.io).

- truquezinhos do Node:
    - `console.count(label)` mantem um contador interno específico para `label` e imprime o número de vezes que `console.count()` foi chamado com a `label`.
    - `util.promisify()` pega uma função que recebe como argumento um callback _error-first_ e returna uma função equivalente que retorna uma Promise.


## Ferramentas

- docker: usei para instalar containers de PostgreSQL, MongoDB e Redis.

- insomnia.rest: testar APIs REST.

- postbird: GUI bem básico e levinho para acessar banco de dados PostgreSQL.

- DevDocs.io: acessar documentações úteis em um lugar só (dá para "instalar" no smartphone)

- mailtrap.io: serviço bem bacana para testar envio de emails em ambientes de desenvolvimento.

- sentry.io: serviço de monitoramento de exceções em ambiente de produção.


<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEzMzczODIxOV19
-->