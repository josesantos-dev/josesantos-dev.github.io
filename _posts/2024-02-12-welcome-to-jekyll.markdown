---
layout: post
title:  "Saiba como criei esse blog estático no GitHub Pages com jekyll"
date:   2024-02-13 20:15:00 -0300
categories: post 
---
# Criando um blog no GitHub Pages com jekyll

Passo a passo do que eu fiz:

`Passo 1`

Instalando o jekyll (no cmd da máquina): `gem install jekyll bundle`

`Passo 2`

Dei início a criação do site estático dando o comando `jekyll new .` (obs: como eu já estava no diretório em que queria iniciar o jekyll eu coloquei um ponto no final, mas se fosse em outro eu colocaria o caminho no final do comando.) Executando esse comando automaticamente ele traz todos os arquivos que compõe o jekyll.

`Passo 3`

Utilizei o comando `bundle exec jekyll serve –livereload` para iniciar um servidor localmente pra ter uma pré visualização antes de subir as alterações para o repositório remoto.

`Passo 4`

Para usar o github pages com jekyll tive que remover o `gem jekyll` no arquivo **gemfile** e habilitar o `gem “github pages”`

`Passo 5`

Depois é necessário fazer um upgrade, então usei o comando `bundle update github-pages` (obs: caso ocorrer algum erro com esse comando, basta da um `bundle update` que resolverá o problema)

`Passo 6`

Configurei algumas coisas no arquivo **_config.yml**, este arquivo é onde está a configuração do blog.

`Passo 7`

Depois de todos esses passos, comecei a criar meu primeiro post, que é justamente esse que você está. O jekyll utiliza **markdown** como linguagem de marcação na criação do blog, então passei a editar os arquivos.md conforme eu os queria.

`Passo 8`

Como meu repositório local já estava conectado com o remoto, eu só adicionei as alterações, commitei e dei um push.  