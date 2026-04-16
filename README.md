## NodeJs Studies

Node.js é um runtime JavaScript de código aberto e multiplataforma, construído sobre o motor V8 do Chrome. Ele permite que desenvolvedores executem JavaScript fora do navegador para criar aplicações de servidor rápidas e escaláveis.

- O JavaScript era inicialmente uma linguagem apenas de frontend, e o Node.js (2009) possibilitou o desenvolvimento backend também.
- Arquitetura não bloqueante e orientada a eventos para alto desempenho.
- Suporta a criação de APIs REST, aplicações em tempo real e microsserviços.
- Vem com uma rica biblioteca de módulos através do npm (Node Package Manager).

First code example:

``` node.js
// Import the http module
const http = require("http");

// Create a server
const server = http.createServer((req, res) => {
    res.statusCode = 200;
    res.setHeader("Content-Type", "text/plain");
    res.end("Welcome to the Node.js Tutorial");
});

// Listen on port 3000
server.listen(3000, () => {
    console.log(
        "Server is running on http://localhost:3000");
});
```

Isso iniciará um servidor e, quando você acessar http://localhost:3000, ele exibirá:
>
> Welcome to the Node.js Tutorial
>

O módulo http é importado para criar um servidor HTTP básico. O método createServer() é usado para lidar com solicitações recebidas e enviar respostas. O servidor escuta na porta 3000 e uma mensagem é exibida no navegador quando acessado.

## Preciso aprender Node.js
Ele permite que desenvolvedores criem aplicações de servidor rápidas e escaláveis usando JavaScript.

- Possibilita desenvolvimento full-stack com uma única linguagem.
- Ideal para aplicativos em tempo real, como servidores de chat e jogos.
- Lida de forma eficiente com tarefas intensivas de I/O graças à arquitetura não bloqueante.
- Conta com uma grande comunidade e um vasto ecossistema de pacotes via npm.

## Introdução ao Node.js
A introdução ao Node.js fornece uma visão geral de seu ambiente de execução, arquitetura e de como ele possibilita o desenvolvimento de JavaScript no lado do servidor.

* Introdução ao Node.js 
* Importância do Node.js 
* Funcionamento

## Primeiros Passos  
Compreenda os conceitos básicos do Node.js e comece criando sua primeira aplicação simples.

- Noções básicas 
- Primeira aplicação 
- REPL

## Gerenciador de Pacotes do Node (NPM)  
Gerencie dependências e pacotes do projeto de forma eficiente usando o NPM.

- NPM (Gerenciador de Pacotes Node.js) 
- Criar e publicar pacotes NPM 
- Instalação global de dependências

## Módulos no Node.js  
Entenda como organizar e reutilizar código utilizando diferentes tipos de módulos.

- Módulos 
- Módulos principais 
- Módulos de terceiros 
- Módulos personalizados


## Programação Assíncrona  
Aprenda como o Node.js lida com múltiplas tarefas de forma eficiente utilizando operações não bloqueantes.

- Bloqueante e Não Bloqueante  
- Conceito de Callback  
- Encadeamento de Promises  
- Loop de Eventos

## Conceito Fundamental  
Compreenda os conceitos essenciais do Node.js que controlam escopo, contexto e comportamento global.

- This Binding (Vinculação do this)
- Objetos Globais
- Variável de Sessão


## Construindo Aplicações  
Crie e gerencie aplicações do lado do servidor utilizando os recursos e ferramentas do Node.js.

- Servidor Web
- Frameworks
- Processo Filho

## Express.js  
Construa aplicações web de forma eficiente utilizando o framework Express.js.

- Introdução ao Express.js
- Padrão de Design MVC
- Servindo Arquivos Estáticos
- Middleware
- Template EJS


## Depuração e Utilitários  
Ferramentas e técnicas para depurar código e melhorar o fluxo de trabalho de desenvolvimento.

- Depuração
- Definir Cor da Fonte do Console
- Reinício Automático do Servidor com Nodemon


## Referências Completas do Node.js  
Abrange os módulos principais e as APIs internas utilizadas para o desenvolvimento no lado do servidor.

#### Sistema e Módulos Centrais  
Lide com funcionalidades essenciais relacionadas às operações do sistema e ao ambiente de execução.
- Assert (Afirmação)
- Console
- Utility (Utilitário)
- OS (Sistema Operacional)
- Processo
- V8
- Módulo VM

#### Manipulação de Arquivos e Dados  
Gerencie o processamento de dados, operações com arquivos e transformação de dados.
- Buffer
- String Decoder (Decodificador de Strings)
- Query String (String de Consulta)
- File System (Sistema de Arquivos)
- Path Module (Módulo de Caminho)
- Stream (Fluxo)
- URL

#### Rede, Segurança e Desempenho  
Suporte para comunicação, recursos de segurança e otimização de desempenho.
- Módulo HTTP
- HTTP2
- DNS
- UDP/DataGram
- Módulo TLS/SSL
- Crypto (Criptografia)
- Zlib
- Módulo Timers (Temporizadores)


## Vantagens do Node.js

Escalabilidade Fácil: Compila e executa JavaScript em altíssima velocidade, tornando-o altamente escalável.

Aplicativos Web em Tempo Real: Permite comunicação em tempo real para chat, jogos, atualizações em redes sociais e muito mais.

Microservices: É leve e ideal para arquiteturas de microsserviços.

JavaScript em Todo Lugar: Aprenda JavaScript uma vez e você poderá usá-lo tanto no front-end quanto no back-end.

Transmissão de Dados Eficiente: Lida de forma eficiente com processos de I/O, como transcodificação de mídia durante uploads.

Arquitetura Orientada a Eventos: Diferente dos servidores tradicionais, o Node.js gerencia requisições simultâneas de forma eficaz.

Forte Suporte da Comunidade: Conta com uma comunidade independente que apoia seu desenvolvimento.


## Pré-requisitos 
- JavaScript 
- Desenvolvimento Web básico

## Instalação 
- Para começar a usar o Node.js, você precisa instalá-lo e configurá-lo em sua máquina. Instalação no Windows
- Instalação no Linux
- Instalação no macOS



