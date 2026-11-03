# Como executar os exercícios

Este guia acompanha os módulos. Os arquivos da trilha são materiais de estudo; a página será criada por você nos exercícios. Os comandos abaixo usam o Terminal do macOS ou o terminal integrado do seu editor. Digite um comando por vez e pressione Enter. Não copie as linhas de marcação dos blocos de código.

## 1. Prepare o ambiente

Você precisa de um editor de código e de um navegador. Abra no editor a pasta:

```text
/Users/rita/Documents/ChatGPT/basics studies
```

No Terminal, entre nessa mesma pasta. As aspas preservam os espaços no caminho:

```sh
cd "/Users/rita/Documents/ChatGPT/basics studies"
pwd
```

O segundo comando deve mostrar o caminho acima. Os comandos deste guia pressupõem essa organização. Se mudar a pasta, adapte os caminhos.

## 2. Execute o módulo 1

O módulo 1 não exige servidor nem código. Abra `trilha-superlog/modulos/01-planejamento.md`, leia um exercício por vez e crie `planejamento.md` na pasta de estudos para registrar as respostas. Faça os esboços no papel ou em uma ferramenta de desenho de sua escolha.

**Concluído quando:** você tem público, ação principal, ordem das seções e dois esboços definidos.

## 3. Crie a estrutura da versão HTML

Ao começar o módulo 2, execute:

```sh
cd "/Users/rita/Documents/ChatGPT/basics studies"
mkdir -p projeto-superlog/css projeto-superlog/js projeto-superlog/assets projeto-superlog/dados
```

No editor, crie os arquivos conforme o módulo pedir. A estrutura crescerá assim:

```text
basics studies/
├── planejamento.md
├── trilha-superlog/          ← enunciados e exemplos
└── projeto-superlog/         ← seu código
    ├── index.html
    ├── css/
    │   └── style.css
    ├── js/
    │   ├── estudos.js
    │   ├── script.js
    │   └── dados.js
    ├── dados/
    │   └── publicos.json
    └── assets/              ← imagens locais
```

Comece apenas com `index.html`. Copie o exemplo de estrutura HTML do material de apoio, salve e abra o arquivo no navegador com um duplo clique no Finder. O endereço começará com `file://`.

**Concluído quando:** o título e o texto que você escreveu aparecem no navegador. Depois de cada alteração, salve no editor e recarregue a página com Command+R.

## 4. Conecte CSS e JavaScript

No módulo 3, crie `css/style.css` e adicione dentro de `head` em `index.html`:

```html
<!-- O caminho parte da pasta em que está o index.html. -->
<link rel="stylesheet" href="css/style.css" />
```

No módulo 5, crie `js/estudos.js` e adicione antes de `</body>`:

```html
<!-- defer espera o HTML ser lido antes de executar o arquivo. -->
<script src="js/estudos.js" defer></script>
```

No módulo 6, mantenha os estudos separados das interações e acrescente:

```html
<script src="js/script.js" defer></script>
```

Não cole novamente o mesmo exemplo no mesmo arquivo: nomes de variáveis repetidos podem gerar erros. Adapte o trecho que já existe.

**Concluído quando:** uma regra de CSS muda a aparência e um `console.log('Arquivo carregado')` aparece no console do navegador. Você pode remover essa mensagem depois da conferência.

## 5. Use um servidor local

Nos módulos iniciais, abrir `index.html` diretamente é suficiente. A partir do módulo 7, módulos JavaScript e `fetch` precisam de um servidor local.

Se usa VS Code, uma opção é instalar a extensão **Live Server**, abrir a pasta `projeto-superlog`, clicar com o botão direito em `index.html` e escolher **Open with Live Server**. Abra o endereço local informado pela extensão. Para encerrar, use o controle de parada da extensão.

Outra opção, se Python 3 estiver instalado, é executar:

```sh
cd "/Users/rita/Documents/ChatGPT/basics studies/projeto-superlog"
python3 --version
python3 -m http.server 8000 --bind 127.0.0.1
```

Abra [a página local](http://127.0.0.1:8000) no navegador. Mantenha esse terminal aberto enquanto estuda. Para encerrar o servidor, clique no terminal e pressione Control+C. Se `python3` não existir, use a opção do editor.

Se a porta estiver ocupada, encerre seu servidor anterior ou troque `8000` por `8001`, tanto no comando quanto no endereço.

No exercício de módulos JavaScript, substitua a tag de `script.js` por:

```html
<!-- type="module" permite usar import e export. -->
<script type="module" src="js/script.js"></script>
```

Não mantenha as duas tags carregando o mesmo arquivo. Módulos já têm execução adiada por padrão.

Para buscar os dados na versão HTML, use `fetch('./dados/publicos.json')`. O arquivo deve conter JSON válido, por exemplo:

```json
[
  {
    "id": "criancas",
    "titulo": "Crianças",
    "descricao": "Conteúdo a confirmar."
  }
]
```

JSON usa aspas duplas, não aceita comentários e não aceita vírgula depois do último item.

**Concluído quando:** a página abre por `http://` e o arquivo JSON pode ser aberto em `http://127.0.0.1:8000/dados/publicos.json` se você usa o servidor Python acima.

## 6. Crie e execute a versão React

Faça esta etapa somente ao chegar ao módulo 8. Instale Node.js em versão LTS a partir do [site oficial](https://nodejs.org/), se necessário, e reabra o terminal após a instalação.

Confira:

```sh
node --version
npm --version
```

Crie o projeto ao lado de `projeto-superlog`, preservando sua versão HTML:

```sh
cd "/Users/rita/Documents/ChatGPT/basics studies"
npm create vite@latest superlog-react -- --template react
cd superlog-react
npm install
npm run dev
```

Se o npm perguntar se pode instalar o pacote de criação, confirme para continuar. Siga eventuais mensagens sobre versão mínima do Node. Se a pasta `superlog-react` já existir, abra e examine seu conteúdo antes de tentar criar o projeto novamente.

Abra no navegador o endereço **Local** exibido no terminal. A porta pode variar. Mantenha o terminal aberto; as alterações salvas normalmente aparecem automaticamente.

Comece editando `src/App.jsx`. Importe seu CSS nesse arquivo, por exemplo `import './App.css';`. Componentes podem ficar em `src/components/`. Para o exercício de busca remota, coloque o JSON em `public/dados/publicos.json` e use `fetch('/dados/publicos.json')`.

Para parar o servidor: Control+C no terminal.

**Concluído quando:** você altera um título em `App.jsx` e vê a mudança no navegador.

## 7. Retome o projeto em outro dia

Para a versão HTML, abra o arquivo ou reinicie o servidor local descrito na etapa 5.

Para a versão React:

```sh
cd "/Users/rita/Documents/ChatGPT/basics studies/superlog-react"
npm run dev
```

Você não precisa criar o projeto novamente. Execute `npm install` outra vez apenas quando precisar instalar ou atualizar dependências, ou quando estiver em uma cópia sem a pasta `node_modules`.

## 8. Confira a versão final React

Na pasta `superlog-react`, execute:

```sh
npm run build
npm run preview
```

O primeiro comando deve terminar sem erros e gerar a pasta `dist`. O segundo serve essa versão para conferência local: abra o endereço exibido no terminal. Isso não publica o site na internet.

Se existir um script `lint` no `package.json`, execute também:

```sh
npm run lint
```

Ao mudar o código depois do build, gere outro build para atualizar a prévia. Siga a lista de revisão do módulo 9.

## 9. Rotina para cada exercício

1. Leia tarefa, passos e critérios de conferência.
2. Abra os arquivos relacionados ao exercício.
3. Faça uma alteração pequena e salve.
4. Observe no navegador e abra o console se houver problema.
5. Teste os casos pedidos, incluindo teclado e tela pequena quando aplicável.
6. Registre o que aprendeu e só então avance.

Para abrir as ferramentas do navegador, clique com o botão direito na página e escolha **Inspecionar**. A aba **Console** mostra mensagens e erros; **Network/Rede** ajuda a identificar arquivos que não carregaram. No Safari, pode ser necessário ativar as ferramentas para desenvolvedores nas configurações avançadas.

## 10. Problemas comuns

| Problema | O que conferir |
| --- | --- |
| A alteração não aparece | Salve o arquivo; confirme que está na aba e na pasta corretas; recarregue. |
| CSS não funciona | Confira a tag `link`, o nome do arquivo e o caminho `css/style.css`. |
| Imagem não aparece | Confira caminho, extensão e letras maiúsculas/minúsculas. |
| `Cannot use import statement outside a module` | Use `type="module"` na versão HTML e abra por servidor local. |
| `Failed to fetch` ou erro de CORS ao abrir arquivo local | Use servidor HTTP e confirme o caminho do JSON. |
| Resposta 404 | O arquivo não foi encontrado; confira endereço e pasta que o servidor está servindo. |
| Erro ao converter JSON | Abra o arquivo e confira aspas, vírgulas e conteúdo; uma página HTML de erro não é JSON. |
| `node` ou `npm`: comando não encontrado | Instale Node.js e reabra o terminal. |
| npm não encontra `package.json` | Entre em `superlog-react` antes de executar scripts. |
| Tela branca no React | Leia o primeiro erro do terminal e do console; confira imports, nomes e JSX. |
| Porta ocupada | Use o novo endereço informado pela ferramenta ou escolha outra porta no servidor Python. |

Ao pedir ajuda, informe o módulo e o exercício, o que esperava ver, o que apareceu e a mensagem de erro completa. Isso permite corrigir o problema sem refazer etapas que já funcionam.
