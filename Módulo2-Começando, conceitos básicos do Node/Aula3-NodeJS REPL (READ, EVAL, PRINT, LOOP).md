O REPL do NodeJS (Read-Eval-Print Loop) é um shell interativo que permite executar código JavaScript linha por linha e ver os resultados imediatamente. Essa ferramenta é extremamente útil para testes rápidos, depuração e aprendizado, fornecendo um ambiente isolado onde você pode experimentar código JavaScript dentro do NodeJS.

READ (Ler): Você digita algum código JavaScript no terminal, e o REPL lê o que você digitou.
EVAL (Avaliar): O REPL executa (avalia) o seu código.
PRINT (Imprimir): O REPL mostra o resultado do seu código.
LOOP (Loop): O REPL volta ao passo 1, aguardando você digitar mais código. Esse ciclo continua até você sair do REPL.

## Primeiros passos com o REPL

Para começar a trabalhar com o ambiente REPL do NodeJS, siga um destes dois métodos:
Iniciando o REPL no Terminal ou Prompt de Comando
Abra o seu terminal (para UNIX/Linux) ou o Prompt de Comando (para Windows).
Digite node e pressione Enter para iniciar o REPL.

``` bash
node
```

> C:\Users\Parikshit\Desktop\GeeksForGeeks>node
(Para sair, pressione ^C novamente ou digite .exit)

O REPL foi iniciado e é demarcado pelo símbolo >.
Diversas operações podem ser realizadas dentro do REPL.
Abaixo estão alguns exemplos para você se familiarizar com o ambiente do REPL.


## Recursos do REPL do NodeJS

Os recursos do REPL do NodeJS são discutidos abaixo:

1.Executando código JavaScript  
O REPL é um ambiente JavaScript completo, o que significa que você pode executar qualquer código JavaScript válido dentro dele.
Exemplo:
``` js
> const x = 10;
> const y = 20;
> x + y
30
```

Você pode declarar variáveis, criar funções e executar qualquer código que funcionaria em um ambiente normal de execução do JavaScript.



2.Entrada Multilinha  
No caso de lógicas mais complexas (como laços ou funções), o REPL suporta entrada em múltiplas linhas.
Quando você digita um bloco de código, o REPL continua lendo a entrada até que o bloco esteja completo.
Exemplo:
``` js
> function add(a, b) {
...   return a + b;
... }
> add(5, 10)
15
```

Aqui, o REPL espera você concluir o bloco da função antes de avaliar o código.


3.Variável Underscore ( )  
O REPL fornece uma variável especial chamada  (underscore) que armazena o resultado da última expressão avaliada.
Exemplo:
``` js
> 3 + 3
6
> _ * 2
12
```

Nesse caso, o resultado de 3 + 3 é armazenado em , que depois é usado na linha seguinte para calcular 12.


4.Salvando e Carregando Sessões do REPL  
O REPL permite salvar a saída da sessão em um arquivo e carregar sessões previamente salvas, facilitando o acompanhamento do código que você já testou.
Salvar uma sessão: Para salvar sua sessão do REPL em um arquivo, use o comando .save:
``` js
> .save ./repl_session.js
```

Carregar uma sessão: Você pode carregar a sessão salva em uma nova sessão do REPL usando o comando .load:
``` js
> .load ./repl_session.js
```


5.Acessando Módulos Principais do NodeJS  
O ambiente REPL permite carregar e usar os módulos principais do NodeJS, como fs, path, http, etc., sem precisar sair do REPL ou escrever um script completo.
Exemplo:
``` js
> const fs = require('fs');
> fs.readFileSync('test.txt', 'utf8');
```

O módulo fs (file system) é carregado, e o REPL lê o conteúdo de um arquivo chamado test.txt.


6.Tratamento de Erros no REPL  
O REPL é tolerante a erros e exibirá mensagens de erro úteis sem encerrar toda a sessão. Isso o torna um ambiente seguro para testes.
Exemplo:
``` js
> console.log(foo);
ReferenceError: foo is not defined
```

Nesse caso, o REPL informa claramente que a variável foo não está definida, mas continua funcionando normalmente.


## Comandos Internos do REPL
O REPL do NodeJS fornece vários comandos internos (os comandos do REPL sempre começam com um ponto .):
.help: Exibe uma lista de todos os comandos disponíveis no REPL.
.break: Interrompe a entrada multilinha ou limpa a entrada atual.
.clear: Redefine o contexto do REPL, limpando todas as variáveis declaradas.
.exit: Encerra a sessão do REPL.

Operações aritméticas em REPL
``` bash
C:\Users\Parikshit\Desktop\GeeksForGeeks>node
> 10+20
30
> 1-2
-1
> 10/4
2.5
> 10%3
1
```


Operações usando bibliotecas do NODE
``` bash
C:\Users\Parikshit\Desktop\GeeksForGeeks>node
> Math.ceil(10/3)
4
> Math.floor(10/3)
3
> math.round(math.e, 3);
ReferenceError: math is not defined
> Math.round(Math.e, 3)
NaN
> Math.round(2.57362, 3)
3
> Math.sqrt(16)
4
> Math.pow(3, 4)
81
(To exit, press ^C again or type .exit)
>
C:\Users\Parikshit\Desktop\GeeksForGeeks>node
```

Observação: Usar 'math' resulta em erro, pois a biblioteca é referenciada como 'Math' no NODE e não como 'math'.


Usando variáveis no REPL
A palavra-chave var
``` bash
> var a = 4;
undefined
> a
4
> var c = "GeeksForGeeks"
undefined
> c
'GeeksForGeeks'
```


Usando laços (loops) no REPL
Os loops podem ser usados no REPL da mesma forma que em outros editores.

``` bash
for (var i = 1; i <= 5; i++) {
    console.log('GeeksforGeeks');
}

GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
undefined
```

Nota: Use Ctrl + C para interromper o comando e Ctrl + C duas vezes para encerrar o NODE REPL.

.help é usado para listar todos os comandos.
```
C:\Users\Parikshit\Desktop\GeeksForGeeks>node
> .help
.break    Sometimes you get stuck, this gets you out
.clear    Alias for .break
.editor   Enter editor mode
.exit     Exit the repl
.help     Print this help message
.load     Load JS from a file into the REPL session
.save     Save all evaluated commands in this REPL session to a file
>
```


