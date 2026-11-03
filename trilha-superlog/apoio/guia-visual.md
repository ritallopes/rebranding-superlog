# Guia visual de estudo

Direção proposta: uma página educacional acolhedora, organizada e confiável. Esta paleta é um exercício de design; não representa um manual oficial da marca.

## Ponto de partida

```css
:root {
  /* Cada cor tem uma função para facilitar ajustes em toda a página. */
  --cor-principal: #164e63;
  --cor-destaque: #fbbf24;
  --cor-texto: #172033;
  --cor-texto-suave: #475569;
  --cor-fundo: #f8fafc;
  --cor-superficie: #ffffff;

  /* Repetir uma escala ajuda a manter os espaços consistentes. */
  --espaco-1: 0.5rem;
  --espaco-2: 1rem;
  --espaco-3: 1.5rem;
  --espaco-4: 2rem;
  --espaco-5: 3rem;
  --espaco-6: 4.5rem;
  --raio: 1rem;
}

* { box-sizing: border-box; }

body {
  margin: 0;
  font-family: system-ui, sans-serif;
  line-height: 1.6;
  color: var(--cor-texto);
  background: var(--cor-fundo);
}

.container {
  /* Limita a largura, preservando uma margem em telas pequenas. */
  width: min(100% - 2rem, 70rem);
  margin-inline: auto;
}

p { max-width: 65ch; }
img { max-width: 100%; height: auto; }

:focus-visible {
  outline: 3px solid var(--cor-principal);
  outline-offset: 4px;
}
```

Confira o contraste em cada combinação efetivamente usada. Por exemplo, prefira texto escuro sobre amarelo; uma cor de destaque não serve automaticamente como fundo para texto branco. Em superfícies escuras, adapte a cor do foco para que permaneça visível.

## Princípios para aplicar

- **Hierarquia:** destaque uma ideia por seção. Título, explicação e ação devem ter pesos diferentes.
- **Alinhamento:** faça cabeçalho, apresentação e seções seguirem as mesmas bordas de conteúdo.
- **Proximidade:** deixe elementos relacionados mais próximos entre si.
- **Repetição:** reutilize o estilo de cartões, botões e títulos.
- **Espaço:** use áreas vazias para separar assuntos, sem tentar preencher toda a tela.
- **Imagens:** use imagens relevantes e com resolução suficiente. Evite ampliar arquivos pequenos ou distorcer proporções.
- **Movimento:** adicione apenas quando comunicar uma mudança útil; a página não precisa de animações para parecer profissional.

## Revisão rápida

Observe a página em tamanho reduzido: ainda é possível reconhecer a ordem de importância? Depois leia um parágrafo no celular: o tamanho e o espaçamento são confortáveis? Por último, procure a próxima ação: ela está clara sem competir com vários botões igualmente fortes?
