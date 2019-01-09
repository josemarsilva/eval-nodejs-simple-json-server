# eval-nodejs-simple-json-server

## 1. Introdução ##

Este repositório contém os artefatos do projeto **eval-nodejs-simple-json-server**, um servidor JSON que responde à chamadas RESTFULL.

Ao final do projeto, você terá uma base de dados em um único arquivo (.json) que pode ser consultada/atualizada por chamadas HTTP.


### 2. Documentação ###

### 2.1. Diagrama de Caso de Uso ###

* n/a

### 2.2. Diagrama de Implantação

![Diagrama de Implantacao](doc/Diagrama%20de%20Implantacao.png)


### 2.3. Diagrama Modelo de Dados ###

* n/a


## 3. Projeto ##

### 3.1. Pré-requisitos ###

* Node.js v10.14.1 (recomendada)


### 3.2. Guia para Desenvolvimento ###

* Passo #1: [Instalação de pacotes e dependências - json-server](#331-Instalação-de-pacotes-e-dependências)
* Passo #2: Criar um arquivo [db.json] que manterá o conteúdo e sua base de dados 
 

### 3.3. Guia para Configuração ###


### 3.3.1. Instalação de pacotes e dependências ###

a. Instalação do json-server

```cmd
C:\...\eval-nodejs-simple-json-server> npm install -g json-server
```


### 3.4. Guia para Implantação ###

* n/a



### 3.5. Guia para Teste ###

* Passo #1: Iniciar o `json-server` que implementa os formulários RESTFULL sobre a base de daados `db.json`

```cmd
C:\..\eval-nodejs-simple-json-server>json-server db.json

  \{^_^}/ hi!

  Loading db.json
  Done

  Resources
  http://localhost:3000/people

  Home
  http://localhost:3000

  Type s + enter at any time to create a snapshot of the database
```

* Passo #2: Acesse pelo browser a página principal do servidor em http://localhost:3000

![Step-BrowserOpenUrl-localhost-3000](doc/Step-BrowserOpenUrl-localhost-3000.png)


* Passo #3: Acesse pelo browser a página da base de dados armazenada em JSON chamada `people` em http://localhost:3000/people

![Step-BrowserOpenUrl-localhost-3000-people](doc/Step-BrowserOpenUrl-localhost-3000-people.png)


* Passo #4: Faça uma requisição HTTP GET à base de dados armazenada em JSON chamada `people` 

```cmd
curl -H "Cache-Control: no-cache" http://localhost:3000/people
```

... o resultado esperado ...

```txt
[  { "id": 0, "name": "Josemar Silva" }, { "id": 1, "name": "Maria Stela Silva" }, { "id": 2, "name": "Guilherme Silva" }, { "id": 3, "name": "Gabrielle Silva" } ]
```

PS: Lembre-se que no Windows será preciso escapar o caracter aspas duplas \("\). No Linux, o uso do caracter aspas simples \('\) simplifica a linha de comando.


* Passo #5: Faça uma requisição HTTP POST adicionando um novo registro à base de dados armazenada em JSON chamada `people` 

```cmd
curl -X POST -H "Content-Type: application/json" -d "{ \"name\": \"Nome Novo 1\" }" http://localhost:3000/people
```

... o resultado esperado ...

```txt
{
  "name": "Nome Novo 1",
  "id": 4
}
```

* Passo #6: Faça uma requisição HTTP GET para consultar o novo registro recém incluído

```cmd
curl -H "Cache-Control: no-cache" http://localhost:3000/people
```



### 3.6. Guia para Execução ###

* n/a


### 3.7. Guia de Credenciais de Acesso ###

* n/a



## Referências ##

* Sobre instalação:
  * [https://blog.teamtreehouse.com/install-node-js-npm-windows]
  * [https://nodejs.org/en/download/]
* Sites e dicas impressionantes sobre Node.js:
  * [https://github.com/typicode/json-server]
  * [https://github.com/sqreen/awesome-nodejs-projects]
* Sobre vídeos de tutorial
  * https://egghead.io/lessons/javascript-creating-demo-apis-with-json-server
* Sobre o comando curl
  * https://curl.haxx.se/docs/manpage.html
  * 
