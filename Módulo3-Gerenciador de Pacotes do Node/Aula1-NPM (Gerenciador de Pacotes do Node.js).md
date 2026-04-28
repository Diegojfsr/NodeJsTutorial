NPM (Node Package Manager) é o gerenciador de pacotes padrão para o Node.js. Ele ajuda a gerenciar dependências de projetos, scripts e bibliotecas de terceiros, sendo instalado automaticamente quando você instala o Node.js.
- Ele é usado principalmente para gerenciar pacotes ou módulos, que são trechos de código pré-construídos que estendem a funcionalidade da sua aplicação Node.js.
- O registro do NPM hospeda milhões de pacotes gratuitos que você pode baixar e usar em seu projeto.
- O NPM é instalado automaticamente quando você instala o Node.js, então não é necessário configurá-lo manualmente.

## Pacote em Node.js  
Um pacote em Node.js é um módulo reutilizável de código que adiciona funcionalidades à sua aplicação. Ele pode ser qualquer coisa, desde uma pequena função utilitária até uma biblioteca completa.
- Os pacotes podem ser instalados a partir do registro do NPM.
- Eles são armazenados na pasta node_modules dentro do seu projeto.
- Você pode facilmente instalar, atualizar ou remover pacotes usando comandos do NPM.


## Usando o NPM com Node.js  
Para começar a usar o NPM em seu projeto, siga estes passos simples:

#### Passo 1: Instalar Node.js e NPM  
Primeiro, você precisa instalar o Node.js. O NPM já vem incluído na instalação do Node.js.

#### Passo 2: Verificar a Instalação  
Após a instalação, verifique se o Node.js e o NPM foram instalados executando os seguintes comandos no seu terminal:
``` bash
node -v
npm -v
```
Esses comandos mostrarão as versões instaladas do Node.js e do NPM.
Saída esperada:
Versão do Node.js
Versão do NPM

#### Passo 3: Inicializar um Novo Projeto Node.js  
No terminal, navegue até o diretório do seu projeto e execute:
``` bash
npm init -y
```
Esse comando criará um arquivo package.json, que armazena metadados sobre o seu projeto, incluindo dependências e scripts.

#### Passo 4: Instalar Pacotes com o NPM  
Para instalar um pacote, use o seguinte comando:
``` bash
npm install <nome-do-pacote>
```

Por exemplo, para instalar o framework Express.js:
``` bash
npm install express
```
Isso adicionará o express à pasta node_modules e atualizará automaticamente o arquivo package.json com as informações do pacote instalado.

#### Passo 5: Instalar Pacotes Globalmente  
Para instalar pacotes que você deseja usar em vários projetos, utilize a flag -g:
``` bash
npm install -g <nome-do-pacote>
```

#### Passo 6: Executar Scripts  
Você também pode definir scripts personalizados no arquivo package.json, dentro da seção `"scripts"`. Por exemplo:
``` json
{
  "scripts": {
    "start": "node app.js"
  }
}
```

Em seguida, execute o script com:
``` bash
npm start
```


## Usando Pacote NPM no Projeto  
Crie um arquivo chamado app.js no diretório do projeto para utilizar o pacote:
``` js
// app.js

const express = require('express'); // importa o pacote necessário
const app = express();

app.get('/', (req, res) => {
    res.send('Hello, World!');
});

app.listen(3000, () => {
    console.log('Servidor rodando em http://localhost:3000');
});
```

- `express()` cria uma instância da aplicação Express.
- `app.get()` define um manipulador de rota para requisições HTTP GET na URL raiz (`/`).
- `res.send()` envia a resposta "Hello, World!" para o cliente.
- `app.listen(3000)` inicia o servidor na porta 3000, e `console.log()` exibe a URL do servidor no terminal.

Agora execute a aplicação com:
``` bash
node app.js
```

Depois, acesse http://localhost:3000 no seu navegador, e você deverá ver a mensagem:
``` codigo
Hello, World!
```


## Gerenciando as dependências do projeto

#### 1. Instalando Todas as Dependências  
Em um projeto Node.js, as dependências são armazenadas no arquivo package.json.
Para instalar todas as dependências listadas nesse arquivo, execute:
``` bash
npm install
```
Esse comando fará o download de todos os pacotes necessários e os colocará na pasta node_modules.

#### 2. Instalando um Pacote Específico  
Para instalar um pacote específico, use:
``` bash
npm install <nome-do-pacote>
```

Você também pode instalar um pacote como dependência de desenvolvimento usando:
``` bash
npm install <nome-do-pacote> --save-dev
```

Dependências de desenvolvimento são pacotes necessários apenas durante o processo de desenvolvimento, como bibliotecas de testes.
Para instalar um pacote e ao mesmo tempo salvá-lo no arquivo package.json (no caso de uso com Node.js), adicione a flag --save.
A flag --save já é padrão no comando `npm install`, portanto é equivalente a:

Exemplo:
``` bash
npm install express --save
```

Uso das Flags:
- --save: flag que controla onde os pacotes devem ser instalados.
- --save-prod: ao usar essa flag, os pacotes aparecerão em Dependencies, o que também é o comportamento padrão.
- --save-dev: ao usar essa flag, os pacotes aparecerão em devDependencies e serão utilizados apenas no modo de desenvolvimento.

Observação:  
Se já existir um arquivo package.json com todos os pacotes mencionados como dependências, basta digitar:
``` bash
npm install
```
no terminal, e todos os pacotes serão instalados automaticamente.

#### 3. Atualizando Pacotes  
Você pode atualizar facilmente os pacotes do seu projeto usando o seguinte comando:
``` bash
npm update
```

Esse comando atualizará todos os pacotes para suas versões mais recentes compatíveis, com base nas restrições de versão definidas no arquivo package.json.
Para atualizar um pacote específico, execute:
``` bash
npm update <nome-do-pacote>
```

#### 4. Desinstalando Pacotes  
Para desinstalar pacotes usando o NPM, siga a sintaxe abaixo:
``` bash
npm uninstall <nome-do-pacote>
```

Para desinstalar pacotes globais:
``` bash
npm uninstall <nome-do-pacote> -g
```

## Pacotes NPM Populares para Node.js  
O NPM possui uma biblioteca enorme de pacotes. Aqui estão alguns pacotes populares que podem aprimorar suas aplicações em Node.js:

| Pacote    | Função Principal                                                                    | Exemplo de Uso Prático                                                              |
| --------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Express   | Framework rápido e minimalista para criar APIs e aplicações web.                    | Criar um servidor simples que responde “Hello, World!” em `http://localhost:3000`.  |
| Mongoose  | Ferramenta de modelagem de objetos para trabalhar com MongoDB no Node.js.           | Definir esquemas e modelos para salvar e consultar documentos em um banco MongoDB.  |
| Lodash    | Biblioteca utilitária para manipulação de arrays, objetos e strings com eficiência. | Usar `_.cloneDeep(obj)` para clonar objetos complexos sem referência compartilhada. |
| Axios     | Cliente HTTP baseado em promises para fazer requisições.                            | Fazer uma requisição GET: `axios.get('https://api.exemplo.com/data')`.              |
| React     | Biblioteca front-end para construir interfaces de usuário.                          | Criar um componente: `function App() { return <h1>Olá Mundo</h1>; }`.               |
| Dotenv    | Carrega variáveis de ambiente de um arquivo `.env` para `process.env`.              | Definir `PORT=3000` em `.env` e acessar com `process.env.PORT`.                     |
| Nodemon   | Reinicia automaticamente o servidor ao detectar mudanças nos arquivos.              | Executar `nodemon app.js` para desenvolvimento sem precisar reiniciar manualmente.  |
| Jest      | Framework de testes em JavaScript para garantir a correção do código.               | Criar um teste: `test('soma 2+2', () => { expect(2+2).toBe(4); });`.                |
| Socket.io | Permite comunicação em tempo real e bidirecional entre cliente e servidor.          | Implementar chat em tempo real entre usuários conectados ao servidor Node.js.       |

## Versionamento no NPM  
O NPM permite gerenciar versões de pacotes. Isso é importante quando você deseja garantir que uma versão específica de uma biblioteca seja usada em todos os ambientes.

Instalar uma Versão Específica  
Para instalar uma versão específica de um pacote, use:
``` bash
npm install <nome-do-pacote>@<versão>
```

Por exemplo:
``` bash
npm install express@4.18.2
```
Isso instalará a versão 4.17.1 do Express, independentemente da versão mais recente.

## Utilizando Versionamento Semântico para gerenciar pacotes

- Para instalar uma versão específica, especifique a versão exata no package.json (por exemplo: `"express": "4.1.1"`).
- Para instalar a versão mais recente, use `"*"` ou `"latest"` como versão.
- Para instalar uma versão compatível acima de uma versão dada, use o acento circunflexo (^), por exemplo: `"express": "^4.1.1"`, o que instala uma versão mais nova compatível (mesma versão principal).

## Dependências vs DevDependencies

Dependências (Dependencies)
Necessárias para executar a aplicação em produção.
Essenciais para que o app funcione corretamente.
Exemplos: express, mongoose, lodash, react, axios.
Instaladas com npm install `<package>`.
Incluídas ao rodar npm install --production.

DevDependencies
Necessárias apenas durante o desenvolvimento.
Usadas para ferramentas de desenvolvimento, testes, linting e empacotamento.
Exemplos: nodemon, eslint, jest, mocha, webpack, babel.
Instaladas com npm install `<package>` --save-dev (ou -D).
Ignoradas ao rodar npm install --production.

