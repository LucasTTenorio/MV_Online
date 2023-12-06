Documentação Principal MV Online
==========================

Requisitos
-------------
Node.js e RPGMaker MV

Instalação
-------------

Deploy na Heroku aqui:

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://dashboard.heroku.com/new?template=https://github.com/Nelderson/MV_Online/tree/master)

Usar `git clone https://github.com/LucasTTenorio/MV_Online.git` ou baixe e descompacte para o diretório de sua escolha.

Run `npm install` para baixar todas as dependências do servidor. Usar `npm install -d` para usuários do Windows.

Depois de configurar o servidor run `npm start` para iniciar o servidor.


Configuração do Servidor
-------------

Dentro do `configurations/config.js` arquivo, há várias coisas para configurar:

`port` define em qual porta o servidor será executado (Padrão `8000`)

`jwtSecret` define o segredo que o JWT está assinado.  Altere isso por motivos de segurança em um ambiente de produção

`firstHash` é o segredo de hash inicial para o sistema de login.  Isso é o mesmo que o primeiro hash do plugin do cliente.  Recomendado que isso seja alterado antes de colocar em um ambiente de produção


`mailFrom` Quando um usuário se registra, ele recebe um e-mail desse endereço.
`smtps://username@gmail.com:password@smtp.gmail.com`  (Etapas adicionais são necessárias se você quiser usar o Gmail.)

`mongoDBconnect` Link e credenciais para o banco de dados MongoDB. `mongodb://username:password@linktomongodb.com:39504/collection`


Configuração do Cliente (RPGMaker MV)
-------------

Adicione o `css` na raiz do diretório do projeto

Adicione os arquivos em `game_resources/js/plugns` que você quer para seus plugins para o seu próprio `js/plugins` do seu jogo. (`Online_Main_Core.js` é manditory para todos os outros plugins)

Adicione os arquivos do `game_resources/js/libs` pasta para o seu próprio `js/libs` pasta

Modifique seu `index.html` no seu jogo para adicionar isso no cabeçalho:

```html
<!-- Nel Add -->
<link rel="stylesheet" type="text/css" href="./css/bootstrap3.3.5.min.css" >
<link rel="stylesheet" type="text/css" href="./css/fontawesome4.4.0.min.css" >
<link rel="stylesheet" type="text/css" href="./css/MMO.css">
<!-- Nel Add -->
```

E isso no corpo, não se esqueça da mudança localhost para o seu IP ou Domínio:

```html
<!-- Nel Add -->
<script type="text/javascript" src="./js/libs/jquery-2.1.4.min.js"></script>
<script type="text/javascript" src="./js/libs/jquerymobile1.4.5.min.js"></script>
<link rel="stylesheet" type="text/css" href="./css/jquerymobile1.4.5.min.css">
<script type="text/javascript" src="./js/libs/crypto.sha1.js"></script>
<script type="text/javascript" src="./js/libs/socket.io-2.2.0.js"></script>
<!-- Nel Add -->
```
