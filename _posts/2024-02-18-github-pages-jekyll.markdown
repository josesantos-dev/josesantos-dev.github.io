---
layout: post
title:  "Saiba como criei esse blog estático no GitHub Pages com jekyll"
date:   2024-02-13 20:15:00 -0300
categories: post 
---
# Criando um blog no GitHub Pages com jekyll


## Objetivo: 

Meu objetivo era criar um blog estático para praticar Git e GitHub utilizando algum framework. Decidi começar com o Jekyll, projetado para criar blogs, portfólios, páginas de documentação e outros tipos de sites estáticos. O Jekyll é escrito em Ruby, mas não é necessário saber programar em Ruby para desenvolver o blog. Além disso, o Jekyll já está integrado com o GitHub Pages. O desenvolvimento das postagens do blog é feito utilizando Markdown.

Após criar o blog com o Jekyll, planejo criar mais três blogs utilizando frameworks diferentes que têm o mesmo propósito: criar blogs estáticos. Vou usar o Hexo, outro framework para criação de blogs, escrito em Node.js para geração de arquivos estáticos. Além disso, pretendo utilizar o Hugo, escrito em Go. Por fim, também utilizarei o Pelican, um gerador de sites estáticos pouco conhecido, baseado em Python. Se você está familiarizado com Python, pode usar o software para criar páginas estáticas usando Markdown e reStructuredText. O Pelican vem com um conjunto de temas que podem ser personalizados.

## Passo a passo do que eu fiz:

`1`
Como o Jekyll é escrito em Ruby, é necessário ter o Ruby instalado na máquina. Então, baixei o Ruby no [site oficial](https://www.ruby-lang.org/pt/). Após instalá-lo, uma tela do terminal aparece. Nesse momento, escolhi instalar as três opções: `1 - MSYS2 base installation`, `2 - MSYS2 system update (opcional)` e `3 - MSYS2 and MINGW development toolchain`. Com isso, o Ruby foi instalado corretamente.

`2`
Instalação do Jekyll: Para instalar o Jekyll, abri o terminal da minha máquina e utilizei exatamente o seguinte comando: `gem install jekyll bundler`, em seguida, pressionei "Enter" e a instalação foi concluída.

`3`
Criando um repositório remoto no GitHub para hospedar o blog: Como se trata de um blog pessoal, a intenção é que ele tenha meu nome de usuário na URL. Portanto, nomeei o repositório com meu nome de usuário do GitHub, deixei-o público e adicionei um README.md.

`4`
Trabalhando com o repositório remoto na minha máquina: No explorador de arquivos, escolhi a pasta onde desejava criar o projeto. Abri o terminal e utilizei o comando `git clone [URL do repositório remoto]`, o que gerou um repositório local. Em seguida, abri a pasta no meu VS Code para começar a fazer alterações.

`5`
Com a pasta do projeto aberta no VS Code, o primeiro passo foi fazer as configurações iniciais para começar o projeto do Jekyll. Abri o terminal do VS Code e executei o comando `jekyll new .`. Como eu já estava na pasta onde queria iniciar o projeto, não era necessário reescrever o caminho, bastava usar um "." (ponto). Ao executar esse comando, ocorreu um conflito, alegando que a pasta estava vazia, mas não estava. Para resolver isso, usei o mesmo comando, mas desta vez, adicionei `--force` no final, para forçar a criação do projeto. Em seguida, os diretórios e arquivos que compõem o Jekyll foram instalados e apareceram automaticamente no VS Code.

`6`
A primeira alteração que fiz nos arquivos que compõem o projeto foi no `Gemfile`. O `Gemfile` informa que, para usar o GitHub Pages com o Jekyll, é necessário remover o `gem "jekyll"`, que está no próprio arquivo `Gemfile`, e habilitar o `gem "github-pages"`, que também está no mesmo arquivo.

`7`
Em seguida, atualizei o bundle. Foi necessário executar `bundle update github-pages` no terminal do VS Code, mas deu um erro ao rodar esse comando, informando que não foi possível encontrar o `gem "github-pages"`. Para resolver e conseguir fazer a atualização, rodei apenas `bundle update`, o que resolveu o problema e fez as atualizações. Utilizei então `bundle install` e pude ver que estava tudo completo e que já estava utilizando o GitHub Pages.

`8`
Nesta etapa, configurei algumas coisas, como o título do blog, e-mail que aparece no rodapé do blog, a descrição e o endereço do meu GitHub. Tudo isso foi feito no arquivo `_config.yml` do Jekyll, onde ficam as configurações do blog.

`9`
Para ver o blog funcionando de fato antes de enviá-lo para o repositório remoto, utilizei o comando `bundle exec jekyll serve --livereload`. Esse comando é usado para iniciar um servidor local. Não necessariamente precisa do `--livereload`; esse comando é para carregar automaticamente as alterações feitas nos arquivos que não sejam os de configurações. Ele não carrega automaticamente as alterações feitas nas configurações; nesse caso, teria que encerrar e iniciar novamente o servidor local. Ao rodar o comando, ele gerou um endereço de acesso ao servidor.

`10`
Um erro que enfrentei ao tentar pela primeira vez foi não conseguir acesso ao endereço do servidor, pois não era gerado de nenhuma maneira. Apareciam algumas informações indicando o erro, mas como eu nunca tinha tido contato com o Jekyll, tive que pesquisar um pouco. Foi aí que encontrei um comentário em um tutorial no YouTube, e também tive ajuda do meu cunhado, que me pediu para adicionar no arquivo `Gemfile` do Jekyll o seguinte: `gem "faraday-retry"`, e na linha de comando `bundle add webrick`. O `gem "faraday-retry"` é uma extensão para a biblioteca Faraday em Ruby, que fornece capacidades automáticas de retry (tentativas) para solicitações HTTP feitas com o Faraday. Faraday é uma biblioteca HTTP flexível e modular usada para fazer solicitações HTTP em Ruby. Já o `bundle add webrick` é usado para adicionar uma nova dependência ao arquivo Gemfile de um projeto Ruby. Especificamente neste caso, ele adiciona o `gem webrick` ao projeto.

`11`
Neste ponto, foi o momento de fazer o primeiro commit para colocar o blog online. Usando o terminal do VS Code, utilizei `git add .` para adicionar tudo, em seguida, `git commit -m "descrição do commit"`, e um `git push origin main` para enviar todos os arquivos do Jekyll do repositório local para o remoto.

`12`
Fui às configurações do repositório remoto e na parte do `GitHub Pages` não precisei fazer nada, pois o source já estava como padrão. A única coisa que fiz foi pegar a URL do blog.

`13`
Criei o primeiro post pelo VS Code, mas também era possível criá-lo no GitHub. Deletei o post padrão que vem, o "Welcome to Jekyll", e comecei a criar um do zero, que no caso é este mesmo. Como já mencionei, o Jekyll usa Markdown para a criação dos posts. Criei um arquivo .md, e a primeira coisa que fiz foi criar o cabeçalho do post, que é onde algumas configurações são definidas, como `layout: post`, `title: "O título deste post"`, `date: data e hora da criação do post`, e no final, por padrão, timezone: `-0300`, e, por fim, `categories: o que for passado aqui vai ser o subcaminho na URL do post`. Comecei a criar o post com todas essas informações acima, utilizando Markdown. Mesmo não tendo muito conhecimento, precisei olhar algumas documentações e também utilizei o ChatGPT para aprender o básico do Markdown para poder desenvolver o post.

`14`
No último passo, adicionei todas as alterações utilizando `git add .`, em seguida, fiz um `commit` com a mensagem informando a criação do primeiro post, e por fim, dei um `git push origin main` para enviar as alterações para o repositório remoto. 
