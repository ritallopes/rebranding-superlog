# Exemplos comentados

Use cada exemplo no módulo indicado. São pontos de partida: complete os exercícios antes de consultar os trechos mais avançados.

## Módulo 2 — Estrutura HTML

```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <!-- Faz a página usar a largura real da tela do dispositivo. -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Superlog — Projeto de estudo</title>
  </head>
  <body>
    <header>
      <a href="#inicio">Superlog</a>
      <nav aria-label="Navegação principal">
        <a href="#metodo">Conheça o método</a>
      </nav>
    </header>
    <main id="inicio">
      <h1>Conheça o método Superlog</h1>
      <p>Uma página de estudo para apresentar o método e seus públicos.</p>
      <!-- O id cria o destino do link da navegação. -->
      <section id="metodo" aria-labelledby="titulo-metodo">
        <h2 id="titulo-metodo">Como funciona o método</h2>
        <p>Texto de apresentação a confirmar.</p>
      </section>
    </main>
    <footer><p>Projeto educacional de reformulação.</p></footer>
  </body>
</html>
```

**Experimente:** acrescente uma seção `publicos` e um link que leve a ela. Explique a diferença entre `href` e `id`.

## Módulo 5 — Dados e funções

```js
const publicos = [
  { id: 'criancas', titulo: 'Crianças', descricao: 'Conteúdo a confirmar.' },
  { id: 'jovens', titulo: 'Jovens', descricao: 'Conteúdo a confirmar.' },
];

function buscarPublicos(lista, termo) {
  // Padroniza a busca para aceitar maiúsculas e espaços nas pontas.
  const busca = termo.trim().toLowerCase();
  return lista.filter((publico) =>
    publico.titulo.toLowerCase().includes(busca)
  );
}

console.log(buscarPublicos(publicos, ' JOV '));
```

**Experimente:** adicione os outros públicos e confira uma busca sem resultado. Por que um termo vazio retorna todos os itens?

## Módulo 6 — Menu que preserva a navegação sem JavaScript

HTML:

```html
<!-- O botão só será exibido quando o JavaScript estiver funcionando. -->
<button id="botao-menu" type="button" aria-controls="navegacao"
  aria-expanded="false" hidden>Menu</button>
<nav id="navegacao" aria-label="Navegação principal">
  <a href="#metodo">Método</a>
  <a href="#publicos">Públicos</a>
</nav>
```

JavaScript, carregado com `defer`:

```js
const botao = document.querySelector('#botao-menu');
const navegacao = document.querySelector('#navegacao');
const telaLarga = window.matchMedia('(min-width: 48rem)');

function atualizarMenu(aberto) {
  botao.setAttribute('aria-expanded', String(aberto));
  // Em tela larga a navegação fica disponível o tempo todo.
  navegacao.hidden = !telaLarga.matches && !aberto;
}

function ajustarTela() {
  botao.hidden = telaLarga.matches;
  atualizarMenu(false);
}

botao.addEventListener('click', () => {
  atualizarMenu(botao.getAttribute('aria-expanded') !== 'true');
});

document.addEventListener('keydown', (evento) => {
  if (evento.key === 'Escape' && !telaLarga.matches && !navegacao.hidden) {
    atualizarMenu(false);
    botao.focus();
  }
});

telaLarga.addEventListener('change', ajustarTela);
ajustarTela();
```

Se seus estilos de layout sobrescreverem a propriedade `hidden`, adicione `[hidden] { display: none !important; }`. **Experimente:** redimensione a tela com o menu aberto; depois desative JavaScript e confira os links.

## Módulo 8 — Componente e propriedades

```jsx
function CartaoPublico({ titulo, descricao }) {
  return (
    <article className="cartao-publico">
      <h3>{titulo}</h3>
      <p>{descricao}</p>
    </article>
  );
}

export default function SecaoPublicos({ publicos }) {
  return (
    <section aria-labelledby="titulo-publicos">
      <h2 id="titulo-publicos">Para quem é o Superlog?</h2>
      <div className="grade-publicos">
        {publicos.map((publico) => (
          // O id identifica cada cartão entre os itens da lista.
          <CartaoPublico key={publico.id}
            titulo={publico.titulo} descricao={publico.descricao} />
        ))}
      </div>
    </section>
  );
}
```

**Experimente:** passe a lista de públicos a partir de `App`. Depois altere uma descrição somente no array e observe o cartão.

## Módulo 8 — Busca com estado

```jsx
import { useState } from 'react';

export default function BuscaPublicos({ publicos }) {
  const [termo, setTermo] = useState('');
  // A lista é calculada a partir do estado; não precisa de outro estado.
  const filtrados = publicos.filter((publico) =>
    publico.titulo.toLowerCase().includes(termo.trim().toLowerCase())
  );

  return (
    <section aria-labelledby="titulo-busca">
      <h2 id="titulo-busca">Encontre um público</h2>
      <label htmlFor="busca-publicos">Buscar pelo nome do público</label>
      <input id="busca-publicos" value={termo}
        onChange={(evento) => setTermo(evento.target.value)} />
      <p role="status">{filtrados.length} público(s) encontrado(s).</p>
      <ul>
        {filtrados.map((publico) => <li key={publico.id}>{publico.titulo}</li>)}
      </ul>
      {filtrados.length === 0 && <p>Tente outro termo.</p>}
    </section>
  );
}
```

**Experimente:** substitua a lista simples pelo componente de cartões. Essa busca é um exercício de estado; decida na revisão se ela é útil para apenas quatro públicos.

## Módulo 8 — Efeito com carregamento e cancelamento

Este componente espera um JSON que contenha um array de objetos com `id`, `titulo` e `descricao`.

```jsx
import { useEffect, useState } from 'react';

export default function PublicosRemotos() {
  const [publicos, setPublicos] = useState([]);
  const [carregando, setCarregando] = useState(true);
  const [erro, setErro] = useState('');

  useEffect(() => {
    const controlador = new AbortController();

    async function carregar() {
      try {
        const resposta = await fetch('/dados/publicos.json', {
          signal: controlador.signal,
        });
        if (!resposta.ok) throw new Error('Falha na resposta');
        const dados = await resposta.json();
        if (!Array.isArray(dados)) throw new Error('Formato inesperado');
        if (!controlador.signal.aborted) setPublicos(dados);
      } catch (falha) {
        // Cancelar ao sair do componente não é um erro para a pessoa.
        if (!controlador.signal.aborted) {
          setErro('Não foi possível carregar os públicos. Tente mais tarde.');
        }
      } finally {
        if (!controlador.signal.aborted) setCarregando(false);
      }
    }

    carregar();
    // O React chama esta limpeza quando o efeito é encerrado.
    return () => controlador.abort();
  }, []);

  if (carregando) return <p role="status">Carregando públicos…</p>;
  if (erro) return <p role="alert">{erro}</p>;
  if (publicos.length === 0) return <p>Nenhum público disponível.</p>;

  return (
    <ul>
      {publicos.map((publico) => <li key={publico.id}>{publico.titulo}</li>)}
    </ul>
  );
}
```

**Experimente:** teste com `[]`, um caminho inexistente e a conexão lenta nas ferramentas do navegador. Este exemplo valida apenas que os dados formam um array; como desafio, confira também os campos de cada objeto.
