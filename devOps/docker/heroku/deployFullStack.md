Acesse https://www.db4free.net/about.php

Clique em "Crie seu banco de dados MySQL gratuitamente »"

Coloque um nome para o banco, nome de usuário e senha (tanto faz, pode inventar qualquer coisa, mas guarde as informações que usar)

Confirme no seu e-mail o cadastro

Acesse seu MySQL Workbench

Certifique-se que tem o banco no estado inicial pronto no MySQL

No menu acesse "Server" -> "Data Export"

Em "Object Selection" -> "Tables to Export", selecione o banco de dados que pretende subir

Em Export Options, deixe selecionado "Export to Dump Project Folder"

Scrolle pra baixo e clique em "Start Export"

Ao vir uma mensagem terminada em "* has finished" está exportado

Acesse https://www.db4free.net/phpMyAdmin/

Entre com as informações que usou de usuário e senha

Clique no nome que deu para o banco na aba da esquerda

No menu do banco de dados, clique em "Importar"

Em ficheiro a importar, selecione uma tabela por vez do banco de dados que exportou, scrolle pra baixo e clique em importar

Clique em "Estrutura" e confira se todas tabelas estão lá, inclusive SequelizeMeta, no caso de Sequelize

Crie um arquivo chamado heroku.yml na raiz do backend e copie o seguinte nele (acredito que somente npm start já funcione, mas usei o run):

    build:
      docker:
        web: Dockerfile
    run:
      web: npm run start

Faça login no Heroku com seu usuário e senha

Clique em "New" -> "Create new app"

Escolha o nome do app e clique em "Create app"

Na página principal do seu app Heroku, clique na aba "Settings"

Verifique as variáveis de ambiente suas no .env da pasta backend

Na seção "Reveal Config Vars" da aba "Seetings" do Heroku, adicione uma a uma as variáveis de acordo com o exemplo abaixo:

PORT=3001 *A porta que tu escolheu expor no docker
DB_USER=usuario_do_db4free
DB_PASS=senha_do_db4free
DB_NAME=db_do_db4free
DB_HOST=db4free.net
DB_PORT=3306 *A porta padrão do db4free

No terminal, acesse a pasta backend e use o comando "heroku stack -a nome-da-sua-aplicação". Ele vai mostrar a lista de recipientes e você estará com o 22 selecionado.

Use o comando "heroku stack:set container -a nome-da-sua-aplicação" para setar o container como recipiente

Use denovo "heroku stack -a nome-da-sua-aplicação" para verificar se selecionou o container

Use o "git init ." para iniciar um repositório no seu backend

Faça "git add ." e git commit -am "mensagem"

Ache o endereço do Heroku indo em settings, App Information e Heroku git URL

Faça "git remote add backend endereço_do_heroku"

Faça "git push backend master"

No heroku, clique em Open App pra ver se o  deploy do backend foi um sucesso

Crie um app para o frontend no Heroku

Se houverem variáveis de ambiente, faça a mesma coisa feita para o backend

Se o .env não estiver no gitgnore, certifique-se de colocar

Adicione o mesmo arquivo heroku.yml na raiz do frontend

No meu TFC um data-testId estava com o I maiúsculo. Certifique-se de mudar para o padrão se acontecer no seu "data-testid".

Mude a URL de acessos para a URL do app backend no Heroku. No TFC, a variável chama-se baseURL e está no arquivo request.js.

Faça o restante do processo igual para o backend. A única diferença é trocar o "git remote add backend endereço_do_heroku" para "git remote add frontend endereço_do_heroku" e "git push backend master" para "git push frontend master".