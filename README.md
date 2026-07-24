# 1. Guia Básico de JavaScript
`#javascript` `#learning`

![Logo JavaScript](Imagens/logo-js.png)
- **Autor**: Luís Marques
- **Data**: 2026-07-14
- **Descrição**: Explicar a origem e a finalidade da linguagem JavaScript
---
## Índice
- [1. Guia Básico de JavaScript](#1-guia-básico-de-javascript)
  - [Índice](#índice)
- [2. Introdução](#2-introdução)
  - [2.1. O que é JavaScript?](#21-o-que-é-javascript)
  - [2.2. Porque foi criada?](#22-porque-foi-criada)
  - [2.3. Porque é popular?](#23-porque-é-popular)
- [3. História de JavaScript](#3-história-de-javascript)
- [4. Principais Características](#4-principais-características)
- [5. Exemplos de código](#5-exemplos-de-código)
- [6. Aplicações da Linguagem](#6-aplicações-da-linguagem)
- [7. Vantagens e Desvantagens](#7-vantagens-e-desvantagens)
- [8. Recursos para Aprender](#8-recursos-para-aprender)
- [9. Conclusão](#9-conclusão)

# 2. Introdução
## 2.1. O que é JavaScript?
**JavaScript** é uma linguagem de programação de **scripting**, **interpretada** e de **alto nível**, criada em **1995** por **Brendan Eich** enquanto trabalhava na Netscape. 

## 2.2. Porque foi criada?
Foi desenvolvida originalmente em *apenas 10 dias*, com o objetivo de tornar as páginas web interativas, permitindo que os programadores adicionassem comportamento dinâmico ao HTML e ao CSS, que por si só são estáticos.

Inicialmente chamava-se **Mocha**, depois **LiveScript**, e só mais tarde recebeu o nome **JavaScript** como estratégia de marketing para aproveitar a *popularidade da Java* na época, embora as duas linguagens sejam bastante diferentes em conceito e sintaxe.

## 2.3. Porque é popular?
A popularidade do JavaScript deve-se a vários fatores. É a única linguagem **nativamente suportada por todos os browsers**, o que a tornou essencial para o **desenvolvimento web** durante décadas. Com o aparecimento do *Node.js em 2009*, passou a poder ser usada também no lado do *servidor (backend)*, permitindo *usar a mesma linguagem em todo o stack de uma aplicação*. 

Além disso, possui um ecossistema enorme de **bibliotecas** e **frameworks** (como React, Vue, Angular e Express), uma comunidade muito ativa e é relativamente fácil de aprender para iniciantes.

Hoje em dia, JavaScript é usado não só em browsers e servidores, mas também em aplicações móveis (React Native), aplicações desktop (Electron) e até em dispositivos IoT, o que a torna uma das linguagens mais versáteis e procuradas no mercado de trabalho.


# 3. História de JavaScript
**JavaScript** foi criado por **Brendan Eich** em **1995**, enquanto trabalhava na **Netscape Communications**. Foi *desenvolvido em apenas 10 dias* para o navegador Netscape Navigator 2.0, com o **objetivo** de tornar as páginas **web dinâmicas e interativas**.

Evolução ao longo do tempo:
- **1995** — Criado com o nome **Mocha**, depois renomeado para **LiveScript** e, por fim, **JavaScript**.
- **1997** — Padronizado pela *ECMA International* sob o nome **ECMAScript (ES1)**, garantindo que diferentes navegadores implementassem a linguagem de forma consistente.
- **2009** — Lançamento do **Node.js**, que permitiu executar *JavaScript fora do browser*, no *lado do servidor*.
- **2015** — Lançamento do **ECMAScript 6 (ES6/ES2015)**, uma atualização histórica que trouxe *let/const*, *arrow functions*, *classes*, *módulos*, *promises*, entre outros.
- **2012** - A Microsoft lança o ***TypeScript***, um *superset* de **JavaScript** com tipagem estática, criado para facilitar o desenvolvimento de aplicações grandes e complexas.
- **2015 até hoje** — A partir do *ES6*, o **TC39** (*comité responsável pela linguagem*) passou a lançar uma **nova versão anual** (ES2016, ES2017... ES2024), com *melhorias incrementais*.
- **Atualidade** — JavaScript continua em **constante evolução**, sustentado por uma *comunidade enorme* e por **frameworks/bibliotecas** que se atualizam continuamente.


# 4. Principais Características
JavaScript possui diversas características que explicam a sua ampla adoção:

- **Sintaxe simples** — *fácil de ler e escrever*, especialmente para quem *já conhece outras linguagens do estilo C*.
- **Multiplataforma** — corre em **qualquer sistema operativo**, **browser** ou **servidor** (via *Node.js*).
- **Grande comunidade** — uma das comunidades de programadores mais ativas do mundo.
- **Muitas bibliotecas** — *ecossistema vastíssimo* (**npm**), com pacotes para *praticamente qualquer necessidade*.
- **Código aberto** — o *motor V8* (usado no Chrome e Node.js) e *muitas ferramentas do ecossistema são open source*.
- **Fácil aprendizagem** — boa linguagem para *iniciantes*, com *muitos recursos* de aprendizagem disponíveis.
- **Tipagem dinâmica e fraca** — as variáveis **não** têm *tipo fixo*, o que *agiliza a escrita de código* (mas pode gerar erros subtis).
- **Orientada a eventos** — muito usada para responder a *interações do utilizador* *(cliques, teclas, etc.)*.
- **Assíncrona** — suporta operações **não bloqueantes** através de *callbacks, promises* e *async/await*.

  
# 5. Exemplos de código


**Exemplo 1** — Assincronia com `async/await` (consumo de uma API).

Mostra a capacidade do JavaScript de lidar com **operações não bloqueantes**, algo essencial no browser e no Node.js:
```javascript
async function getUser(id) {
  try {
    const response = await fetch(`https://jsonplaceholder.typicode.com/users/${id}`);
    const user = await response.json();
    console.log(`Nome: ${user.name} | Email: ${user.email}`);
  } catch (error) {
    console.error("Erro ao obter utilizador:", error);
  }
}

getUser(1);
```

**Exemplo 2** — Programação funcional com `map`, `filter` e `reduce`

Mostra a *expressividade e concisão* do JavaScript ao trabalhar com coleções de dados, *sem precisar* de ciclos *for* explícitos:

```javascript
const products = [
  { name: "Keyboard", price: 25, inStock: true },
  { name: "Mouse", price: 10, inStock: false },
  { name: "Monitor", price: 150, inStock: true },
];

const totalInStock = products
  .filter((p) => p.inStock)          // apenas produtos disponíveis
  .map((p) => p.price)               // extrai os preços
  .reduce((sum, price) => sum + price, 0); // soma tudo

console.log(`Valor total em stock: ${totalInStock}€`);
// Resultado: 175€
```
# 6. Aplicações da Linguagem

- **Desenvolvimento Web** — a aplicação mais comum, tanto no **frontend** (*React, Vue, Angular*) como no **backend** (Node.js*, Express*).
- **Inteligência Artificial** — bibliotecas como o **TensorFlow.js** permitem *correr* **modelos de machine learning** diretamente no *browser*.
- **Ciência de Dados** — embora *menos comum que Python*, existem bibliotecas como **Danfo.js** para *análise e manipulação de dados*.
- **Jogos** — desenvolvimento de **jogos 2D/3D** no *browser* com bibliotecas como **Phaser** ou **Three.js**.
- **Automação** — *scripts* de **automação de tarefas**, **testes end-to-end** (*Playwright, Cypress*) e **scraping de dados**.
- **Aplicações móveis** — através de *frameworks* como **React Native**.
- **Aplicações desktop** — através de *frameworks* como **Electron**.

# 7. Vantagens e Desvantagens

| **Vantagens**           | **Desvantagens**           |
| :------------------ | :--------------------- |
| Fácil para aprender | Difícil de aprofundar (conceitos avançados como `closures`, `this`, `event loop`) |
| Fácil para instalar *frameworks*         | Existe uma enorme variedade de *frameworks*, constantemente a atualizar              |
| Corre em **todos os browsers** sem instalação | Comportamento pode *variar* ligeiramente entre *browsers/motores* |
| Grande **ecossistema** de bibliotecas (*npm*) | Tipagem **dinâmica** pode gerar *erros difíceis de detetar* |
| Permite usar a *mesma linguagem* no **frontend** e **backend** | Gestão de *assincronia* pode ser **confusa** para iniciantes |


# 8. Recursos para Aprender

- **Documentação oficial** — MDN Web Docs — [JavaScript](https://developer.mozilla.org/pt-PT/docs/Web/JavaScript)
- **Tutoriais**:
  - [javascript.info](https://javascript.info/)
  - [W3Schools](https://www.w3schools.com/js/) — JavaScript Tutorial 
- **Cursos**:
  - [freeCodeCamp](https://www.freecodecamp.org/) — JavaScript Algorithms and Data Structures 
  - [The Odin Project](https://www.theodinproject.com/)
- Livros:
  - [Eloquent JavaScript](https://eloquentjavascript.net/) — *Marijn Haverbeke (link para e-Book)*
  - [You Don't Know JS](https://github.com/getify/you-dont-know-js) — *Kyle Simpson (link para GitHub com e-Book)*
- Vídeos:
  - Canal [Traversy Media](https://www.youtube.com/@TraversyMedia/playlists)
  - [Learn JavaScript - Full Course for Beginners](https://www.youtube.com/watch?v=PkZNo7MFNFg)
  
# 9. Conclusão

**JavaScript** é uma linguagem *fundamental* no panorama tecnológico atual. É a *única linguagem nativamente suportada* por **todos os browsers**, o que a torna *indispensável* para o **desenvolvimento web**, e a sua *expansão para o backend* (com Node.js), *aplicações móveis e desktop* consolidou-a como uma das linguagens *mais versáteis e procuradas no mercado de trabalho*.

Deve ser usada sempre que se pretenda *criar interatividade em páginas web*, *construir aplicações completas (frontend e backend)* com uma única linguagem, ou *desenvolver protótipos rápidos* graças à sua *sintaxe simples* e ao *vasto ecossistema* de *bibliotecas disponível*. É especialmente recomendada para quem está a dar os primeiros passos na programação, dada a sua *curva de aprendizagem suave* e a *enorme quantidade de recursos e comunidade de suporte*.
