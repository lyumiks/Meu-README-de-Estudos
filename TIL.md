# **2024-07-13**
## Como mudar de pasta (Terminal)
Quando for necessário salvar os arquivos em outro local.
Primeiro verificar em qual pasta está atualmente: ``git status``
Verificado o local, para mover para uma pasta anterior, basta digitar ``cd ..``
Repita o comando caso a pasta desejada seja anterior a atual.
Para confirmar a pasta, digitar ``cd`` + ``NOME DA PASTA``

## Como criar um novo repositório
Para crirar um novo repositório, é necessário que seja criado tanto no Github quanto atravpes do Git. 
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

