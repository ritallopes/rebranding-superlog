# Módulo 9 — Acabamento e apresentação

**Pré-requisito:** módulo 8. **Objetivo:** revisar a página com critérios observáveis.

## Exercício 9.1 — Consistência visual

**Tarefa:** revise todos os títulos, botões, cartões e espaços. Compare capturas em celular e desktop.

**Passos:** elimine valores de CSS duplicados sem motivo; confira o alinhamento dos contêineres; escolha imagens coerentes em estilo e recorte; remova ornamentos que competem com o conteúdo.

**Confira:** componentes equivalentes parecem equivalentes; existe uma ação principal clara; textos e imagens têm espaço para respirar.

## Exercício 9.2 — Usabilidade

**Tarefa:** peça a uma pessoa para descobrir para quem é o método, como ele funciona e onde entrar em contato.

**Passos:** não explique onde clicar; registre hesitações e caminhos; pergunte o que a pessoa entendeu; corrija os dois problemas mais relevantes e repita as tarefas.

**Confira:** as tarefas são concluídas com menos dúvidas. Caso não consiga uma pessoa, registre o teste externo como pendente; uma revisão individual não o substitui.

## Exercício 9.3 — Acessibilidade

**Tarefa:** percorra a página com Tab, Shift+Tab, Enter e Escape. Verifique contraste com uma ferramenta de medição.

**Passos:** confira rótulos, foco, ordem de títulos, textos alternativos e zoom a 200%; busque contraste mínimo de 4,5:1 para texto comum e 3:1 para texto grande; teste sem depender de cor. Se adicionar animações, respeite `prefers-reduced-motion`.

**Confira:** não há bloqueio de teclado, conteúdo cortado ou texto essencial de baixo contraste. Uma ferramenta automática ajuda a encontrar problemas, mas não comprova sozinha que a página é acessível.

## Exercício 9.4 — Qualidade técnica

**Tarefa:** confira console, imagens, links, carregamento e mensagens de erro.

**Passos:** use imagens dimensionadas adequadamente, com dimensões declaradas; aplique carregamento tardio em imagens fora da primeira tela quando apropriado; teste o build e a prévia em um segundo navegador disponível; registre os ambientes testados.

**Confira:** não há arquivos ausentes, erros no console nem links de demonstração fingindo ações reais. O formulário continua identificado como demonstração se não houver serviço de envio.

## Exercício 9.5 — Apresente as decisões

**Tarefa:** escreva um README do projeto com objetivo, instruções de execução, imagens do resultado, decisões visuais e limitações.

**Passos:** apresente três comparações entre a primeira versão e a final; justifique cada mudança pelo efeito na leitura ou na navegação; liste testes e pendências reais.

**Confira:** outra pessoa consegue executar o projeto e entender por que as decisões foram tomadas.

## Critérios de conclusão

- [ ] A apresentação explica a proposta e oferece um próximo passo claro.
- [ ] Todas as seções têm função e conteúdo revisado.
- [ ] Tipografia, cores, espaçamentos e componentes são consistentes.
- [ ] A página funciona em telas estreitas e largas, inclusive entre as medidas testadas.
- [ ] Navegação, menu, perguntas e formulário demonstrativo funcionam com teclado.
- [ ] Carregamento, falha e ausência de dados têm tratamento.
- [ ] React usa componentes, propriedades, listas e estado com responsabilidades claras.
- [ ] Build concluído e resultado conferido na prévia.
- [ ] Testes, limitações e eventuais pendências estão documentados.

**Entrega:** página final e uma apresentação curta das decisões. Publicar é uma etapa posterior, após validar conteúdo, materiais e o funcionamento real do contato.
