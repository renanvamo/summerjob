
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

Por padrão, o eixo principal é definido como sendo o eixo horizontal, equanto o eixo cruzado como sendo o eixo vertical.

Nessa imagem você pode entender um pouco melhor essa abstração:

![FlexboxAxis](https://s3.us-east-2.amazonaws.com/assets.app.betrybe.com/fundamentals/css-flexbox/css-flexbox-part-1/images/css_flexbox_axes-ae037e975930d45a18d1ef4417501d82.png)

, vamos dar uma olhada em algumas propriedades dos Flex Containers. 

## Flex direction, flex wrap e flex flow

A propriedade que define o direcionamento dos Eixos Principal e Cruzado, é o flex-direction.

Mas nada como a boa e velha prática para que você possa entender melhor como isso funciona e conhecer os principais valores de flex-directions.

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

Outra propriedade que também pode interferir no posicionamento dos itens é a flex-wrap.

Através dessa propriedade podemos definir se os elementos dentro de um flex container, ao atingirem o limite, serão movidos para a linha de baixo ou, se ajustarão seu tamanho para caber dentro do flex container. Por padrão a propriedade é flex-wrap: nowrap; ou seja, não haverá a quebra de linha. 

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

E também temos a propriedade flex-flow.

Esta propriedade nada mais é do que a junção das propriedades flex-direction e flex-wrap em uma só.

```
flex-flow: row nowrap; //(padrão) - podemos usar as combinações como aprendemos antes como por exemplo: flex-flow: column wrap;
```

Experimente substituir nos códigos anteriores as pripriedades flex-direction e flex-wrap por flex-flow, e faça a mágica acontecer.

## Justify content, align items e align content

Depois que você aprendeu a manipular o Main Axis de um Flex Container, está na hora de aprender a alinhar itens dentro deste Flex Container.

Para isso você verá 3 propriedades:

justify-content:
align-itens:
align-content:

Essas propriedades utilizam valores semelhantes, portanto veremos como se comportam separadamente.

A primeira propriedade é justify-content, ela é utilizada para alinhar itens do eixo principal.

Já align-items é utilizada para alignhar os itens do eixo cruzado.

Enquanto align-content só é útil quando possuímos uma quebra de linha no eixo principal.

```
justify-content: flex-start; // padrão
align-items: stretch; // padrão
align-content: stretch; // padrão
```

E a respeito de valores, as propriedades podem utilizar as seguintes:

center - itens sao posicionados ao centro.
stretch - itens se esticam até preencher o container.
baseline - itens se iniciam de acordo com uma base única.
flex-start - itens iniciam alinhamento ao início do flex container.
flex-end - itens iniciam o alinhamento partindo do final deste flex container.
space-around - uma pequena margem ao inicio e ao final do container, e margens maiores entre os itens.
space-between - primeiro e último itens alinhados a borda deste flex container, enquanto possui margens iguais no meio.
space-evenly - margens iguais entre todos itens deste container.

Lembrando que todas estas propriedades, se ajustam de acordo com a posição do eixo principal e cruzado.

Fique atento - Se um flex item possuir um tamanho específico de width e height, algumas propriedades como stretch podem não surtir efeito algum.

Para que você possa ver claramente, copie o código abaixo e vamos mais uma vez ver o funcionamento na prática:

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

Esse novo aprendizado abre muitos horizontes para seus novos projetos e até mesmo para os antigos, agora é só você praticar.

- Exercícios




- Recursos Adicionais




Gabarito de Exercícios

