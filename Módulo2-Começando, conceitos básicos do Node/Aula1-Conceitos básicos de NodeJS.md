Node.js é um ambiente de execução JavaScript construído sobre o motor V8 do Chrome que permite aos desenvolvedores executar código JavaScript fora do navegador. Ele pode ser usado para criar aplicações baseadas em console e aplicações web com Node.js.

Algumas das características do Node.js são mencionadas abaixo:
- I/O não bloqueante: Node.js é assíncrono, permitindo o tratamento eficiente de requisições concorrentes.
- Arquitetura orientada a eventos: Os desenvolvedores podem criar aplicações orientadas a eventos usando callbacks e emissores de eventos.
- Ecossistema extenso de módulos: O npm (Node Package Manager) fornece acesso a milhares de pacotes reutilizáveis.
- Modelo de thread único: O Node.js roda em uma única thread. Apesar de ser assíncrono, ele utiliza um loop de eventos para lidar com as requisições.

## Configurando o Node.js  
Para começar a usar o Node.js, você primeiro precisará instalá-lo em seu sistema.

#### Passo 1: Baixar e Instalar o Node.js
Vá até o site oficial do Node.js ou siga nosso artigo para instalar o Node.js.
Baixe o instalador apropriado para o seu sistema operacional (Windows, macOS ou Linux).
Siga as etapas de instalação para configurar o Node.js.


#### Passo 2: Verificar a Instalação  
Depois de instalado, você pode verificar a instalação abrindo o terminal e digitando os seguintes comandos:
``` bash
node -v
npm -v
```

Esses comandos exibem as versões instaladas do Node.js e do npm (Node Package Manager), confirmando que a instalação foi concluída com sucesso.


#### Passo 3: Criar um Projeto Node.js
Crie um novo diretório para o seu projeto e inicialize-o com o npm executando:
``` bash
mkdir node-project
cd node-project
```

Isso irá gerar um arquivo package.json, que é essencial para gerenciar as dependências do seu projeto.

``` bash
npm init -y
```


#### Passo 4: Escreva sua Primeira Aplicação em Node.js  
Crie um novo arquivo chamado app.js e adicione o seguinte código para criar um servidor HTTP simples:

``` js
const http = require('http');

const server = http.createServer((req, res) => {
    res.write('Hello World!');
    res.end();
});

server.listen(3000, () => {
    console.log('Servidor rodando na porta 3000');
});
```

Saída:
``` bash
node app.js
```

O navegador exibirá a página localhost:3000 com a mensagem “Hello World!”. Isso confirma que o servidor Node.js criado no arquivo app.js está rodando corretamente e respondendo às requisições HTTP.

- O módulo http é importado usando `require('http')` para permitir a criação de um servidor HTTP.
- `http.createServer` cria um novo servidor que escuta requisições HTTP recebidas.
- A função de callback `(req, res)` lida com as requisições e respostas.
- Dentro do callback, `res.write('Hello, World!')` envia "Hello, World!" como resposta, e `res.end()` finaliza a resposta.
- `server.listen(3000)` inicia o servidor na porta 3000. Uma vez que o servidor está rodando, ele registra no console: "Server running on port 3000".


## Arquitetura do Node.js  
O Node.js segue um modelo de loop de eventos de thread única que lida com todas as requisições de clientes usando uma única thread. Ele é baseado em um modelo de I/O não bloqueante, o que significa que o servidor pode processar múltiplas requisições sem precisar esperar uma tarefa terminar antes de iniciar a próxima.

Loop de Eventos: O loop de eventos processa tarefas sem bloqueio, permitindo que o Node.js lide com muitas requisições simultaneamente em uma única thread.

Execução Assíncrona: Funções não bloqueantes são usadas para tarefas como leitura do sistema de arquivos ou consultas a bancos de dados. Isso garante que a aplicação permaneça responsiva.

## Conceitos Básicos do Node.js

1-  Módulos no Node.js O Node.js é baseado em módulos, que são trechos de código reutilizáveis que podem ser importados em aplicações. Isso inclui módulos internos (como fs e http) e pacotes externos instalados usando o NPM.
Módulos Comuns do Node.js
- Módulo HTTP: O módulo http cria servidores web e lida com requisições e respostas.
- Módulo FS (File System): O módulo fs lê, escreve e gerencia arquivos.
- Módulo Path: O módulo path manipula e transforma caminhos de arquivos entre diferentes plataformas.
- Módulo Event: O módulo events permite emitir e escutar eventos.
- Framework Express: O framework Express simplifica o roteamento, o uso de middleware e o tratamento de requisições HTTP.

2- Loop de Eventos e Programação Assíncrona O Node.js utiliza um loop de eventos para lidar com tarefas assíncronas sem bloquear a execução, tornando as aplicações rápidas e responsivas.
- Executa tarefas em segundo plano (non-blocking I/O).
- Usa callbacks quando as tarefas são concluídas.
- Lida com múltiplas requisições de forma eficiente.
- É adequado para aplicações em tempo real e aplicações web.


## Vantagens de Usar Node.js
Alto Desempenho: Utiliza um modelo de I/O não bloqueante e o motor V8 para execução rápida, ideal para aplicações em tempo real e em larga escala.
Escalável: A arquitetura orientada a eventos lida de forma eficiente com muitas conexões simultâneas.
Multiplataforma: Funciona em Windows, macOS e Linux.
Comunidade Ativa: Forte suporte da comunidade com um grande ecossistema de bibliotecas e ferramentas open-source.








