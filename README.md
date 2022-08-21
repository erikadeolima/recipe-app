# Boas-vindas ao repositório do projeto App de Receitas!

Este projeto faz parte do curso de formação desenvolvedor em web full stack da Trybe. e foi o projeto final do bloco de front-end. E foi realizado em grupo.

Para replicar o projeto, atente-se a cada passo descrito a seguir. Se tiver qualquer dúvida, nos envie por _email_ _erikadeo.lima@hotmail.com_! #vqv 🚀

Aqui, você vai encontrar os detalhes de como estruturar o desenvolvimento do seu projeto a partir deste repositório, utilizando uma branch específica e um _Pull Request_ para colocar seus códigos.

# Termos e acordos

Este projeto faz parte da formação da Trybe, ao clona-lo você comcord em referenciar seus autores e a escola.

# Entregáveis

<details>
  <summary><strong>👨‍💻 O que deverá ser desenvolvido</strong></summary><br />

  Você irá desenvolver um app de receitas, utilizando o que há de mais moderno dentro do ecossistema React: Hooks e Context API!

  Nele será possível: ver, buscar, filtrar, favoritar e acompanhar o progresso de preparação de receitas e drinks!

  ⚠️ A base de dados serão 2 APIs distintas, uma para comidas e outra para bebidas.

  O layout tem como foco dispositivos móveis, dessa forma todos os protótipos vão estar desenvolvidos em telas menores.

  Você pode acessar um protótipo no link abaixo:

  https://www.figma.com/file/XoGZTOjZxNagmjSwdbwYuO/Recipes-App

  **⚠️ Para visualizar os comentários sobre cada componente, basta clicar no ícone de comentários no Figma (lado esquerdo superior).**

  ![image](https://res.cloudinary.com/drdpedroso/image/upload/c_scale,w_400/v1575815877/Screenshot_2019-12-08_at_11.37.25_kzt7rl.png)
</details>

<details>
  <summary><strong>:memo: Habilidades</strong></summary><br />

  Nesse projeto, você será capaz de:

  - Utilizar _Redux_ para gerenciar estado
  - Utilizar a biblioteca _React-Redux_
  - Utilizar a Context API do _React_ para gerenciar estado
  - Utilizar o _React Hook useState_
  - Utilizar o _React Hook useContext_
  - Utilizar o _React Hook useEffect_
  - Criar Hooks customizados
</details>

# Orientações

<details>
  <summary><strong>‼️ Antes de começar a desenvolver</strong></summary><br />

  1. Clone o repositório

  - Use o comando: `git clone `.
  - Entre na pasta do repositório que você acabou de clonar:
    - `cd recipes-app`
  - Vá para a branch do seu grupo:
    - `git checkout -b XXXXXXX && git pull`, onde `XX` é o nome da sua branch.

  2. Instale as dependências e inicialize o projeto

  - Instale as dependências:
    - `npm install`
  - Inicialize o projeto:
    - `npm start` (uma nova página deve abrir no seu navegador com um texto simples)

</details>

<details>
  <summary><strong>🎛 Linter e Stylelint</strong></summary><br />

  Usaremos o [ESLint](https://eslint.org/) para fazer a análise estática do seu código.

  Para garantir a qualidade do seu código de forma a tê-lo mais legível, de mais fácil manutenção e seguindo as boas práticas de desenvolvimento, nós utilizamos neste projeto o linter `ESLint`. Para rodar o linter localmente no seu projeto, execute o comando abaixo:

  ```bash
  npm run lint
  npm run lint:styles
  ```

  Caso ainda fique alguma dúvida, você pode consultar nosso conteúdo sobre [`ESLint`](https://app.betrybe.com/course/real-life-engineer/eslint)

  **PULL REQUESTS COM ERROS DE LINTER NÃO SERÃO AVALIADAS. ATENTE-SE PARA RESOLVÊ-LAS ANTES DE FINALIZAR O DESENVOLVIMENTO!** ⚠

  Você pode também instalar o plugin do `ESLint` no `VSCode`, bastar ir em extensions e baixar o [plugin `ESLint`](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint).
</details>

<details>
  <summary><strong>:busts_in_silhouette: Trello como ferramenta Kanban</strong></summary><br />

  Uma forma para organizar as atividades e dividir as tarefas é através de um modelo de kanban. A Trybe disponibiliza um [aqui o board utilizado](https://trello.com/b/fW8dCjho/app-de-receitas-grupo-4).
</details>

<details>
  <summary><strong>🛠 Testes</strong></summary><br />

  <details><summary><strong>Executando testes de requisito :building_construction:</strong></summary><br />
  
  Nesse projeto foram escritos testes em React Testing Library (RTL), e testam cerca de 88% de cobertura das funcionalidades dessa aplicação.
  Para rodar os testes utilize o comando: `npm test`

  ### Dica: desativando testes

  Para rodar somente um arquivo de teste, você precisa utilizar o comando:

  `npm test 'nome do test'`. Ex.: `npm test Cover`.
  </details>

  <details><summary><strong>Executando testes de cobertura :open_umbrella:</strong></summary><br />
  Alguns requisitos irão pedir para que você desenvolva testes para sua aplicação. Esses testes serão avaliados através da cobertura de testes.

  É possível verificar o percentual da cobertura de testes com o comando `npm run test-coverage`. 

  Você também pode executar `npm run test-coverage -- --collectCoverageFrom=caminho/da/Pagina` para verificar o percentual de cobertura de testes de cada 'Pagina'. Por exemplo, para verificar a cobertura de testes da página de `Login`, execute o comando `npm run test-coverage -- --collectCoverageFrom=src/pages/Login.js`.

  </details>
</details>

<summary><strong>:convenience_store: Desenvolvimento </strong></summary><br />

  * <details><summary><b> APIs :gear:</b></summary>

    * <details><summary><b> TheMealDB API</b></summary>

      O [TheMealDB](https://www.themealdb.com/) é um banco de dados aberto, mantido pela comunidade, com receitas e ingredientes de todo o mundo.

      Os end-points são bastante ricos, você pode [vê-los aqui](https://www.themealdb.com/api.php)

      O modelo de resposta para uma `meal` é o seguinte:
        <details><summary><b>Ver modelo de resposta para uma meal</b></summary>

        ```json
          {
            "meals":[
                {
                  "idMeal":"52882",
                  "strMeal":"Three Fish Pie",
                  "strDrinkAlternate":null,
                  "strCategory":"Seafood",
                  "strArea":"British",
                  "strInstructions":"Preheat the oven to 200C\/400F\/Gas 6 (180C fan).\r\nPut the potatoes into a saucepan of cold salted water. Bring up to the boil and simmer until completely tender. Drain well and then mash with the butter and milk. Add pepper and taste to check the seasoning. Add salt and more pepper if necessary.\r\nFor the fish filling, melt the butter in a saucepan, add the leeks and stir over the heat. Cover with a lid and simmer gently for 10 minutes, or until soft. Measure the flour into a small bowl. Add the wine and whisk together until smooth.\r\nAdd the milk to the leeks, bring to the boil and then add the wine mixture. Stir briskly until thickened. Season and add the parsley and fish. Stir over the heat for two minutes, then spoon into an ovenproof casserole. Scatter over the eggs. Allow to cool until firm.\r\nSpoon the mashed potatoes over the fish mixture and mark with a fork. Sprinkle with cheese.\r\nBake for 30-40 minutes, or until lightly golden-brown on top and bubbling around the edges.",
                  "strMealThumb":"https:\/\/www.themealdb.com\/images\/media\/meals\/spswqs1511558697.jpg",
                  "strTags":"Fish,Seafood,Dairy,Pie",
                  "strYoutube":"https:\/\/www.youtube.com\/watch?v=Ds1Jb8H5Sg8",
                  "strIngredient1":"Potatoes",
                  "strIngredient2":"Butter",
                  "strIngredient3":"Milk",
                  "strIngredient4":"Gruy\u00e8re",
                  "strIngredient5":"Butter",
                  "strIngredient6":"Leek",
                  "strIngredient7":"Plain Flour",
                  "strIngredient8":"White Wine",
                  "strIngredient9":"Milk",
                  "strIngredient10":"Parsley",
                  "strIngredient11":"Salmon",
                  "strIngredient12":"Haddock",
                  "strIngredient13":"Smoked Haddock",
                  "strIngredient14":"Eggs",
                  "strIngredient15":"",
                  "strIngredient16":"",
                  "strIngredient17":"",
                  "strIngredient18":"",
                  "strIngredient19":"",
                  "strIngredient20":"",
                  "strMeasure1":"1kg",
                  "strMeasure2":"Knob",
                  "strMeasure3":"Dash",
                  "strMeasure4":"50g",
                  "strMeasure5":"75g",
                  "strMeasure6":"2 sliced",
                  "strMeasure7":"75g",
                  "strMeasure8":"150ml",
                  "strMeasure9":"568ml",
                  "strMeasure10":"2 tbs chopped",
                  "strMeasure11":"250g",
                  "strMeasure12":"250g",
                  "strMeasure13":"250g",
                  "strMeasure14":"6",
                  "strMeasure15":"",
                  "strMeasure16":"",
                  "strMeasure17":"",
                  "strMeasure18":"",
                  "strMeasure19":"",
                  "strMeasure20":"",
                  "strSource":"https:\/\/www.bbc.co.uk\/food\/recipes\/three_fish_pie_58875",
                  "dateModified":null
                }
            ]
          }
        ```
      </details>
    
      Os ingredientes seguem uma ordem lógica onde o nome dele (<code>strIngredient1</code>) e a quantidade (<code>strMeasure1</code>) tem o mesmo número no final (1, nesse caso).

      É possível listar todas as `categorias`, `nacionalidades` (vindas da API como "areas") e `ingredientes`:

      ```
      categorias: https://www.themealdb.com/api/json/v1/1/list.php?c=list
      nacionalidades: https://www.themealdb.com/api/json/v1/1/list.php?a=list
      ingredientes: https://www.themealdb.com/api/json/v1/1/list.php?i=list
      ```

      As fotos dos ingredientes vêm de um end-point padronizado com a seguinte lógica:

      ```
      https://www.themealdb.com/images/ingredients/{nome-do-ingrediente}-Small.png
      // exemplo com "Lime"
      https://www.themealdb.com/images/ingredients/Lime-Small.png
      ```
      </details>

    * <details><summary><b> The CockTailDB API</b></summary>
      Bem similar (inclusive mantida pela mesma entidade) a TheMealDB API, só que focado em bebidas.

      Os end-points também são bastante ricos, você pode [vê-los aqui](https://www.thecocktaildb.com/api.php)

      As respostas seguem a mesma estrutura, com algumas particularidades relativas às bebidas (como ser ou não alcoólica, por exemplo)

        <details><summary><b>Ver modelo de resposta para drinks</b></summary>

        ```json
          {
            "drinks":[
                {
                  "idDrink":"17256",
                  "strDrink":"Martinez 2",
                  "strDrinkAlternate":null,
                  "strDrinkES":null,
                  "strDrinkDE":null,
                  "strDrinkFR":null,
                  "strDrinkZH-HANS":null,
                  "strDrinkZH-HANT":null,
                  "strTags":null,
                  "strVideo":null,
                  "strCategory":"Cocktail",
                  "strIBA":null,
                  "strAlcoholic":"Alcoholic",
                  "strGlass":"Cocktail glass",
                  "strInstructions":"Add all ingredients to a mixing glass and fill with ice.\r\n\r\nStir until chilled, and strain into a chilled coupe glass.",
                  "strInstructionsES":null,
                  "strInstructionsDE":"Alle Zutaten in ein Mischglas geben und mit Eis f\u00fcllen. Bis zum Abk\u00fchlen umr\u00fchren und in ein gek\u00fchltes Coup\u00e9glas abseihen.",
                  "strInstructionsFR":null,
                  "strInstructionsZH-HANS":null,
                  "strInstructionsZH-HANT":null,
                  "strDrinkThumb":"https:\/\/www.thecocktaildb.com\/images\/media\/drink\/fs6kiq1513708455.jpg",
                  "strIngredient1":"Gin",
                  "strIngredient2":"Sweet Vermouth",
                  "strIngredient3":"Maraschino Liqueur",
                  "strIngredient4":"Angostura Bitters",
                  "strIngredient5":null,
                  "strIngredient6":null,
                  "strIngredient7":null,
                  "strIngredient8":null,
                  "strIngredient9":null,
                  "strIngredient10":null,
                  "strIngredient11":null,
                  "strIngredient12":null,
                  "strIngredient13":null,
                  "strIngredient14":null,
                  "strIngredient15":null,
                  "strMeasure1":"1 1\/2 oz",
                  "strMeasure2":"1 1\/2 oz",
                  "strMeasure3":"1 tsp",
                  "strMeasure4":"2 dashes",
                  "strMeasure5":null,
                  "strMeasure6":null,
                  "strMeasure7":null,
                  "strMeasure8":null,
                  "strMeasure9":null,
                  "strMeasure10":null,
                  "strMeasure11":null,
                  "strMeasure12":null,
                  "strMeasure13":null,
                  "strMeasure14":null,
                  "strMeasure15":null,
                  "strCreativeCommonsConfirmed":"No",
                  "dateModified":"2017-12-19 18:34:15"
                }
            ]
          }
        ```
        </details>
      Os ingredientes seguem uma ordem lógica onde o nome dele (<code>strIngredient1</code>) e a quantidade (<code>strMeasure1</code>) tem o mesmo número no final (1, nesse caso).
      </details>
    </details>

  * <details><summary><b>Requisitos do Projeto :memo:</b></summary>

    Os requisitos são organizados por telas e dessa vez, vocês que irão definir as prioridades! Usem com sabedoria!

    Recomendamos que os requisitos de uma mesma tela sejam feitos em sequência ou paralelamente por pessoas que irão comunicar-se bastante para que não haja conflitos. Requisitos de uma mesma tela com prioridades iguais possam ser feitos em paralelo, mas isso exigirá organização por parte das pessoas que estão dividindo a tarefa para não  haver conflitos.

    * Os requisitos do seu projeto são avaliados automaticamente, sendo utilizada a resolução de tela de `360 x 640` (360 pixels de largura por 640 pixels de altura).

        - ⚠️ Logo, recomenda-se desenvolver seu projeto usando a mesma resolução, via instalação [deste plugin](https://chrome.google.com/webstore/detail/window-resizer/kkelicaakdanhinjdeammmilcgefonfh?hl=en) do `Chrome` para facilitar a configuração da resolução. ⚠️
    </details>

  * <details><summary><b>Obsrevações técnicas :information_source:</b></summary>

    Algumas coisas devem seguir um padrão pré-estabelecido para que os testes de correção funcionem corretamente.

    ⚠️ Leia-os atentamente e siga à risca o que for pedido. O não cumprimento de um requisito, total ou parcialmente, impactará em sua avaliação. ⚠️

    * <details><summary><b> Rotas</b></summary>

      As rotas que foram utilizadas na aplicação são as seguintes:

      * Tela de login: `/`;
      * Tela principal de receitas de comidas: `/foods`;
      * Tela principal de receitas de bebidas: `/drinks`;
      * Tela de detalhes de uma receita de comida: `/foods/{id-da-receita}`;
      * Tela de detalhes de uma receita de bebida: `/drinks/{id-da-receita}`;
      * Tela de receita em progresso de comida: `/foods/{id-da-receita}/in-progress`;
      * Tela de receita em progresso de bebida: `/drinks/{id-da-receita}/in-progress`;
      * Tela de perfil: `/profile`;
      * Tela de receitas feitas: `/done-recipes`;
      * Tela de receitas favoritas: `/favorite-recipes`.
      </details>
      
    * <details><summary><b> LocalStorage</b></summary>

      O uso de `localStorage` foi necessário para que as informações não se perdessem caso a pessoa atualize a página.

      No `localStorage` do navegador:

      * a chave `mealsToken` deve conter a seguinte estrutura:
      ```
      1
      ```

      * a chave `cocktailsToken` deve conter a seguinte estrutura:
      ```
      1
      ```

      * a chave `user` deve conter a seguinte estrutura:
      ```js
      {
          email: email-da-pessoa
      }
      ```

      * a chave `doneRecipes` deve conter a seguinte estrutura:
      ```js
      [{
          id: id-da-receita,
          type: comida-ou-bebida,
          nationality: nacionalidade-da-receita-ou-texto-vazio,
          category: categoria-da-receita-ou-texto-vazio,
          alcoholicOrNot: alcoholic-ou-non-alcoholic-ou-texto-vazio,
          name: nome-da-receita,
          image: imagem-da-receita,
          doneDate: quando-a-receita-foi-concluida,
          tags: array-de-tags-da-receita-ou-array-vazio
      }]
      ```

      * a chave `favoriteRecipes` deve conter a seguinte estrutura:
      ```js
      [{
          id: id-da-receita,
          type: food-ou-drink,
          nationality: nacionalidade-da-receita-ou-texto-vazio,
          category: categoria-da-receita-ou-texto-vazio,
          alcoholicOrNot: alcoholic-ou-non-alcoholic-ou-texto-vazio,
          name: nome-da-receita,
          image: imagem-da-receita
      }]
      ```

      * a chave `inProgressRecipes` deve conter a seguinte estrutura:
      ```js
      {
          cocktails: {
              id-da-bebida: [lista-de-ingredientes-utilizados],
              ...
          },
          meals: {
              id-da-comida: [lista-de-ingredientes-utilizados],
              ...
          }
      }
      ```

      **Observações técnicas**

      * `id-da-bebida` e `id-da-comida` representam o ID de uma bebida e comida, respectivamente, e cada item da lista de ingredientes da respectiva receita deve ser representado apenas pelo número do ingrediente no formato numérico.
      </details>
    
    </details>

    * <details><summary><b> Biblioteca <code>clipboard-copy</code></b></summary>

      Para os componentes que contêm a funcionalidade de favoritar pratos ou bebidas, foi necessário utilizar a biblioteca `clipboard-copy` para copiar as informações da receita. Essa biblioteca já vem instalada no projeto.

      Para mais informações, consulte a [documentação](https://www.npmjs.com/package/clipboard-copy)
      </details>

    * <details><summary><b> Biblioteca <code>Bootstrap</code> (opcional)</b></summary>

      Para os grupos que quiserem implementar estilizações no app, recomendamos o uso da lib `Bootstrap`. Ela já vem instalada por padrão neste projeto, bastando apenas implementar nos seus componentes. Por exemplo, caso queira implementar um [botão](https://react-bootstrap.github.io/components/buttons/):

      ``` jsx
      import Button from 'react-bootstrap/Button';

      const MeuComponente = () => (
        <Button variant="success">
          Botão Verde
        </Button>
      );
      ...
      ```

      Para mais informações, consulte a [documentação](https://react-bootstrap.github.io/getting-started/introduction/)
      </details>
    </details><br />
</details>