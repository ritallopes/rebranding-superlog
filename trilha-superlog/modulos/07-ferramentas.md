# Módulo 7 — Ferramentas, módulos e dados

**Pré-requisito:** módulo 6. **Objetivo:** preparar a transição para um projeto com ferramentas de desenvolvimento.

## Exercício 7.1 — Terminal e npm

**Tarefa:** instale uma versão LTS do Node.js pela fonte oficial, se ainda não tiver. Abra o terminal na pasta do projeto e confira `node --version` e `npm --version`.

**Passos:** pratique `pwd`, `ls` e `cd`; anote a diferença entre pasta, arquivo e comando; explique que npm gerencia pacotes e scripts.

**Confira:** sabe identificar em qual pasta está antes de executar um comando. Não precisa instalar React ainda.

## Exercício 7.2 — Histórico com Git

**Tarefa:** dentro da pasta do projeto, use `git status` para verificar se já existe um repositório; se não existir, inicialize com `git init`.

**Passos:** crie `.gitignore` para `node_modules/` e `dist/`; confira os arquivos antes de usar `git add`; registre uma versão com `git commit -m "Cria versão inicial do Superlog"`.

**Confira:** o histórico contém os arquivos do projeto e não contém pastas de dependências. Se houver um repositório na pasta superior, use o existente e selecione apenas os arquivos pertinentes.

## Exercício 7.3 — Módulos JavaScript

**Tarefa:** mova a lista de públicos para `js/dados.js`, exporte e importe em `script.js`.

**Passos:** troque a tag de script para `type="module"`; use `export` e `import`; rode um servidor local, por exemplo com uma extensão de servidor do editor. Evite abrir módulos diretamente por `file://`.

**Confira:** os dados continuam disponíveis e você explica por que organizá-los em outro arquivo facilita manutenção.

## Exercício 7.4 — Dados com fetch

**Tarefa:** crie `dados/publicos.json` com os públicos e carregue usando `fetch` no servidor local. Esse arquivo simula um recurso de uma API, sem depender de um serviço externo.

**Passos:** aprenda `async`/`await`; verifique `response.ok`; converta com `response.json()`; mostre carregamento, sucesso, lista vazia e erro; use `try...catch`.

**Confira:** um caminho incorreto produz mensagem útil; o estado de carregamento termina tanto em sucesso quanto em falha; dados são inseridos como texto, não como HTML arbitrário.

## Exercício 7.5 — Preparação conceitual

**Tarefa:** identifique blocos repetidos e agrupe responsabilidades: cabeçalho, cartão de público, seção e formulário.

**Passos:** desenhe uma árvore desses blocos; marque quais recebem dados e quais têm estado que muda por interação.

**Confira:** sabe distinguir conteúdo recebido de estado interativo. Essa árvore guiará os componentes React.

**Entrega:** projeto organizado, histórico inicial e carregamento local com tratamento de falhas.
