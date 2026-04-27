Node.js é um ambiente de execução que permite que o JavaScript seja executado fora do navegador para construir aplicações do lado do servidor.
- Construído sobre o motor JavaScript V8.
- Suporta programação assíncrona e orientada a eventos.
- Eficiente para aplicações de rede escaláveis.

  
![Nodejs](https://media.geeksforgeeks.org/wp-content/uploads/20250818182101841499/Nodejs.webp "Click to enlarge")


##  Programa "Hello, World!" em Node.js  
Um programa “Hello, World!” é a forma mais simples de começar com Node.js, mostrando como o JavaScript pode ser executado fora do navegador.
- Executa JavaScript em um ambiente de servidor ou linha de comando.
- Não depende do console do navegador.

```node.js
console.log("Hello, World!");
```

Output:
![helloworld](https://media.geeksforgeeks.org/wp-content/uploads/20250221160505357131/helloworld.png "Click to enlarge")
Hello, World! in NodeJS


## Recursos do Node.js

JavaScript no Servidor: Executa JavaScript fora do navegador para desenvolvimento de backend.
Assíncrono e Não Bloqueante: Lida com múltiplas requisições de forma eficiente usando um modelo orientado a eventos.
Loop de Eventos Monothread: Gerencia tarefas concorrentes sem a sobrecarga de múltiplas threads.
Motor V8: Utiliza o motor de alto desempenho do Google para executar JavaScript rapidamente.
Escalável e Leve: Adequado para microsserviços e aplicações de alto tráfego.
Ecossistema Rico do NPM: Oferece acesso a milhares de pacotes open-source reutilizáveis.

## Funcionamento do Node.js  

O Node.js é um ambiente de execução que permite que o JavaScript seja executado fora do navegador para construir aplicações escaláveis do lado do servidor.
- Construído sobre o motor JavaScript V8.
- Utiliza uma arquitetura assíncrona e orientada a eventos.
- Adequado para aplicações de rede escaláveis.

## Modelo de Loop de Eventos Monothread  
O Node.js opera em uma única thread, mas lida de forma eficiente com múltiplas requisições simultâneas usando um loop de eventos.
- Cliente Envia Requisição: Solicita dados, arquivos ou operações em banco de dados.
- Loop de Eventos Processa: Tarefas não bloqueantes são delegadas sem interromper a execução.
- Processamento em Segundo Plano: O Node.js continua atendendo outras requisições.
- Callback Executa: A resposta é retornada assim que a tarefa é concluída.

``` node
const fs = require('fs');

fs.readFile('file.txt', 'utf8', (err, data) => {
    if (err) throw err;
    console.log(data); 
});

console.log("Reading file...");
```

## Componentes da Arquitetura do Node.js  
A arquitetura do Node.js é composta por elementos que trabalham em conjunto para lidar com operações assíncronas e não bloqueantes de forma eficiente.
- Motor V8: Compila JavaScript para código de máquina, garantindo execução rápida.
- Loop de Eventos: Gerencia tarefas assíncronas sem bloquear a thread principal.
- Libuv: Responsável por operações de I/O, pool de threads e temporizadores.
- I/O Não Bloqueante: Executa tarefas sem precisar esperar a conclusão das anteriores.

## Casos de Uso do Node.js  
O Node.js é bem adequado para construir aplicações de alto desempenho, escaláveis e em tempo real. Alguns casos comuns incluem:

APIs Web e Serviços de Backend: Usado para criar APIs RESTful e GraphQL, além de alimentar serviços de backend para aplicações web e móveis.

Aplicações em Tempo Real: Aplicativos de chat (ex.: WhatsApp, Slack). Serviços de streaming ao vivo (ex.: Netflix, Twitch).

Arquitetura de Microsserviços: Permite construir serviços escaláveis e independentes, comumente usados em aplicações baseadas em nuvem.

Aplicações de IoT (Internet das Coisas): Lida com fluxos de dados em tempo real de dispositivos, sendo adequado para casas inteligentes e sistemas baseados em sensores.

Computação Serverless: Executa funções leves de forma eficiente em plataformas de nuvem como AWS Lambda e Azure Functions.

Aplicações de Página Única (SPAs): Dá suporte a apps em React, Angular e Vue.js, lidando de forma eficiente com requisições de APIs de backend.

Aplicações Intensivas em Dados: Processa análises em tempo real e integra-se bem com bancos NoSQL como MongoDB e Firebase.





