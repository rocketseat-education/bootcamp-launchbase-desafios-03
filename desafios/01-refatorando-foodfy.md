# Refatorando Foodfy

Nesse desafio você irá refatorar, ou seja, reescrever algumas partes, do seu código do desafio anterior, o Foodfy.

Até esse módulo não conhecíamos sobre back-end, ou seja, todos dados da nossa página ficavam no próprio front-end (arquivos HTML).

Agora que conhecemos sobre Node.js vamos tornar a exibição dos dados mais dinâmica :rocket: 

## Arquivo de dados

Crie um arquivo `data.js` na raiz do seu projeto com o conteúdo do link abaixo:

[Arquivo data.js](https://github.com/Rocketseat/bootcamp-launchbase-desafios-03/blob/master/data.js)

## Alterações no projeto

Use os dados das receitas contidos no arquivo `data.js` para a página de listagem de receitas e para a home.

Na home, liste as 6 primeiras receitas, não é necessário agora sabermos sobre as receitas mais acessadas.

Na listagem, liste todas receitas do arquivo.

*Obs.: Você precisará converter seu projeto em um projeto Node.js usando Nunjucks para mostrar cada página.*

## Detalhe da receita

<div align="center">
  <img src="https://rocketseat-cdn.s3-sa-east-1.amazonaws.com/mockup-detalhe-receita.png" />
</div>

- Ao clicar em uma receita agora o usuário deve ser redirecionado para uma nova página contendo todas informações da receita como ingredientes, modo de preparo e informações adicionais (todas essas informações estão contidas no arquivo `data.js`).
- Na página de listagem não é mais necessário abrir o modal como tínhamos no desafio anterior do Foodfy.

**Download dos arquivos:** https://github.com/Rocketseat/bootcamp-launchbase-desafios-03/archive/master.zip

Acesse o arquivo `layouts/specs/index.html` para ver todas especificações do layout da página.

*Obs.: A página do detalhe da receita precisa buscar no arquivo `data.js` apenas a receita desejada pelo usuário, por isso você usará de parâmetros na rota dessa página, por exemplo: `http://localhost:3000/recipes/3`, nesse caso estaríamos acessando os detalhes da receita com índice 3 no array de receitas (recipes[3]).*

Para obter um ID da receita através da URL no Node.js você vai usar conforme o exemplo:

```js
server.get("/recipes/:index", function (req, res) {
  const recipes = [...]; // Array de receitas carregadas do data.js
  const recipeIndex = req.params.index;
  
  console.log(receipts[recipeIndex]);
})
```

## Ação de mostrar/esconder

Dentro da página do detalhe da receita, em cada seção "Ingredientes", "Modo de preparo" e "Informações adicionais" há um botão `Mostrar` ou `Esconder` que ao ser clicado deve mostrar ou esconder o texto abaixo do título baseado em seu estado de visibilidade.
