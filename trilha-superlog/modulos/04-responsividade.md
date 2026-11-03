# Módulo 4 — Layout responsivo

**Pré-requisito:** módulo 3. **Objetivo:** adaptar a composição ao espaço disponível.

## Exercício 4.1 — Base para celular

**Tarefa:** organize a página em uma coluna e crie um contêiner com largura máxima e margens laterais.

**Passos:** remova larguras rígidas que excedam a tela; use `max-width: 100%` e `height: auto` nas imagens; revise palavras e links longos.

**Confira:** não há rolagem horizontal a 320 px de largura; textos e botões não ficam colados às bordas.

## Exercício 4.2 — Cabeçalho com Flexbox

**Tarefa:** use `display: flex`, `gap`, `align-items` e `flex-wrap` no cabeçalho.

**Passos:** experimente alinhamento e distribuição; mantenha a navegação disponível em telas pequenas enquanto o menu interativo ainda não existe.

**Confira:** o logotipo não é esmagado e os links continuam acessíveis em todas as larguras.

## Exercício 4.3 — Cartões com Grid

**Tarefa:** distribua os públicos em uma coluna no celular e em mais colunas quando houver espaço.

**Passos:** comece com `grid-template-columns: 1fr`; adicione uma media query quando a composição precisar de espaço; experimente `repeat` e `minmax` depois de entender a versão explícita.

**Confira:** os cartões não ficam estreitos demais; a ordem de leitura continua lógica; textos maiores cabem sem cortes.

## Exercício 4.4 — Apresentação e imagens

**Tarefa:** crie uma apresentação com texto e imagem lado a lado em telas largas e empilhados em telas estreitas.

**Passos:** experimente `aspect-ratio` e `object-fit: cover`; escolha o recorte sem esconder conteúdo relevante; use `clamp()` em um título após testar tamanhos fixos.

**Confira:** a imagem tem boa proporção e o título não domina toda a tela pequena.

## Exercício 4.5 — Teste contínuo

**Tarefa:** revise a 320, 375, 768, 1024 e 1440 px e também arrastando a largura entre esses pontos.

**Passos:** teste zoom de 200%; percorra a página com Tab; registre e corrija problemas de sobreposição e quebra de texto.

**Confira:** o layout funciona entre as larguras de referência. Media queries resolvem necessidades do conteúdo, não apenas tamanhos de aparelhos.

**Entrega:** página adaptável com evidências de testes em tela estreita e larga.
