
# CSS Flexbox Parte 1

## - O que vamos aprender?

Você irá aprender a propriedade Flexbox do CSS.

Uma das preocupações que acompanham o dia a dia de qualquer pessoa desenvolvedora, é a famosa **Responsividade**.

Somando a isso, há também todas as complexidades de ajustar aquela pequena área do site que você está criando, utilizando propriedades como: 
* float
* position 
* display inline 
* display block 

E depois disso ~torcendo~ calculando para que ao diminuir a janela do navegador, o site continue com os elementos organizados na tela.

Felizmente, hoje você iniciará seus estudos na propriedade que irá facilitar esse trabalho, o CSS Flexbox.

## Você será capaz de:

* Posicionar os elementos do seu site utilizando a propriedade flexbox.

* Tornar seu site responsivo.

## Porque isso é importante?

O acesso aos sites que você criará na sua carreira como pessoa desenvolvedora, certamente será acessado não apenas através de um computador, mas também por tablets, celulares e até TV's. 

Por isso, o cuidado para tornar os sites que você criará a partir desse momento, em sites mais dinâmicos e flexíveis, serão constantes. 

E é através do Flebox que conseguiremos esse resultado de maneira mais fácil.

# Conteúdos

## Introdução

Aprender sobre Flexbox é uma tarefa tão divertida quanto trabalhosa, por isso dividiremos esse assunto em duas partes.

### Parte 1

Você aprenderá como aplicar a propriedade Flexbox aos containers, tornando-os Flex Containers, e é essa parte que veremos hoje com mais profundidade.

### Parte 2

Nesse momento você aprenderá como utilizar o Flexbox aos elementos que estão dentro de um Flex Container, também conhecidos como Flex Items, e veremos esse assunto na próxima aula.

## Introdução

O primeiro passo para tornar o seu elemento em um Flex Container, podendo a partir de então trabalhar com suas propriedades flex, é o:

```
#id-elemento {
  display: flex;
}
```

A partir de agora, você poderá utilizar algumas propriedades exclusivas de um flex container, e veremos 3 destas a seguir: `flex-direction`, `flex-wrap` e `flex-flow:` 

Mas para entender como serão utilizadas, você precisará compreender como são posicionados elementos(Flex Items) dentro de um Flex Container.

O posicionamento desses itens é definido de acordo com a direção do eixo principal (main axis) e do eixo cruzado (cross axis).

Por padrão, o eixo principal é definido como sendo horizontal, enquanto o eixo cruzado como sendo vertical.

Nessa imagem você pode entender um pouco melhor essa abstração:

![flexbox_axis.jpg](https://www.imagemhost.com.br/images/2021/05/02/flexbox_axis.jpg)

Vale lembrar, que este é o comportamento padrão, porém podemos alterar a orientação de um eixo principal, e você verá como isso é feito logo a seguir.

## Flex direction, flex wrap e flex flow

A propriedade que define o direcionamento de um eixo principal, é o `flex-direction`.

Mas nada como a boa e velha prática para que você possa entender melhor como isso funciona e conhecer os principais valores de flex directions.

copie o código.
``` 
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flexbox</title>
  <style>
    #flex-container {
      display: flex;
      /* Alterne o flex-direction para column, column-reverse e row-reverse; */
      flex-direction: row;
      width: 1000px;
      height: 500px;
      background-color: rgb(24, 92, 24);
    }

    #flex-item1 {
      width: 100px;
      height: 100px;
      border: 1px solid black;
      background-color: rgb(120, 7, 124);
    }

    #flex-item2 {
      width: 100px;
      height: 100px;
      border: 1px solid black;
      background-color: cadetblue;
    }

    #flex-item3 {
      width: 100px;
      height: 100px;
      border: 1px solid black;
      background-color: darkgoldenrod;
    }

    #flex-item4 {
      width: 100px;
      height: 100px;
      border: 1px solid black;
      background-color: rgb(24, 3, 212);
    }

  </style>
</head>
<body>
  <div id="flex-container">
    <div id="flex-item1">1</div>
    <div id="flex-item2">2</div>
    <div id="flex-item3">3</div>
    <div id="flex-item4">4</div>
  </div>
</body>
</html>
```

Agora alterne no código, o elemento flex-direction como descrito abaixo para que você veja no seu navegador a diferença do posicionamento dos itens.

```
flex-direction: row; // Main Axis na horizontal - itens ficam um ao lado do outro.
flex-direction: column; // Main Axis na vertical - itens abaixo um do outro.
```

Outra propriedade que interfere no posicionamento dos itens é a flex-wrap.

Através dessa propriedade, você pode definir o que estes elementos dentro de um flex container, farão ao atingir o limite de seu container. Se você quiser que os elementos ajustem seu tamanho para que todos eles caibam em uma só linha, use `flex-wrap: nowrap`, mas se você preferir que estes elementos não modifiquem seu tamanho original e ao atingir a borda do container, pulem para outra linha, basta adicionar a propriedade `flex-wrap: wrap`. Por padrão, essa propriedade está configurada como *nowrap*. 

Para melhor visualização, vamos para o vscode novamente:

Copie o código:
``` 
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    #flex-container {
      display: flex;
      /* Alterne o flex-wrap para wrap e depois para wrap-reverse; */
      flex-wrap: nowrap;
      width: 1000px;
      height: 200px;
      background-color: rgb(121, 39, 7);
    }

    .flex-item {
      width: 150px;
      height: 90px;
      border: 1px solid black;
      background-color: rgb(126, 123, 113);
    }
    
  </style>
</head>
<body>
  <div id="flex-container">
    <div class="flex-item">1</div>
    <div class="flex-item">2</div>
    <div class="flex-item">3</div>
    <div class="flex-item">4</div>
    <div class="flex-item">5</div>
    <div class="flex-item">6</div>
    <div class="flex-item">7</div>
    <div class="flex-item">8</div>
    <div class="flex-item">9</div>
  </div>
</body>
</html>
```

Por último, temos a propriedade flex-flow.

Esta propriedade nada mais é do que a junção das propriedades flex-direction e flex-wrap em uma só.

```
flex-flow: row nowrap; //(padrão) - podemos usar as combinações como aprendemos antes como por exemplo: flex-flow: column wrap;
```

Experimente substituir nos códigos anteriores as pripriedades flex-direction e flex-wrap por flex-flow, e faça a mágica acontecer.

## Justify content, align items e align content

E agora que você aprendeu a manipular um **main axis** de um **flex container**, está na hora de aprender a alinhar itens dentro deste container.

Para isso você verá 3 propriedades:

* justify-content:
* align-itens:
* align-content:

A primeira propriedade é `justify-content`, ela é utilizada para alinhar itens do **eixo principal** veja abaixo alguns de seus possíveis valores e comportamentos.

[![justify-content.jpg](https://i.postimg.cc/NjNt50RY/justify-content.jpg)](https://postimg.cc/QFWwzh6n)

Já `align-items` é utilizada para alinhar os itens do **eixo cruzado**.

[![align-itens.jpg](https://i.postimg.cc/KYTRLVF0/align-itens.jpg)](https://postimg.cc/xk0fV6Xm)

Enquanto `align-content` você só irá utilizar quando possuímr mais de uma linha em seu **eixo principal**.

[![align-content.jpg](https://i.postimg.cc/HnHk1sqM/align-content.jpg)](https://postimg.cc/gXSWvdkc)

```
justify-content: flex-start; // padrão
align-items: stretch; // padrão
align-content: stretch; // padrão
```

Lembrando que todas estas propriedades, se ajustam de acordo com a posição do eixo principal e cruzado.

Agora, para exercitar o seu aprendizado, copie o código abaixo e vamos mais uma vez ver o funcionamento na prática:

```
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    #flex-container {
      display: flex;
      /* abaixo, o alinhamento do eixo principal, teste as propriedades que você aprendeu */
      justify-content: flex-start;
      /* abaixo, o alinhamento do eixo cruzado, teste as propriedades que você aprendeu*/ 
      align-items: stretch;
      /* abaixo, o alinhamento das filas de itens, quando houver mais de uma ao eixo principal  */
      align-content: stretch;
      width: 80%;
      height: 500px;
      background-color: rgb(16, 5, 66);
    }

    .flex-item {
      width: 150px;
      border: 1px solid black;
      background-color: rgb(104, 82, 9);
    }
    
  </style>
</head>
<body>
  <div id="flex-container">
    <div class="flex-item">1</div>
    <div class="flex-item">2</div>
    <div class="flex-item">3</div>
    <div class="flex-item">4</div>
    <div class="flex-item">5</div>
    
  </div>
</body>
</html>
```

Esse novo aprendizado abre muitos horizontes para seus novos projetos e até mesmo para os antigos, experimente reorganizar os elementos do seu último projeto utilizando as facilidades que você aprendeu com CSS Flexbox.

Agora vamos praticar!

## Exercícios

CHegou a hora de você exercitar os conhecimentos em CSS Flexbox.

### Antes de começar: versionando seu código

Para versionar seu código, utilize o seu repositório de exercícios.

Caso você ainda não tenha um, crie um repositório com o nome Trybe ou algo similar.

Abaixo você vai ver exemplos de como organizar cada exercício em uma branch, com arquivos e commits específicos para cada exercício. Você deve seguir este padrão para realizar os exercícios a seguir.

1. Crie uma branch com o nome exercises/css-flexbox-parte1:

`git checkout -b exercises/css-flexbox-parte1`

2. Crie um diretório exercises e, dentro dele, um diretório css-flexbox-parte1. O caminho completo para o diretório a partir da raiz do projeto deverá ser `exercises/css-flexbox-parte1`.

```
mkdir -p exercises/css-flexbox-parte1
cd exercises/css-flexbox-parte1
pwd
<path_to_your_repo>/exercises/css-flexbox-parte1
```
3. Crie um arquivo com um nome descritivo para cada exercício. Os arquivos devem estar dentro da pasta exercises/css-flexbox-parte1, mas lembre-se de fazer os commits a partir da pasta raiz do seu projeto!

```
git status
On branch exercises/css-flexbox-parte1
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

  modified:   exercise_1.html
  ```
4. Faça commits organizados durante o processo de resolução de cada um de seus exercícios. As mensagens dos commits devem ser breves e explicativas.

```
git log
commit 100d4c10d64e2b8443f43edf3be13588a77b8fa4 (HEAD -> exercises/css-flexbox-parte1)
Author: Tryber Bot <tryberbot@betrybe.com>
Date:   Fry Sep 27 17:48:01 2019 -0300

    Exercício 1 - adicionei display: flex ao elemento header

commit c0701d91274c2ac8a29b9a7fbe4302accacf3c78
Author: Tryber Bot <tryberbot@betrybe.com>
Date:   Fry Sep 27 16:47:21 2019 -0300

    Exercicio 1 - centraliza os elementos dentro da div header
```

5. Lembre-se que na primeira vez que você for enviar o código para o repositório remoto a branch exercises/css-flexbox-parte1 não vai existir lá.
Então você precisa configurar o remote utilizando a opção --set-upstream (ou -u, que é a forma abreviada).

`git push -u origin exercises/css-flexbox-parte1`

6. Lembre-se de enviar os commits para o repositório do GitHub.
  
`git push origin exercises/css-flexbox-parte1`  
  
7. Quando terminar os exercícios, seus códigos devem estar todos commitados na branch exercises/css-flexbox-parte1, e disponíveis no repositório remoto do GitHub.
Pra finalizar, crie um Pull Request , adicione uma descrição bem bacana, e envie para a monitoria e/ou colegas revisarem! 🤜🏼🤛🏼

### TrybeBook

Hoje você irá montar o cabeçalho de uma rede social chamada Trybebook. Segue abaixo uma imagem exemplo de como deve ficar ao final dos exercícios.

[![Screenshot-from-2021-05-03-13-49-09.png](https://i.postimg.cc/6qVzZfT3/Screenshot-from-2021-05-03-13-49-09.png)](https://postimg.cc/wRvh8JX8)

Para começar a desenvolver, copie o código abaixo:

```
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Exercícios Flexbox</title>
  <style>
    body {
      margin: 0 auto;
    }

    header { 
      width: 100%;
      background-color: rgb(4, 153, 153);
      padding: 10px 0;
      /* Exercício 1 - Adicione o código abaixo */
      
    }

    .title-content {
      /* Exercício 2 - Adicione o código abaixo */
      
    }

    #search-input {
      padding: 6px;
      border-radius: 5px;
    }

    .search-panel {
      display: flex;
      /* Exercício 3 - Adicione o código abaixo */
      
    }
    
    .nav-main {
      /* Exercício 4 - Adicione o código abaixo */
      
    }

    .nav-main div {
      display: flex;
      font-size: 13px;
      margin: 0 10px;
      width: 100px;
      height: 100px;
      border: 1px solid black;
      border-radius: 10px;
      background-color: rgb(153, 116, 151);
    }

    .icons {
      /* Exercício 5 - Adicione o código abaixo */
      
    }

    .nav-profile {
      width: 300px;
    }
  
    .personal{
      /* Exercício 6 - Adicione o código abaixo */
      
    }

    .nav-user {
      /* Exercício 7 - Adicione o código abaixo */
      
    }


  </style>
</head>
<body>

  <header class="header">
    <section class="title-content">
      <div id="title">
        <h1>TRYBEBOOK</h1>
      </div>
      <div class="search-panel">
        <img id="logo" src="https://img.icons8.com/ios-filled/50/26e07f/y-combinator.png"/>
        <input id="search-input" placeholder="Pesquise aqui!">
      </div>
    </section>

    <section class="nav-main">
      <div class="icons">
        <p>Página Inicial</p>
        <img src="https://img.icons8.com/pastel-glyph/50/000000/browser-homepage--v2.png"/>
      </div>
      <div class="icons">
        <p>Vídeos</p>
        <img src="https://img.icons8.com/dotty/50/000000/movies-folder--v1.png"/>
      </div>
      <div class="icons">
        <p>Grupos</p>
        <img src="https://img.icons8.com/pastel-glyph/50/000000/groups--v4.png"/>
      </div>
      <div class="icons">
        <p>Jogos</p>
        <img src="https://img.icons8.com/ios/50/000000/footman.png"/>
      </div>
    </section>

    <section class="nav-profile">
      <section class="personal">
        <img id="user-image" src="https://img.icons8.com/material-sharp/59/26e07f/user-male-circle.png"/>
        <div>Nome do usuário</div>
      </section>
      <section class="nav-user">
        <img id="user-menu" src="https://img.icons8.com/fluent-systems-filled/40/000000/top-menu.png"/>
        <img id="user-notifications" src="https://img.icons8.com/material-rounded/40/000000/bell--v1.png"/>
        <img id="user-settings" src="https://img.icons8.com/windows/40/000000/user-settings.png"/>
      </section>
    </section>
  </header>
  <section>
    <p>Todos os ícones foram retirados do site <a href="https://icons8.com.br/" target="_blank">icons8</a></p>
    <p>Um excelente site com milhares de ícones gratuitos que você pode usar no desenvolvimento dos seus projetos</p>
  </section>
</body>
</html>
```

#### Exercício 1

Analisando o código acima, você perceberá que o elemento `header` possui 3 elementos filhos, organize-os de maneira a ficarem em uma só linha horizontal, e que tenha os espaçamentos como mostra a imagem de exemplo.

#### Exercício 2

Agora, faça com que o elemento de classe `title-content` se alinhem como na imagem. (Lembre-se do alinhamento horizontal e vertical)

#### Exercício 3

No elemento de classe `search-panel`, posicione os itens que existem dentro dele.

#### Exercício 4

Nos ícones de centro, que possuem a classe `nav-main`, determine a direção correta destes itens, posicionando-os como na imagem de exemplo.

#### Exercício 5

Dentro da tag de classe `nav-profile`, os itens estão organizados de maneira a não ocuparem todo o espaço do container de maneira correta, organize esses elementos internos para que eles fiquem como na imagem.

#### Exercício 6

Já na classe `personal`, temos itens que não seguem o alinhamento da imagem de exemplo, organize de maneira que se pareça com a imagem que você viu acima.

#### Exercício 7

E em `nav-user`, precisamos organizar todos os ícones como mostra a imagem. 


## Gabarito de Exercícios

Segue a solução para os exercícios propostos:
As repostas para cada questão, estão comentadas no código abaixo.

```
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Exercícios Flexbox</title>
  <style>
    body {
      margin: 0 auto;
    }

    header { 
      width: 100%;
      background-color: rgb(4, 153, 153);
      padding: 10px 0;
      /* Exercício 1 */
      display: flex;
      justify-content: space-around;
      align-items: flex-end;
    }

    .title-content {
      /* Exercício 2 */
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    #search-input {
      padding: 6px;
      border-radius: 5px;
    }

    .search-panel {
    /* Exercício 3 */
      display: flex;
      justify-content: center;
      align-items: center;
    }
    
    .nav-main {
      display: flex;
    }

    .nav-main div {
      display: flex;
      font-size: 13px;
      margin: 0 10px;
      width: 100px;
      height: 100px;
      border: 1px solid black;
      border-radius: 10px;
      background-color: rgb(153, 116, 151);
    }

    .icons {
      /* Exercício 4 */
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    .nav-profile {
      /* Exercício 5 */
      display: flex;
      align-items: flex-end;
      width: 300px;
      justify-content: space-between;
    }
  
    .personal{
      /* Exercício 6 */
      display: flex;
      align-items: center;
    }

    .nav-user {
      /* Exercício 7 */
      display: flex;
      flex-direction: column-reverse;
    }

  </style>
</head>
<body>

  <header class="header">
    <section class="title-content">
      <div id="title">
        <h1>TRYBEBOOK</h1>
      </div>
      <div class="search-panel">
        <img id="logo" src="https://img.icons8.com/ios-filled/50/26e07f/y-combinator.png"/>
        <input id="search-input" placeholder="Pesquise aqui!">
      </div>
    </section>

    <section class="nav-main">
      <div class="icons">
        <p>Página Inicial</p>
        <img src="https://img.icons8.com/pastel-glyph/50/000000/browser-homepage--v2.png"/>
      </div>
      <div class="icons">
        <p>Vídeos</p>
        <img src="https://img.icons8.com/dotty/50/000000/movies-folder--v1.png"/>
      </div>
      <div class="icons">
        <p>Grupos</p>
        <img src="https://img.icons8.com/pastel-glyph/50/000000/groups--v4.png"/>
      </div>
      <div class="icons">
        <p>Jogos</p>
        <img src="https://img.icons8.com/ios/50/000000/footman.png"/>
      </div>
    </section>

    <section class="nav-profile">
      <section class="personal">
        <img id="user-image" src="https://img.icons8.com/material-sharp/59/26e07f/user-male-circle.png"/>
        <div>Nome do usuário</div>
      </section>
      <section class="nav-user">
        <img id="user-menu" src="https://img.icons8.com/fluent-systems-filled/40/000000/top-menu.png"/>
        <img id="user-notifications" src="https://img.icons8.com/material-rounded/40/000000/bell--v1.png"/>
        <img id="user-settings" src="https://img.icons8.com/windows/40/000000/user-settings.png"/>
      </section>
    </section>
  </header>
  <section>
    <p>Todos os ícones foram retirados do site <a href="https://icons8.com.br/" target="_blank">icons8</a></p>
  </section>
</body>
</html>
```

## Recursos Adicionais

E aí, gostou do novo aprendizado? Que tal praticar um pouco mais e se aprofundar nisso. Seguem algumas referências para aprender e até se divertir aprendendo:

* [Froggy](http://flexboxfroggy.com/#pt-br)
* [Grid Garden](https://cssgridgarden.com/)
* [Flexbox Defense](http://www.flexboxdefense.com/)
* [Flexbox Zombies](https://mastery.games/flexboxzombies/)
* [TreinaWeb](https://www.treinaweb.com.br/blog/css-flexbox-um-guia-interativo-parte-1-containers/)





