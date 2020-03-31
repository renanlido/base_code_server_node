Passo a passo configurações básicas

1 - yarn init -y
2 - Dependencias:
  - express, sequelize, pg, pg-hstore, dotenv
  - nodemon, sucrase, eslint, prettier eslint-config-prettier
  eslint-plugin-prettier babel-eslint, sequelize-cli -D

3 - Estrutura de pastas:
  - ~/ - raiz do projeto

  - src - código da aplicação
  - src/app.js (configuração do servidor express)
  - src/server.js (instancia e porta onde roda o servidor)
  - src/routes.js (arquivos de rotas)

  - src/app
  - src/app/controllers
  - src/app/models

  - src/database
  - src/database/migrations

  - src/config
  - src/config/database.js

4 - Configuração do nodemon / sucrase
  - Criar arquivo nodemon.json na raiz com a configuração abaixo
    {
      "execMap":
      {
      "js": "node -r sucrase/register"
      }
    }
  - Configurar package.json com a seguinte configuração:
    "scripts": {
      "dev": "nodemon src/server.js",
      "dev:debug": "nodemon --inspect src/server.js",
    },

5 - Criar .editorConfig na raiz com a configuração:
  root = true
  [*]
  indent_style = space
  indent_size = 2
  charset = utf-8
  trim_trailing_whitespace = true
  insert_final_newline = true

6 - Configurar prettier criando arquivo ~/.prettierrc
  - {
    "singleQuote": true,
    "trailingComma": "es5"
    }

7 - Configurar eslint:
  - yarn eslint --init
  - copiar arquivo de configuração modelo

8 - Configuração do app.js
  - importação do express
  - criar classe App
  - chamar método constructor dentro da classe App
  - chamar os métodos this.server=express(), this.middlewares() e this.routes
  - criar os métodos midllewares e routes;
  - metodo midllewares
    - this.server.use(express.json())
  - método routes
    - this.server.use(routes)
  - exportar new App().server

9 - Configuração do server.js
  - importar o app
  - app.listen(3333)

10- Configuração do arquivo de rotas
  - import { Router } from 'express'
  - cria uma constante para instanciar new Router()
  - cria uma rota
  - exporta routes por default

11- Configuração do sequelize
  - criar arquivo .sequelizerc na raiz
  - copiar configuração do modelo
  - configurar arquivo em app/config/database.js conforme modelo
