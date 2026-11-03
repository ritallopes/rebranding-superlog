# Módulo 8 — React

**Pré-requisito:** módulo 7. **Objetivo:** reconstruir a página usando componentes, propriedades e estado.

## Exercício 8.1 — Crie o ambiente

**Tarefa:** em uma pasta ao lado da versão HTML, crie o projeto com o modelo React em JavaScript do Vite.

```sh
npm create vite@latest superlog-react -- --template react
cd superlog-react
npm install
npm run dev
```

**Passos:** leia o endereço informado pelo terminal; encontre `src/App.jsx` e o arquivo de estilos importado; substitua a tela inicial por um título do projeto. Os requisitos de versão do Node podem mudar: siga a mensagem da ferramenta se ela exigir atualização.

**Confira:** consegue iniciar e parar o servidor, localizar o componente principal e ver uma alteração no navegador.

## Exercício 8.2 — JSX e primeiros componentes

**Tarefa:** crie `Cabecalho`, `Apresentacao` e `Rodape`; componha a página em `App`.

**Passos:** adapte `class` para `className` e `for` dos rótulos para `htmlFor`; feche as tags; use chaves para expressões; importe os estilos existentes gradualmente.

**Confira:** cada componente tem responsabilidade clara; títulos e links mantêm a semântica da versão HTML.

## Exercício 8.3 — Propriedades e listas

**Tarefa:** crie `CartaoPublico` recebendo título e descrição por propriedades e renderize os cartões a partir de um array.

**Passos:** use `map`; passe uma `key` estável baseada no `id`; consulte o exemplo de apoio; não copie quatro componentes com textos diferentes.

**Confira:** alterar um objeto atualiza o cartão correspondente; não há aviso de chave no console. Propriedades são dados recebidos, não devem ser alteradas pelo componente.

## Exercício 8.4 — Estado e eventos

**Tarefa:** reimplemente o menu usando `useState` e adicione uma busca por público.

**Passos:** armazene o termo digitado; calcule a lista filtrada a partir dele; mostre uma mensagem para resultado vazio; sincronize `aria-expanded` com o estado do menu.

**Confira:** limpar a busca restaura todos os cartões; o DOM é atualizado pelo React. Não use `querySelector` para alterar cartões renderizados por ele.

## Exercício 8.5 — Formulário controlado

**Tarefa:** conecte os campos a estado com `value` e `onChange` e trate o envio demonstrativo.

**Passos:** preserve rótulos e validação; apresente erros compreensíveis; indique explicitamente que nenhuma mensagem foi enviada.

**Confira:** campos aceitam digitação normalmente e o estado acompanha o conteúdo. Compare essa abordagem com a do módulo 6.

## Exercício 8.6 — Efeitos e carregamento

**Tarefa:** coloque o JSON de públicos em `public/dados/publicos.json` e carregue com `fetch` em `useEffect`.

**Passos:** modele carregamento, erro e dados; cancele a requisição no retorno do efeito com `AbortController`; ignore erro de cancelamento; teste caminho inválido e array vazio. Consulte o exemplo de apoio.

**Confira:** há conteúdo útil durante espera e falha; o efeito não entra em repetição; o cancelamento não vira um erro visível.

## Exercício 8.7 — Integração

**Tarefa:** conclua todas as seções, reutilize estilos e remova código de demonstração desnecessário.

**Passos:** organize `src/components`, `src/data` quando houver dados locais e estilos; rode `npm run build`; use `npm run preview` para conferir a versão gerada; rode `npm run lint` se o script estiver disponível.

**Confira:** a versão final preserva a acessibilidade e a responsividade anteriores e não apresenta erros de compilação.

**Entrega:** página React completa. Roteamento, autenticação e backend ficam para uma trilha posterior; esta página não precisa deles para cumprir seu objetivo.
