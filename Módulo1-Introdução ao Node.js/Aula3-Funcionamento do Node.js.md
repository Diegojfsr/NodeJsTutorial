Node.js é um ambiente de execução que permite que o JavaScript rode fora dos navegadores, voltado para o desenvolvimento no lado do servidor. Ele é rápido, escalável e projetado para lidar com múltiplas tarefas de forma eficiente.
- Construído sobre o motor V8 do Chrome e criado por Ryan Dahl.
- JavaScript normalmente roda em navegadores como Chrome (V8) e Firefox (SpiderMonkey).
- Permite que o JavaScript realize operações em nível de sistema, como manipulação de arquivos.
- Utiliza arquitetura assíncrona e não bloqueante.
- Funciona em um loop de eventos monothread para melhor desempenho.
- Lida com múltiplas requisições simultaneamente usando recursos mínimos.
- Ideal para aplicações em tempo real, como APIs, aplicativos de chat e serviços de streaming.

## Npm no Node.js  
O NPM (Node Package Manager) é uma ferramenta que acompanha o Node.js e é usada para gerenciar dependências e configurações de projetos.
- Instalado automaticamente com o Node.js e utilizado para gerenciar pacotes.
- npm init inicializa um projeto e cria o arquivo package.json.
- package.json


## Processo de Manipulação de Requisições no Node.js  
O Node.js lida com requisições de clientes usando uma arquitetura orientada a eventos, com o Event Loop e o Thread Pool, para garantir desempenho eficiente e escalável.
Processo de Manipulação de Requisições no Node.js
- O cliente envia uma requisição ao servidor web do Node.js.
- A requisição pode ser bloqueante (síncrona) ou não bloqueante (assíncrona).
- O Node.js recebe a requisição e a coloca na Fila de Eventos (Event Queue).
- O Event Loop verifica continuamente a fila e processa as requisições na ordem FIFO (First In, First Out).

## Processamento de Requisições  
As requisições são tratadas de forma diferente dependendo se são bloqueantes ou não bloqueantes.
- Se a requisição for não bloqueante, ela é processada imediatamente e a resposta é enviada de volta ao cliente.
- Se a requisição for bloqueante, ela é encaminhada para o Thread Pool.


## Manipulação pelo Thread Pool  
Gerencia tarefas bloqueantes em uma aplicação web atribuindo-as a threads disponíveis para execução.
- O Thread Pool contém um número limitado de threads.
- Se uma thread estiver disponível, a tarefa bloqueante é atribuída a ela.
- Quando concluída, o resultado é retornado ao Event Loop, que envia a resposta ao cliente.
- Se todas as threads estiverem ocupadas, novas requisições bloqueantes devem aguardar em uma fila.
Observação: Uma thread funciona como um trabalhador que processa tarefas bloqueantes, permitindo que a aplicação principal continue rodando de forma fluida.


## Operação Bloqueante ou Síncrona  
Em uma operação bloqueante ou síncrona, as tarefas são executadas uma após a outra, e o programa espera cada tarefa terminar antes de passar para a próxima.
- As tarefas são executadas em uma sequência fixa.
- O programa espera até que a tarefa atual seja concluída.
- Operações demoradas podem atrasar todo o programa.
- É simples de entender, mas menos eficiente para múltiplas requisições.

#### Exemplo para entender operações síncronas:
Lê um arquivo de forma síncrona usando fs.readFileSync() com codificação UTF-8 e bloqueia a execução.
 Nesse caso, o programa só continua após a leitura completa do arquivo, ilustrando como uma operação bloqueante funciona.

``` node
// Importa o módulo de sistema de arquivos (fs)
const fs = require('fs');

// Lê o arquivo de forma síncrona com codificação UTF-8
const result = fs.readFileSync('./sync.txt', 'utf-8');

// Exibe o conteúdo do arquivo no console
console.log(result);
```
Mostra a saída do arquivo após ele ser completamente lido.
Em outras palavras, o conteúdo só é exibido no console depois que a leitura síncrona do arquivo termina, ilustrando o comportamento bloqueante desse tipo de operação.


Ao rodar esse script abaixo, com o comando `nodemon blockingsync.js`, o Nodemon monitora alterações no arquivo e reinicia automaticamente a aplicação, exibindo o conteúdo do arquivo lido de forma síncrona.
``` node
// blockingsync.js
// Exemplo simples de operação síncrona em Node.js

const fs = require('fs');

// Lê o arquivo de forma síncrona
const result = fs.readFileSync('./sync.txt', 'utf-8');

// Exibe o conteúdo do arquivo
console.log(result);

// Saída simulada (conteúdo do arquivo sync.txt):
// eisha: +91 1111111111
// ruhi: +91 2222222222
```
Adiciona logs para demonstrar como a execução é pausada durante a leitura do arquivo.
Isso significa inserir mensagens no console antes e depois da operação de leitura, para evidenciar que o programa só continua após a conclusão da leitura síncrona.



Esse código abaixo demonstra claramente que a execução pausa na linha do fs.readFileSync() até que o arquivo seja totalmente lido, e só depois os próximos console.log() são exibidos.
``` node
// sync-2nd part
const fs = require('fs');

console.log("1"); // Log antes da leitura

// Lê o arquivo de forma síncrona (bloqueia até terminar)
const result = fs.readFileSync('./sync.txt', 'utf-8');

console.log(result); // Conteúdo do arquivo
console.log("2");    // Executado somente após a leitura
console.log("3");    // Continua normalmente
```
Exibe a ordem de execução, confirmando o comportamento síncrono (bloqueante).
Ou seja, os logs aparecem na sequência exata em que o código é escrito, demonstrando que o programa só continua depois que a leitura do arquivo é concluída.


Ao rodar esse script abaixo com nodemon blockingSync.js, você verá a saída na ordem exata: primeiro o log "1", depois o conteúdo do arquivo, seguido por "2" e "3". Isso confirma o comportamento síncrono/bloqueante do fs.readFileSync().
``` node
// blockingSync.js
const fs = require('fs');

console.log("1"); // Executa primeiro

// Lê o arquivo de forma síncrona (bloqueia até terminar)
const result = fs.readFileSync('./sync.txt', 'utf-8');

console.log(result); // Conteúdo do arquivo (ex.: contatos)
console.log("2");    // Só aparece depois da leitura
console.log("3");    // Continua normalmente
```


## Operação Não Bloqueante ou Assíncrona  
Em uma operação não bloqueante ou assíncrona, as tarefas são executadas sem esperar que as anteriores sejam concluídas, permitindo o tratamento eficiente de múltiplas operações.
- As tarefas rodam em segundo plano sem bloquear a execução.
- Melhora o desempenho ao lidar com várias operações simultaneamente.
- Utiliza callbacks ou promises para tratar os resultados após a conclusão.


``` node
// async.js
const fs = require('fs');

console.log("1"); // Executa primeiro

// Lê o arquivo de forma assíncrona (não bloqueia a execução)
fs.readFile('./async.txt', 'utf-8', (err, result) => {
    if (err) {
        console.error("Erro ao ler o arquivo:", err);
        return;
    }
    console.log(result); // Conteúdo do arquivo exibido depois
});

console.log("2"); // Executa enquanto o arquivo ainda está sendo lido
console.log("3"); // Continua normalmente
```
Solicitação não bloqueante
Nesse caso, os logs "2" e "3" aparecem antes do conteúdo do arquivo, confirmando o comportamento não bloqueante/assíncrono.

- Usa fs.readFile(), que executa de forma assíncrona sem bloquear o programa.
- Os logs "2" e "3" são impressos antes do conteúdo do arquivo.
- O conteúdo do arquivo é exibido depois, por meio de uma função de callback.
- A execução continua enquanto o arquivo está sendo lido em segundo plano.
- Demonstra o comportamento não bloqueante, onde as tarefas rodam de forma concorrente.

## Benefícios do Node.js  
Oferece um ambiente poderoso para construir aplicações de servidor rápidas e escaláveis usando JavaScript.
- Permite a execução de JavaScript fora do navegador, em um ambiente de servidor.
- Possibilita que o JavaScript interaja com recursos de nível de sistema, como sistemas de arquivos e processos.
- Facilita a criação de servidores web escaláveis e aplicações de backend utilizando JavaScript.


