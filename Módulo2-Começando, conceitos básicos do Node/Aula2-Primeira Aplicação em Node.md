O NodeJS é amplamente utilizado para construir aplicações escaláveis e de alto desempenho, especialmente para desenvolvimento do lado do servidor. É comumente empregado em servidores web, APIs, aplicações em tempo real e microsserviços.
- Perfeito para lidar com requisições concorrentes devido ao seu modelo de I/O não bloqueante.
- Usado na construção de APIs RESTful, aplicações em tempo real como chats, e muito mais.

## Criando uma Aplicação em Node baseada no Console
Esta seção demonstra como executar JavaScript diretamente no Node.js usando o console (REPL), sem precisar criar arquivos ou configurar um projeto.

Executando Node.js no Console (Sem Configuração Necessária)  
O Node.js permite executar JavaScript diretamente no console usando o REPL. Basta digitar node no terminal para executar JavaScript de forma interativa.
``` bash
$ node
> let name = "Jane";
> console.log("Hello, " + name + "!");
```

Saída:
``` bash
Hello, Jane!
```


## Criando Aplicação com npm init e Módulos Instalados  
Inicialize uma aplicação Node.js usando npm init e aumente sua funcionalidade instalando os módulos necessários.

Passo 1: Inicializar um Projeto Node.js
``` bash
mkdir my-node-app
cd my-node-app
npm init -y
```

Passo 2: Instalar os Módulos Necessários  
Vamos instalar fs (para manipulação de operações com arquivos) e path (para trabalhar com caminhos de arquivos).
``` bash
npm install fs path
```

Passo 3: Criar um Arquivo index.js
Crie um servidor HTTP simples que lê e serve um arquivo.
``` javascript
import http from "http";
import fs from "fs";
import path from "path";
import { fileURLToPath } from "url";

const __filename = fileURLToPath(import.meta.url);
const __dirname = path.dirname(__filename);

const server = http.createServer((req, res) => {
    const filePath = path.join(__dirname, "message.txt");

    fs.readFile(filePath, "utf8", (err, data) => {
        if (err) {
            res.writeHead(500, { "Content-Type": "text/plain" });
            res.end("Erro ao ler o arquivo");
        } else {
            res.writeHead(200, { "Content-Type": "text/plain" });
            res.end(data);
        }
    });
});

server.listen(3000, () => {
    console.log("Servidor está rodando na porta 3000");
});
```


Passo 4: Criar um Arquivo message.txt  
Crie um arquivo message.txt no mesmo diretório e adicione algum conteúdo:
``` txt
Olá, esta é uma aplicação Node.js sem Express!
```


Passo 5: Executar a Aplicação
``` bash
node index.js
```


## Criando Aplicação Web em Node  
Uma aplicação web em Node consiste nos seguintes três componentes importantes:
Importar o módulo necessário
Criar o servidor
Ler a requisição e retornar a resposta

Passo 1: Importar os módulos necessários  
Carregue os módulos do Node usando a diretiva require. Carregue o módulo http e armazene a instância retornada em uma variável.
Sintaxe:
``` js
var http = require("http");
```

Passo 2: Criando um servidor em Node  
Crie um servidor para escutar as requisições do cliente. Crie uma instância de servidor usando o método createServer(). Em seguida, associe o servidor à porta 8080 usando o método listen da instância do servidor.
Sintaxe:
``` js
http.createServer().listen(8080);
```

Passo 3: Ler a requisição e retornar a resposta no Node  
Leia a requisição do cliente feita pelo navegador ou console e retorne a resposta.
Uma função com parâmetros de request e response é usada para ler as requisições do cliente e retornar as respostas.
Sintaxe:
``` js
http.createServer(function (request, response) {
    // lógica para processar a requisição e enviar resposta
}).listen(8080);
```

Passo 4: Criar um Arquivo index.js
``` js
var http = require('http');
 
http.createServer(function (req, res) {

    res.writeHead(200, {'Content-Type': 'text/html'});
    
    res.end('Olá Mundo!');

}).listen(8080);
```

Passo 5: Para executar o programa, digite o seguinte comando no terminal
``` bash
node index.js
```

Saída:
``` bash
Hello World!
```


## Componentes Principais de uma Primeira Aplicação em Node.

Backend (Node.js com Express.js/NestJS/Koa.js): Lida com requisições de API, operações de banco de dados e autenticação.

Banco de Dados (MongoDB, PostgreSQL, MySQL, Redis): Utiliza o MongoDB (NoSQL) ou bancos SQL como PostgreSQL e MySQL.

Frontend (React, Vue.js, Angular): React.js, Vue.js e Angular se integram de forma fluida com backends baseados em Node.

Autenticação e Segurança: Usa JWT (JSON Web Tokens), OAuth ou autenticação baseada em sessões.

Recursos em Tempo Real (Socket.io, WebRTC): O Socket.io permite comunicação via WebSocket para aplicações em tempo real.

