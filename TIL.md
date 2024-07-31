# **2024-07-13**
## Como mudar de pasta (Terminal)
Quando for necessário salvar os arquivos em outro local.
Primeiro verificar em qual pasta está atualmente: ``git status``
Verificado o local, para mover para uma pasta anterior, basta digitar ``cd ..``
Repita o comando caso a pasta desejada seja anterior a atual.
Para confirmar a pasta, digitar ``cd`` + ``NOME DA PASTA``

## Como criar um novo repositório
Para crirar um novo repositório, é necessário que seja criado tanto no Github quanto através do Git. 
### No Github
Em "My repositories" clicar em ``New``
Atribuir um nome ao repositório
Concluir a ação
. 

### No Git
Se uma pasta foi criada localmente, é preciso que ela seja selecionada

No Terminal, digiar git init + enter 

Commitar na nova pasta

Copiar do Github os comandos em "…or push an existing repository from the command line" e colar no Terminal.

## Como criar uma nova branch
Primeiro git push → “git push -u origin NOME DA BRANCH”
“-u” : abreviação de set upstream (para qual branch vai)
Importante quando é um projeto envolvendo outras pessoas, para ter uma versão consigo sem afetar a main, acesse o Terminal e digie ``git checkout -b [NOME DA BRANCJ]`` 

## Utilizar variáveis em SCSS 
São úteis em funções, quando não há um valor cravado, mas sim um valor que pode ser diferente dependendo da condição. 
As variáveis têm sintaxe de ```$ NOME DA VARIÁVEL`` 
**IMPORTANTE:** a variável precisa ser NOMEADA primeiro, é imporante a ordem dos fatores, então no início do código, ela precisa já estar definida para ser reconhecida. 

## Função calculate-percentage 
Essa é uma função para calcular em porcentagem , a exemplo da prática, consta no projeto desafio-grid 

@function calculate-percentage($variável) {
  @return % / $variável;
}

Basicamente, foi definida a função a ser utilizada (calculate-percentage) e qual valor será utilizado, a variável "ncolunas" (número de colunas, que a ideia é mudar a quantidade de colunas conforme o tamanho da página) 

## Include e Mixin 
O mixin é como um bloco de código reutilizável, ele permite que o código fique menos repetitivo, com um visual mais clean 
As includes são como exceções, alguns acréscimos de código ao mixin (como uma condição E, somada ao que foi descrito no mixin). Obrigatoriamente para haver um include, um mixin deve ser escrito. 

## Media qwery 
É a forma de se trabalhar com breakpoints. Com o media qwery, é possível definir qual resposta será do conteúdo de acordo com o tamanho da tela. No projeto de grid, foi utilizado: 

  ``@media (max-width: 1000px) {
    @include tamanhotela(3);
  }

  @media (max-width: 800px) {
    @include tamanhotela(2);
  }

  @media (max-width: 600px) {
    @include tamanhotela(1);
  }
}``

O ``@media`` se repetiu pois a cada um dos cenários (breakpoints) foi definido quantas colunas haveriam na visualização de acordo com o seu tamanho em px.

## Display grid
É uma forma de "organização" do conteúdo na página web no SCSS. Ela basicamente divide a tela como em uma forma de grade, em que o conteúdo fica dividido entre esses espaços: 
![exemplo de grid](https://www.freecodecamp.org/news/content/images/2022/05/CSS-GRID-3.png)

# **2024-07-18**
Asterisco (*) é o seletor universal do CSS.
``* {
    box-sizing: border-box;
    margin;0;
    padding: 0;
    }``

O underline na frente do nome do arquivo, não o renderiza. Ex.: "_variables.scss"

Utilizar o ``@import`` no SCSS possibilita dividir o código em pastas. Então por exemplo, é possível com o import, criar uma pasta somente com variáveis e importar as definições para a pasta main de estilização. 

## Utilizando Webpack
Para visualizar, é preciso iniciar o webpack, para que sejam importadas as configurações. para isso: ``npm  run start`` (no terminal)  

Atenção à linha: ``<i> [webpack-dev-server] Loopback: VER O LOCAL HOST E ACESSAR O LINK``

# **2024-07-21**
## Utilizando o Git Pull
O Git Pull, ao contrário do GIT PUSH, é para pegar o código atualizado do github

OU SEJA : enquanto o Git Push exporta da máquina para o github, o Git Pull importa a main do github para a máquina

### Como usar
``git pull origin main``

## Iniciar o sass 
Em um novo projeto, utilizando o Sass, é preciso iniciá-lo no Terminal com o comando ``sass --watch styles/main.scss:styles/styles.css``

Para isso, certifique-se que o local da pasta está correto. Deve ser o mesmo do projeto!

No arquivo html, deve estar referenciado no head: ``<link rel="stylesheet" href="styles.css" />``

O comando ``sass --watch`` deverá conter o caminho da pasta input e output, divididas por :! 

# **2024-07-25**
## Aula JavaScript
**linguagem interpretada:** interpretar a linguagem, transformá-la a uma linguagem mais próxima de uma linguagem de máquina

**linguagem compilada:** interpretação baixo nível
js roda em browser, navegadores web, o que muda é o compilador- V8: chrome e node.js (ambientes diferentes que usam V8, o mesmo compilador)

**node.js:** é um compilador javascript, é uma plataforma que permite a execução de javascript via servidor

**V8:** biblioteca criada pela google 

**parsing e compilação:**

**call stack:** pilha de chamados, todo processamento é feito por essa call stack - como o js funciona

**LIFO (Last In, First Out):** é o termo na programação, em que significa último a entrar/primeiro a sair. 
imagina uma pilha de cadernos pra uma professora corrigir. O último a  colocar o caderno na pilha é o primeiro caderno que vai ser corrigido.
existem métodos para executar e gerenciar: LIFO é um deles

stack executa uma ação por vez, o js precisa gerenciar isso, pra isso serve a call stack

**Síncrono** é quando você espera pelo sanduíche até que ele esteja pronto. Você fica parado, olhando para a sua mãe fazer o sanduíche, e não faz nada mais até que ela termine e te dê o sanduíche. Só depois disso você vai comer.

**Assíncrono** é quando você pede o sanduíche e vai brincar enquanto sua mãe faz o sanduíche. Você pode brincar, assistir TV ou fazer qualquer outra coisa. Quando o sanduíche estiver pronto, sua mãe chama você e aí sim você vai comer.

JS é single-threaded, mas usa o conceito de event loop, 
**thread:** tem um fluxo de execução único, só consigo fazer uma coisa por vez 

**non blocking I/O**

**visualização do que seria uma call stack:** http://latentflip.com/loupe/?code=JC5vbignYnV0dG9uJywgJ2NsaWNrJywgZnVuY3Rpb24gb25DbGljaygpIHsKICAgIHNldFRpbWVvdXQoZnVuY3Rpb24gdGltZXIoKSB7CiAgICAgICAgY29uc29sZS5sb2coJ1lvdSBjbGlja2VkIHRoZSBidXR0b24hJyk7ICAgIAogICAgfSwgMjAwMCk7Cn0pOwoKY29uc29sZS5sb2coIkhpISIpOwoKc2V0VGltZW91dChmdW5jdGlvbiB0aW1lb3V0KCkgewogICAgY29uc29sZS5sb2coIkNsaWNrIHRoZSBidXR0b24hIik7Cn0sIDUwMDApOwoKY29uc29sZS5sb2coIldlbGNvbWUgdG8gbG91cGUuIik7!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D

**call-back queue:** assíncronas (requisição com um tempo para ser feita) - ele não é do js! bloqueia call stack 
libuv - linguagem mãe do js, de baixo nível, quem determina o que foi resolvido ou não, faz um gerenciamento, converte o código em c
1) vai para o web apis (síncrono) 

2) callback queue

callstack -> via api do browser vai para o aps

js leva para o C++ transformar em um código de baixo nível

**arrays:** listas ordenadas de valores, na programação tudo começa por 0! [1,2,3,4] -> o 1 está na posição 0, 2 na posição 1....

**STRINGS:** 'valor da variável, um texto' 

criar variável

1) usar "var" (palavra reservada)
   ex: var aluno = "Yumi" -> Yumi é uma string 
   
2) usar "let"

ex: let aluno2 = "leila"
mesma forma de declarar uma variável. o problema do var é de ignorar o escopo. NÃO DEVE SER UTILIZADO

o let deve ser utilizado "let me change", deixe-me mudar.

3) const

ex: const aluno3 = "kato" 

console.log(aluno, aluno3)

o const é constante, então recebe o valor atribuído na primeira linha 

ex.: 
let name = "Daniel" 
let lastName = "Gomes" 
let nomeCompleto = ${name} ${lastName}  -> para deixar as palavras separadas por espaço 

resultado (node dados) -> Daniel Gomes

números ficam representados com cor diferente, mas precisam estar sem nada como aspas (para entender como número e não como texto)

PHP: pesquisar, para entender javascript

# **2024-07-28** 
## **Boas práticas para commitar** 
### **Tipo**
build: Related to build process changes;
ci: Related to continuous integration setup changes;
chore: About build process or auxiliary tool changes;
docs: Limited to documentation changes;
feat: Introducing new features;
fix: Addressing bug fixes;
perf: Enhancing code performance;
refactor: Code changes without bug fixes or new features;
revert: Reverting previous changes;
style: Markup, formatting, or whitespace changes;
test: Adding missing tests.

### **Conteúdo opcional**
ele fica entre parênteses, logo após o tipo. Ex.: feat(parser): add the ability to parse arrays

### **Assunto**
deve ser conciso, evite escrever "mudanças", "alterações". uma boa prática é utilizar o presente e imperativo (e preferencialmente em inglês): "change"
evite terminar a linha do assunto com um ponto final

### **Corpo|Body**
É opcional, bem semelhante ao assunto (subject). Manter a forma imperativa e conjugação no presente. O body explica a motivação por trás da mudança e destaca quaisquer contrastes notáveis com o comportamento anterior. 

## **Regras básicas**
Limite a linha de assunto a no máximo 50 caracteres;
Comece a linha de assunto com uma letra minúscula e use o presente;
Utilize o corpo para explicar “o quê” e “porquê” das mudanças, em vez de “como”.

**Exemplos de commit** 
``fix(filter): change filtration logic``
``feat(authentication): Add Google auth``

# **2024-07-30**
## Tipos de dados
### Boolean
Retorna true or false 
- thruthy and falsy no JS 
Falsy: valor falsy é algo que foi avaliado como false
ex.: 0, false, undefined, null, "" (string vazia), NaN (Not a Number), 0n, -0  
Truthy: 

Colocar uma ! antes da variável, é negar. Fazer uma negação do valor 
  ``console.log(!0)`` 
  Quero que retorne o valor booleano dessa variável, mas me negando ela
    ``console.log(!!0)`` 
  Negando a negação -> retorna como verdadeiro (true) 

  ### Undefined e Null
    ``let contador;``
  ``node [PASTA]``
  ``console.log(typeof contador == 'undefined')`` 
  Criei uma variável e vai me retornar como ``undefined``, que aparece quando uma variável não é definida
  Os dois "=" verifica somente o valor 
  Três "=" verifica o valor e o tipo
  Então: 
  ``console.log(6 === '6')`` vai retornar no node como FALSE
  É preferível utilizar o **estritamente** igual, que são os 3 =

  ``let carro = null;`` 
  ``console.log(carro)`` 

O Null é para quando quer retornar uma informação ao usuário, mas que não tem um valor para a variável para ser definida.  
É mais semântico do que undefined, pois indica que não tem um valor. No caso do undefined, indica que você simplemente não definiu nada. 

### Object
O objeto é uma coleção/dicionário de dados definida baseada em chave e valor. 
  ``const usuario = {
  [key/propriedade/chave]: value
  }``

Assim se cria um objeto literal: 
  ``const usuario = {
  nome: "Yumi"
  }``
Objeto literal é aquele que é escrito na raça 

"Nome" é uma propriedade ou chave, "Yumi" é o valor dessa chave/propriedade

``console.log(usuario)`` (no código) + node [PASTA] = { nome: 'Yumi'} 

``console.log(usuario.nome)`` o ponto serve quando quero listar todas as propriedades desse objeto (no caso retorna com ``string`` - no node)  . listar a propriedade que quer acessar

**Objetos alinhados** 
``idade: 26
nome: Yumi``

``console.log(usuario.idade)``
``console.log(usuario.nome)``
Retorna: ``26
Yumi``

### Array
É um vetor, um agrupador de dados (forma uma lista)
``const listaDeCompras = []``
Para criar um array, a sintaxe é colchetes
``console.log(typeof listaDeCompras)``
Vai retornar como um object: **Tudo no JS é um objeto**
``console.log(Array.isArray(listaDeCompras))`` 
Dentro do parênteses, o "Array" é uma classe, já indicando o tipo, e em seguida ".isArray" é uma função, em que dentro do 2º parênteses é para falar qual variável é

``const listaDeCompras = [
'banana',
'maçã',
'arroz',
'frango'
]``

Ele vai retornar do node: [ 'banana', 'maçã', 'arroz', 'frango']
No JS, um array pode ser uma lisa de qualquer coisa, qualquer tipod e dado. Pode colocar vários dados dentro de uma lista, incluindo textos e números. Existe essa flexibilidade de colocar qualquer tipo de valor (ex. {valor: true}, 10) 

``console.log(listaDeCompras.length)`` 
O length é uma variável, ele em específico serve para contar quantos itens tenho na lista array (Capturo o tamanho do array)

``console.log(listaDeCompras[0])`` 
Isso serve para identificar qual a posição 

Para definir qual posição é o último item do array: ``console.log(listadeCompras[listaDeCompras.length - 1])`` 

### Function
É criada para executar uma tarefa
**Function Expression (named function/função nomeada)**
``function lavarLouça(){
  const prato = ' ' 
}
``
O escopo de uma função existe só dentro da função! (Por isso que se rodar o que estiver acima, vai dar um erro.

Esqueleto da function: escrevo function, nomeio a função e parênteses para definir os parâmetros/argumentos, as chaves são para colocar o escopo

``function lavarLouça(prato){
  console.log(prato) 
}
``
``console.log(lavarLouca())`` -> undefined 
função pode ser anônima se escrita assim: ``function ()`` 

**Anonymous Function** 
``verificaSeEhMaiorDeIdade: function () {
return usuario.idade >= 18
}
log: () = >

console.log(usuario.log())

**Arrow function**

Próxima: loops, condicionais

**INDICAÇÕES** 
- "Entendendo algoritmos: Um Guia Ilustrado Para Programadores e Outros Curiosos"




  

  

  
  

