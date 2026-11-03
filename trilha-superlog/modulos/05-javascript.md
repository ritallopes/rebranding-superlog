# Módulo 5 — JavaScript básico

**Pré-requisito:** módulo 4. **Objetivo:** aprender a linguagem antes de controlar a página.

Crie `js/estudos.js`, conecte ao HTML com `<script src="js/estudos.js" defer></script>` e abra o console nas ferramentas do navegador. Use apenas dados fictícios nos exercícios.

## Exercício 5.1 — Variáveis e tipos

**Tarefa:** crie constantes para nome do método, nome de um público e quantidade fictícia de etapas. Crie uma variável booleana que indique se uma pergunta está aberta.

**Passos:** mostre os valores com `console.log`; compare texto, número e booleano; altere a variável com `let`.

**Confira:** você explica quando usou `const` e `let`; não mistura um número com sua representação em texto sem perceber.

## Exercício 5.2 — Condições

**Tarefa:** receba o nome de um público em uma variável e escolha uma mensagem correspondente com `if`, `else if` e `else`.

**Passos:** teste “crianças”, “jovens”, “adultos”, “sênior” e um valor desconhecido; use comparação estrita `===`.

**Confira:** cada caso tem uma saída prevista e o caso desconhecido tem uma mensagem útil. Não transforme o exercício em recomendação clínica.

## Exercício 5.3 — Funções

**Tarefa:** escreva `criarSaudacao(nome)` e `obterDescricaoPublico(publico)`.

**Passos:** receba dados por parâmetros; devolva o resultado com `return`; chame cada função com três entradas diferentes; trate nome vazio.

**Confira:** a função retorna o texto e quem a chama decide como exibi-lo. Você distingue `return` de `console.log`.

## Exercício 5.4 — Arrays e objetos

**Tarefa:** crie um array de quatro objetos com `id`, `titulo` e `descricao`, representando os públicos.

**Passos:** acesse o primeiro objeto; percorra com `for...of`; produza um array de títulos com `map`; filtre por parte de um título com `filter`; localize um item com `find`.

**Confira:** sabe diferenciar o array retornado por `filter` do item retornado por `find`; a busca sem resultado não causa erro.

## Exercício 5.5 — Desafio de consolidação

**Tarefa:** crie `buscarPublicos(lista, termo)` que devolva os públicos cujo título contém o termo, sem diferenciar maiúsculas de minúsculas.

**Passos:** use `trim`, `toLowerCase` e `includes`; defina que termo vazio retorna todos; teste “JOV”, texto inexistente e espaços em branco.

**Confira:** a lista original permanece intacta e todos os casos têm resultado compreensível.

**Entrega:** arquivo de estudos com comentários explicando as decisões. Exemplo: `// Uma busca vazia mostra todos os públicos.` Evite comentar cada símbolo.
